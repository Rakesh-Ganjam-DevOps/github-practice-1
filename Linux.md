Here’s a list of **most commonly used Linux commands by DevOps engineers**, along with **real-time scenarios** where each command is typically used. These cover system administration, automation, deployment, monitoring, and troubleshooting.

---

### 🔧 **System and Server Management**

| **Command**     | **Scenario**                                                                       |
| --------------- | ---------------------------------------------------------------------------------- |
| `ssh user@host` | Access remote servers for deployment or debugging.                                 |
| `top` / `htop`  | Monitor real-time CPU and memory usage during high-load situations.                |
| `free -m`       | Check available memory when troubleshooting slow applications.                     |
| `uptime`        | Check server load averages and how long the system has been running.               |
| `whoami`        | Confirm the current logged-in user, useful in scripts with user-based permissions. |
| `hostname`      | Get or set the server’s hostname in a cluster environment.                         |

---

### 📦 **Package Management**

| **Command**                    | **Scenario**                                                   |
| ------------------------------ | -------------------------------------------------------------- |
| `apt update && apt upgrade -y` | Update packages on Ubuntu-based servers before a release.      |
| `yum install nginx`            | Install a required package like NGINX on CentOS-based systems. |
| `dpkg -i package.deb`          | Install a .deb file manually during CI/CD automation.          |

---

### 📁 **File and Directory Management**

| **Command**                  | **Scenario**                                                                         |
| ---------------------------- | ------------------------------------------------------------------------------------ |
| `ls -lAh`                    | View permissions and sizes of files in a directory when debugging permission issues. |
| `cd /var/log`                | Navigate to log directory to check system or application logs.                       |
| `cp -r /source /destination` | Copy configuration files across directories before restarting services.              |
| `mv config.old config.bak`   | Rename config files as a backup during upgrades.                                     |
| `rm -rf /tmp/cache/*`        | Clear cache directory to resolve storage or space issues.                            |

---

### 📄 **Log and Text Processing**

| **Command**                             | **Scenario**                                                |
| --------------------------------------- | ----------------------------------------------------------- |
| `tail -f /var/log/syslog`               | Monitor live logs while restarting a service.               |
| `cat /etc/nginx/nginx.conf`             | View contents of the NGINX config file to validate changes. |
| `grep "error" /var/log/nginx/error.log` | Search for specific error strings in log files.             |
| `awk '{print $1}' access.log`           | Extract IPs from access logs for analytics or banning.      |
| `sed -i 's/old/new/g' config.yml`       | Replace configuration values during a deployment script.    |

---

### ⚙️ **Process and Service Management**

| **Command**               | **Scenario**                                           |                                                     |
| ------------------------- | ------------------------------------------------------ | --------------------------------------------------- |
| \`ps aux                  | grep java\`                                            | Find a running Java process to check memory or PID. |
| `kill -9 PID`             | Forcefully terminate a hung process.                   |                                                     |
| `systemctl restart nginx` | Restart services after deploying new code.             |                                                     |
| `systemctl status docker` | Check Docker service status if containers won’t start. |                                                     |

---

### 🐳 **Docker & Containers**

| **Command**                                | **Scenario**                                             |
| ------------------------------------------ | -------------------------------------------------------- |
| `docker ps`                                | List running containers to ensure the app is up.         |
| `docker logs <container_id>`               | Debug issues inside a containerized service.             |
| `docker-compose up -d`                     | Start a multi-container application stack in background. |
| `docker exec -it <container_id> /bin/bash` | Enter into a running container for debugging.            |

---

### 🕸️ **Networking and Connectivity**

| **Command**                  | **Scenario**                                                 |
| ---------------------------- | ------------------------------------------------------------ |
| `ping google.com`            | Check basic network connectivity from the server.            |
| `curl -I http://example.com` | Fetch HTTP headers to check if a service is up.              |
| `netstat -tuln`              | Check listening ports and protocols on the server.           |
| `ss -ltnp`                   | View detailed info about listening TCP ports with processes. |
| `traceroute <host>`          | Diagnose network latency or routing issues.                  |

---

### 🔐 **Permissions and Ownership**

| **Command**                         | **Scenario**                                         |
| ----------------------------------- | ---------------------------------------------------- |
| `chmod +x deploy.sh`                | Make deployment scripts executable.                  |
| `chown -R ubuntu:www-data /var/www` | Set ownership to allow the web server to read/write. |
| `ls -la`                            | Verify file permissions during troubleshooting.      |

---

### 📦 **CI/CD and Automation Support**

| **Command**        | **Scenario**                                                       |
| ------------------ | ------------------------------------------------------------------ |
| `crontab -e`       | Set up scheduled jobs like log rotation or backups.                |
| `env`              | Print environment variables during troubleshooting CI/CD failures. |
| `export VAR=value` | Set environment variables for a script or session.                 |

---

### 🧪 **Disk and File System**

| **Command**        | **Scenario**                                        |
| ------------------ | --------------------------------------------------- |
| `df -h`            | Check disk usage when the server runs out of space. |
| `du -sh *`         | Find large directories that are taking up space.    |
| `mount` / `umount` | Attach or detach volumes in cloud environments.     |

---

Would you like me to turn this into a **PDF cheatsheet** or **interactive table**?
