## 🟢 Steps to Reproduce

Follow these steps to set everything up:

---

### 1️⃣ Launch EC2 Instance

- **AMI:** Amazon Linux 2023
- **Instance Type:** t2.micro
- **Security Group Inbound Rules:**
  - Port 22 (SSH) - Your IP
  - Port 80 (HTTP) - 0.0.0.0/0
  - Port 443 (HTTPS) - 0.0.0.0/0

---

### 2️⃣ SSH into the EC2 Instance

```bash
ssh -i /path/to/key.pem ec2-user@<EC2_PUBLIC_IP>
```

---

### 3️⃣ Update and Install NGINX

```bash
sudo yum update -y
sudo yum install -y nginx
sudo systemctl start nginx
sudo systemctl enable nginx
```

✅ Test in browser: `http://<EC2_PUBLIC_IP>`

---

### 4️⃣ Register a Domain

- Register a `.click` domain (e.g., `nginx.azaz.click`) via Route53 or Cloudflare.

---

### 5️⃣ Configure DNS in Route53

- Create an **A record**:

  - **Name:** nginx
  - **Type:** A
  - **Value:** Your EC2 Public IP
  - **TTL:** 300

✅ Confirm propagation with:

```bash
dig nginx.yourdomain.click
```

---

### 6️⃣ Create a Custom NGINX HTML Page

Edit the default index page:

```bash
sudo nano /usr/share/nginx/html/index.html
```

Paste your custom HTML:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Welcome to Azad's NGINX Server</title>
</head>
<body style="text-align:center; font-family:sans-serif;">
  <h1>Hello from Azad's EC2 NGINX Server 🚀</h1>
  <p>This page is secured with HTTPS and deployed on AWS.</p>
</body>
</html>
```

✅ Save and exit.

---

### 7️⃣ Create an NGINX Server Block

Create a new config:

```bash
sudo nano /etc/nginx/conf.d/nginx.azaz.click.conf
```

Paste:

```nginx
server {
    listen 80;
    server_name nginx.azaz.click;

    root /usr/share/nginx/html;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

✅ Test and reload:

```bash
sudo nginx -t
sudo systemctl reload nginx
```

---

### 8️⃣ Install Certbot

```bash
sudo yum install -y certbot python3-certbot-nginx
```

---

### 9️⃣ Generate SSL Certificate

Run:

```bash
sudo certbot --nginx -d nginx.azaz.click
```

✅ Follow the prompts:
- Enter your email
- Agree to terms
- Choose to redirect HTTP to HTTPS

---

### 🔟 Test HTTPS

✅ Visit:

```
https://nginx.azaz.click
```

You should see your custom secure page with a padlock.

---

### 1️⃣1️⃣ Verify Auto-Renewal

```bash
sudo certbot renew --dry-run
```

✅ Confirm there are no errors.

![NGINX Deployment Demo](nginx.gif)



