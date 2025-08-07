# 📘 Windows Event Logs and the Event Viewer

Like other operating systems, **Windows OS** logs many activities for auditing, diagnostics, and security. These logs are stored in segregated log files, each representing a specific category of activity.

Windows offers a built-in utility called **Event Viewer** that provides a graphical interface for viewing and analyzing these logs.

---

## 📂 Types of Windows Event Logs

### 🟦 Application Log
- Logs information related to **user-level applications**.
- Includes:
  - Application errors
  - Warnings
  - Compatibility issues
  - Debugging messages

### 🟦 System Log
- Logs information from the **Windows OS itself**.
- Includes:
  - Driver issues
  - Hardware failures
  - System startup/shutdown
  - Service behavior and crashes

### 🟦 Security Log
- The most critical log in terms of **security**.
- Includes:
  - User authentication (logins/logouts)
  - User account changes
  - Group and policy changes

### 🟦 Other Logs
- Windows also includes logs for:
  - Setup
  - Forwarded Events
  - Custom application/service logs

---

## 🔍 Viewing Logs with Event Viewer

### ✅ Opening Event Viewer

1. Click the **Start** menu.
2. Type: `Event Viewer`
3. Press **Enter**.

You’ll see the **Event Viewer** window with a navigation pane on the left.

---

### 🗂 Navigation Areas

- **Windows Logs** section includes:
  - Application
  - Security
  - System
  - Setup
  - Forwarded Events

Clicking on a log type will display:
- A list of individual events
- Options to filter, search, or export events
- Detailed view of any selected log entry

---

## 📑 Understanding Event Log Fields

Each event contains important metadata. Key fields include:

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Description** | Detailed explanation of the event (what happened)                           |
| **Log Name**    | Indicates the category of the log file (e.g., Security, System)             |
| **Logged**      | Date and time the event occurred                                            |
| **Event ID**    | A unique identifier for the type of event (e.g., login success or failure)  |

---

## 🆔 Important Windows Event IDs

| Event ID | Description                                      |
|----------|--------------------------------------------------|
| 4624     | A user account successfully logged in            |
| 4625     | A user account failed to log in                  |
| 4634     | A user account successfully logged off           |
| 4720     | A user account was created                       |
| 4724     | An attempt was made to reset an account password |
| 4722     | A user account was enabled                       |
| 4725     | A user account was disabled                      |
| 4726     | A user account was deleted                       |

> 📝 You don’t need to memorize all IDs, but knowing the common ones is valuable in investigations.

---

## 🎯 Filtering Event Logs by Event ID

### 🔍 Using "Filter Current Log"

1. Open the Event Viewer.
2. Click on a log category (e.g., **Security**).
3. On the right panel, click **Filter Current Log**.
4. In the dialog box, enter an **Event ID** (e.g., `4624`).
5. Click **OK**.

You will now see only the events matching the filter. Double-click any of them to view full details.

---

## 📸 Example Workflow

- Open **Event Viewer**
- Go to **Security Logs**
- Filter for `4624`
- View all successful login attempts

This allows analysts or administrators to monitor login activity, detect anomalies, or investigate incidents.

---

## ✅ Summary

- Windows logs crucial system, application, and security events.
- **Event Viewer** provides a friendly GUI for viewing and filtering logs.
- **Event IDs** are powerful for filtering specific actions like logins or account changes.
- Use these tools for system auditing, threat detection, and troubleshooting.

> Remember: logs are only useful if regularly monitored or integrated into a SIEM system for alerts.

---
