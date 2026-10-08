# Nginx Proxy Manager with Docker Compose 🚀

A production-ready setup for deploying **Nginx Proxy Manager** using Docker Compose. Easily manage reverse proxies, redirection, and free automatic SSL certificates (Let's Encrypt) via a clean web interface.

> 📺 **YouTube Tutorial:** [PouyaStack Channel](https://youtube.com/@PouyaStack)

---

## 📋 Prerequisites
Ensure you have Docker and Docker Compose installed:

docker --version
docker compose version

⚡ Quick Start
1. Clone & Navigate

                                                                  
git clone https://github.com/YOUR_USERNAME/nginx-proxy-manager-docker.git
cd nginx-proxy-manager-docker

2. Run the Stack

                                                                   
docker compose up -d

3. Check Status

                                                                   
docker compose ps

🌐 Web Interface & Default Credentials

Open your browser and navigate to:

http://<SERVER_IP>:81
Field 	Default Value
Email 	admin@example.com
Password 	changeme

    ⚠️ Important: You will be prompted to change the email and password immediately after your first login.

🔒 Security Best Practices

    Change Default Credentials: Set a strong password upon initial login.
    Firewall Restriction: Restrict port 81 to your own IP using UFW or a security group once configuration is complete:

                                                                   
  sudo ufw allow 80/tcp
  sudo ufw allow 443/tcp
  sudo ufw allow from YOUR_LOCAL_IP to any port 81 proto tcp
  

📂 Directory Structure

                                                                    
.
├── docker-compose.yml
├── data/            # Stores SQLite database & configuration (auto-generated)
└── letsencrypt/     # Stores SSL certificates (auto-generated)

📄 License

This project is licensed under the MIT License.

                                                                   

---

### ۳. فایل `.gitignore`
برای اینکه دایرکتوری‌های دیتا و سکرت‌های SSL ناخواسته وارد ریپو نشوند:

```gitignore
data/
letsencrypt/
*.log
.env
