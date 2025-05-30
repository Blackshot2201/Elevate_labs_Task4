# Elevate_labs_Task4
# 🔐 Task 4: Setup and Use a Firewall on Linux

## 🎯 Objective

To install, configure, and test basic firewall rules on Kali Linux using **UFW (Uncomplicated Firewall)**. This task focuses on enabling the firewall, allowing and denying specific ports (22 and 23), verifying the changes, and cleaning up after testing.

---

## 🛠️ Tools Used

* **Operating System**: Kali Linux
* **Firewall**: UFW (Uncomplicated Firewall)
* **Services/Ports Involved**:

  * **Port 23 (Telnet)** – to be **blocked**
  * **Port 22 (SSH)** – to be **allowed**
* **Command Line Utilities**: `ufw`, `telnet`, `apt`

---

## 📸 Screenshots Included

All screenshots captured during the process are shown below along with each step.

---

## 🧪 Step-by-Step Procedure

---

### 1️⃣ UFW Not Found Initially

Tried checking UFW status, but got a "command not found" error.

```bash
sudo ufw status
```

### 2️⃣ Install UFW

Installed UFW using the APT package manager.

```
sudo apt install ufw
```

### 3️⃣ Enable UFW

Enabled the firewall so it becomes active and starts on boot.

```
sudo ufw enable
```

### 4️⃣ Check Firewall Status

Verified whether UFW was active after enabling it.

```
sudo ufw status
```

### 5️⃣ Add Firewall Rules

Blocked **Telnet (port 23)** and allowed **SSH (port 22)** using UFW rules.

```
sudo ufw deny 23 sudo ufw allow 22
```

6️⃣ List Active Rules with Numbers

Displayed all current firewall rules with indexes using:

```
sudo ufw status numbered
```

### 7️⃣ Test Telnet Access on Blocked Port

Tested connection to port 23 using Telnet. Connection was refused, confirming the rule worked.

```
telnet localhost 23
```

### 8️⃣ Delete Firewall Rules (Cleanup)

Removed the rules added earlier for port 23 and 22.

```
sudo ufw delete deny 23 sudo ufw delete allow 22
```

### 9️⃣ Disable UFW

Disabled UFW and stopped it from starting on boot.

```
sudo ufw disable
```
