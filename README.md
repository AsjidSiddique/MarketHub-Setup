
# 🛍️ MarketHub Desktop Setup

**MarketHub** is a fully offline desktop marketplace app developed by **Asjad Siddique** using **Java Swing + Portable MySQL (No XAMPP Required)**.  
It supports auto-database import, data backup, and runs as a single `.exe` file — making deployment simple for end users.

---

## 📦 Features

- ✅ Java Swing GUI
- 🔐 Admin/User Login & Password Reset
- 🛍️ Product Management (Add/View/Search)
- 💰 Transactions & Sales History
- 🗃️ Built-in MySQL Server (No install needed)
- 📦 Auto-import `markethub.sql` on first run
- 📤 One-click `.sql` + `.csv` data export
- 🖥️ Portable `.exe` setup via Launch4j

---

## 📂 Folder Structure

```
MarketHub-Setup/
├── mysql/                   # Embedded MySQL server
│   ├── bin/
│   └── data/
├── markethub.sql            # Initial database schema
├── MarketHub.exe            # Final app (launches DB + GUI)
├── MarketHub.jar            # Java source app (optional)
├── setup.bat                # Start DB and app
├── backup.bat               # Backup current DB to .sql
├── README.md                # This file
```

---

## 🚀 First-Time Use

1. 📦 **Download** the full folder (exe or Git clone).
2. 🔁 **Double-click `MarketHub.exe`** — it will:
   - Start embedded MySQL server
   - Auto-import `markethub.sql` if DB doesn't exist
   - Launch the app

3. ✅ You're done! No MySQL or Java or XAMPP needed.

---

## 🔐 Default Admin Login

```
Username: admin  
Password: admin
```

---

## 💾 Backup Script (`backup.bat`)

Exports the current DB to `markethub.sql`:

```bat
@echo off
set BACKUP_FILE=markethub.sql
mysql\bin\mysqldump.exe -u root markethub > %BACKUP_FILE%
```

---

## 📊 Export to CSV

Add this to `backup.bat` to export `products` table:

```bat
mysql\bin\mysql.exe -u root -e "SELECT * FROM products INTO OUTFILE 'products.csv' FIELDS TERMINATED BY ',' ENCLOSED BY '"' LINES TERMINATED BY '\n';" markethub
```

📝 Requires MySQL file privileges + write access.

---

## 🛠 JAR to EXE Note

- Built with **Launch4j**
- Windows may show **“Unknown Publisher”** warning

---

## 📥 GitHub Hosting

I upload this setup to GitHub:

- Max file upload = **2 GB**
- As `.exe` is large (e.g., 378 MB), it can be uploaded directly via:
  - GitHub Desktop
  - Git LFS (for large files)
  - Or compress and upload `.exe` archive

---

## ✍️ Author Info

```
👤 Asjad Siddique  
📞 +92 318 4485469  
📧 asjadsaddique4@gmail.com
📍 Pakistan  
```

---

## 📘 License

Free for academic, demo, and internal business use.  
Not for resale without author permission.

---

## 📌 Download Link 

👉 [Download MarketHub EXE](https://github.com/AsjidSiddique/MarketHub-Setup/releases)

---

> 💬 Need help? Message me on WhatsApp or GitHub.
