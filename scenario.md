Absolutely! Here’s a **more polished and readable version** of the Linux interview Q\&A, with a clear, professional tone that flows well in an actual interview setting. Each answer is concise, structured, and easy to follow — great for both verbal and written formats.

---

## ✅ **Linux Admin Interview: Sample Questions & Answers**

---

### 🔹 **1. A server is running slowly. How do you troubleshoot it?**

**Answer:**

> I’d begin by checking the system’s overall load using `uptime`, then monitor real-time resource usage with tools like `top` or `htop`. I’d also look into I/O performance using `iostat`, and network activity with `iftop` or `nload`. Once I identify the bottleneck—whether it’s CPU, memory, disk, or network—I’ll investigate the specific processes or services responsible.

**Key Commands:**

```bash
top
vmstat 1
iostat -xz 1
```

---

### 🔹 **2. A user's home directory is consuming too much root partition space. What do you do?**

**Answer:**

> First, I’d analyze disk usage with `du` to see which files are using the most space. If necessary, I’d move the user’s home directory to another partition with more space and create a symbolic link so that user services remain unaffected.

**Key Commands:**

```bash
du -sh /home/username/*
mv /home/username /mnt/data/username
ln -s /mnt/data/username /home/username
```

---

### 🔹 **3. How would you secure a web server from common vulnerabilities?**

**Answer:**

> I take a layered security approach: applying security updates regularly, enforcing HTTPS with SSL, setting strict file permissions, disabling directory listings, and using a firewall like UFW. I also deploy tools like Fail2Ban to mitigate brute-force attempts.

**Key Commands:**

```bash
ufw allow 'Nginx Full'
chmod -R 640 /etc/nginx
apt update && apt upgrade
```

---

### 🔹 **4. Your SSH server is being brute-forced. What steps do you take?**

**Answer:**

> I’d mitigate this by changing the default SSH port, disabling root login, enforcing key-based authentication, and installing Fail2Ban to block repeated login attempts.

**Key Commands:**

```bash
vi /etc/ssh/sshd_config  # Change port, disable root login
systemctl restart ssh
apt install fail2ban
```

---

### 🔹 **5. How would you automate backups to a remote server?**

**Answer:**

> I’d use `rsync` over SSH for efficient incremental backups, and schedule it using a cron job. I’d also set up SSH key authentication for automation.

**Key Commands:**

```bash
rsync -avz /data user@remote:/backup/
crontab -e
# Add: 0 2 * * * rsync -avz /data user@remote:/backup/
```

---

### 🔹 **6. A critical service crashed and won’t restart. What do you do?**

**Answer:**

> I’d check the service status using `systemctl` and inspect logs via `journalctl`. Then I’d troubleshoot configuration files or permissions based on the errors and try restarting the service.

**Key Commands:**

```bash
systemctl status servicename
journalctl -u servicename
systemctl restart servicename
```

---

### 🔹 **7. The server time is incorrect. How do you fix it?**

**Answer:**

> I’d verify the time settings using `timedatectl`, then install and start a time sync service like `chrony` to correct the server time.

**Key Commands:**

```bash
timedatectl
apt install chrony
systemctl enable --now chronyd
```

---

### 🔹 **8. How do you create a user with no shell access?**

**Answer:**

> I’d use the `useradd` command with `/usr/sbin/nologin` as the shell to prevent the user from logging into the system.

**Key Command:**

```bash
useradd -M -s /usr/sbin/nologin newuser
```

---

### 🔹 **9. The server is running out of memory and swapping heavily. What actions would you take?**

**Answer:**

> I’d identify high-memory processes using `top` or `ps`, kill any unnecessary ones, and tune the swappiness value to reduce dependency on swap. For a long-term fix, I’d consider upgrading memory or optimizing services.

**Key Commands:**

```bash
top
free -h
kill -9 <pid>
sysctl vm.swappiness=10
```

---

### 🔹 **10. How would you limit a user’s disk usage?**

**Answer:**

> I’d configure disk quotas by enabling `usrquota` on the relevant filesystem, then set quota limits for the user using `edquota`.

**Key Commands:**

```bash
mount -o remount,usrquota /home
quotacheck -cum /home
quotaon /home
edquota username
```

---

### 🔹 **11. How do you make sure a service starts on boot?**

**Answer:**

> I’d simply enable it using `systemctl`.

**Key Command:**

```bash
systemctl enable servicename
```

---

### 🔹 **12. Your web server shows a 502 Bad Gateway error. How do you troubleshoot it?**

**Answer:**

> This usually indicates the backend service is down or misconfigured. I’d check if the backend (like PHP-FPM or a Node.js app) is running, inspect web server logs, and verify the port/socket configuration.

**Key Commands:**

```bash
systemctl status php-fpm  # or relevant backend
tail -f /var/log/nginx/error.log
```

---

### 🔹 **13. How would you schedule a cleanup of temporary files?**

**Answer:**

> I’d use a cron job to regularly delete old files from the `/tmp` directory, for example, those older than 7 days.

**Key Command:**

```bash
crontab -e
# Add: 0 3 * * * find /tmp -type f -mtime +7 -delete
```

---

### 🔹 **14. How do you compile and install software from source?**

**Answer:**

> I’d install build tools, extract the source code, then use the standard `./configure`, `make`, and `make install` process.

**Key Commands:**

```bash
apt install build-essential
tar -xzf package.tar.gz
cd package
./configure
make
sudo make install
```

---

### 🔹 **15. How would you find and kill all processes started by a specific user?**

**Answer:**

> I’d use `pkill` to kill all processes by that user, or combine `ps` with `kill` if I need more control.

**Key Commands:**

```bash
pkill -u username
# Or more detailed:
ps -u username -o pid= | xargs kill -9
```

---

Would you like this in a downloadable **PDF or DOCX format** for printing or preparation?
