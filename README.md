##Secure Identity Vault

The Secure Identity Vault is a client-side, offline-first application designed for the secure processing and anonymization of sensitive resident data (PII). It allows organizations to handle high-stakes information like Social Security Numbers (SSN) and Dates of Birth (DOB) without exposing raw data to cloud environments or internet-connected databases.

🎯 Purpose
This tool bridges the gap between restricted, offline local records and cloud-based management systems (such as AppSheet). By converting PII into a salted, irreversible cryptographic hash, the tool generates an anonymous Primary Key that can be safely used in the cloud. Even in the event of a cloud data breach, the stored identifiers remain mathematically impossible to reverse-engineer.

🛡️ Security Features
100% Offline Processing: The tool runs entirely in your browser's local memory (RAM). Zero data is sent over the internet.

One-Way Cryptography: Uses the SHA-256 algorithm to generate unique, anonymous identifiers.

AES-GCM Encryption: Master database files are encrypted using 256-bit AES encryption, requiring an Admin Key to unlock or modify.

Zero-Knowledge Design: The application does not log, track, or phone home. All data remains on your local machine or your organization's secure network drive.

⚙️ How It Works
Master Mode (In-Office)
Enter your Admin Encryption Key.

Load your encrypted Master_Database.csv file.

Add new resident records securely. The application will automatically re-encrypt and download the updated database for storage on your secure network drive.

Field Mode (Out-of-Office)
If no CSV is loaded, the tool operates in Field Mode.

New records are temporarily cached in your browser's local persistent storage (localStorage).

Syncing: Upon returning to the office, load your Master_Database.csv, and the tool will prompt you to automatically merge your queued, offline records into the master file.

🚀 Getting Started

https://github.com/mikelewis1971/Resident_Encoder
Open the Tool: Simply download open index.html in any modern web browser (Chrome, Firefox, Edge).

No Installation Required: Because the application is a standalone HTML/JavaScript file, it requires no backend server, database configuration, or internet connectivity to function.

⚠️ Important Usage Notes
Password Management: The Admin Encryption Key is the only way to unlock your database. Do not lose this key. If lost, the encrypted CSV files will become permanently unrecoverable.

Browser Storage: While the tool is offline, "Field Mode" data relies on your browser’s localStorage. Ensure you are using a secure, private, and authorized workstation to perform these tasks.

Backup: Regularly create redundant backups of your encrypted Master_Database.csv file on separate secure storage media.

📄 License
This project is intended for internal organizational use. Ensure all handling of PII adheres to your local data protection and privacy compliance regulations (e.g., HIPAA, GDPR, etc.).
