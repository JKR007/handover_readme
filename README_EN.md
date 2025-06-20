# 📝 Final Documentation for Project Handover

---

## ✅ 1. Project Overview

For **each bot/service**, specify:

- **Name**:
- **Purpose**: What does the bot/service do?
- **Technologies**:
  - Language / framework: Python, Node.js, etc.
  - Libraries: `aiogram`, `python-telegram-bot`, `axios`, etc.
  - DB / cache: PostgreSQL, Redis, etc.
  - Third-party APIs: OpenAI, Telegram, etc.
- **Code Repository**:
  - Repository link: GitHub / GitLab, etc.
  - Branch: `main`, `dev`, etc.
  - Project structure:
    ```
    /project-name
    ├── src/
    ├── config/
    ├── scripts/
    └── README.md
    ```
- **Dependencies**: how to install them (`pip install -r requirements.txt`, etc.)

---

## 💻 2. Local Launch

Step-by-step guide to running each project on a local machine:

- **Required Software**:  
  Python 3.9+, Node.js 18+, Redis, PostgreSQL, etc.

- **Instructions**:
  ```bash
  1. Clone the repository:
     git clone https://github.com/your/repo.git
  2. Navigate to the project folder:
     cd repo
  3. Create and activate a virtual environment:
     python3 -m venv venv && source venv/bin/activate
  4. Install dependencies:
     pip install -r requirements.txt
  5. Add a .env file:
     BOT_TOKEN=...
     DB_URL=...
  6. Run the bot:
     python src/bot.py
  ```

---

## ☁️ 3. Server Deployment

### 🔹 3.1 Servers
List the servers and what is hosted on each:

| Project        | IP / Host           | OS            | SSH User         |
|----------------|---------------------|---------------|------------------|
| Bot A          | 192.168.0.101       | Ubuntu 22.04  | `ubuntu`         |

- SSH Connection:
  ```bash
  ssh ubuntu@192.168.0.101
  ```

### 🔹 3.2 Deployment Method
- **Manual Deployment**:
  ```bash
  cd /var/www/botname
  git pull origin main
  source venv/bin/activate
  pm2 restart botname
  ```

- **systemd**:
  ```bash
  sudo systemctl restart botname
  sudo systemctl status botname
  ```

- **Docker**:
  ```bash
  docker-compose build
  docker-compose up -d
  ```

- **CI/CD** (if used): GitHub Actions, Jenkins, etc.

### 🔹 3.3 Service Management
- Example with PM2:
  ```bash
  pm2 start bot.py --name telegram-bot
  pm2 logs telegram-bot
  ```

- Cron jobs:
  ```bash
  crontab -l
  # Example:
  0 3 * * * /scripts/backup.sh
  ```

---

## 🔐 4. Variables and Access

### 🔹 4.1 Important Variables
| Variable       | Description                   |
|----------------|-------------------------------|
| BOT_TOKEN       | Telegram bot token            |
| DB_URL          | Database connection string    |
| API_KEY_X       | External API key              |

### 🔹 4.2 Where They Are Stored
- `.env` files: path to files
- Password managers: 1Password, Notion, Bitwarden, etc.

### 🔹 4.3 SSH Keys
- Path: `~/.ssh/id_rsa`
- If used for access — provide the public key

---

## 🖥️ 5. Servers and Environments

| Server IP       | Project Name       | Code Path                  |
|------------------|--------------------|-----------------------------|
| 192.168.0.101    | Payment Bot        | `/home/user/payment/`      |
| 192.168.0.102    | Reminder Service   | `/var/www/reminder/`       |

- Used ports / firewall / nginx proxy, etc.

---

## ⚙️ 6. Automation and Maintenance

### 🔹 6.1 Scripts
- `/scripts/backup.sh`: data backup
- `/scripts/deploy.sh`: auto-deploy

### 🔹 6.2 Cron Jobs
```bash
crontab -l
# Example:
0 2 * * * /scripts/backup.sh
```

### 🔹 6.3 Logs
- `pm2 logs botname`
- `/var/log/botname/errors.log`

---

## 🧯 7. Errors and Resolutions

| Error                          | Resolution                       |
|--------------------------------|----------------------------------|
| Bot crashes on network loss    | `pm2 restart botname`            |
| API not responding             | Retry / check logs               |
| Service won't start            | Check systemctl / logs           |

---

## 🧪 8. Testing

- How to test:
  ```bash
  Send to Telegram: "/start"
  Expected reply: "Welcome"
  ```

- Which scenarios to test manually

---

## 📝 9. Notes, Warnings, TODOs

- Bot B lacks retry logic — restart manually
- Incomplete branches: `dev-refactor`, `feature-x`
- TODO: rework image processing

---

## 👨‍💻 10. Instructions for My Laptop (if needed)

If any bots run **locally only**:
```bash
1. Open the laptop
2. Password: [provide securely]
3. Open Terminal
4. cd ~/Projects/bots/payment-bot
5. source venv/bin/activate
6. python bot.py
```

---

## 🔄 11. Final Steps

- [ ] Provide access to repositories
- [ ] Share SSH/passwords via manager
- [ ] Hand over CI/CD instructions (if any)
- [ ] Hold a meeting (online or offline) for demonstration
- [ ] Ensure the new developer can run everything

---

## 📌 Conclusion

> “This documentation is a living document. Update it upon any changes.”
