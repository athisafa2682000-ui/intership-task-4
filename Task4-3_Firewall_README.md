# 🔥 Task 4-3: Configure and Test a Firewall on Windows

## 🎯 Objective
Configure and test **basic firewall rules** on Windows using the **Windows Firewall with Advanced Security** graphical user interface (GUI).  
This task helps understand how to allow or block specific network traffic using firewall settings.

---

## 🧰 Tools Used
- **Windows Defender Firewall (Control Panel)**
- **Windows Firewall with Advanced Security**
- **Command Prompt / PowerShell**
- **Telnet client** (for testing)

---

## 🪟 Main GUIs Used for Firewall Configuration

### 1. 🧱 **Windows Defender Firewall (Control Panel)**

**Purpose:**  
The general interface for configuring basic Windows Firewall settings.

**How to Access:**
1. Open the **Start Menu**.
2. Type **"Windows Defender Firewall"** and click to open it.

**What You Can Do:**
- Enable or disable the firewall for **Domain**, **Private**, or **Public** profiles.
- Turn notifications on/off for blocked programs.
- Access **Advanced settings** to create detailed inbound/outbound rules.

---

### 2. ⚙️ **Windows Firewall with Advanced Security**

**Purpose:**  
The advanced GUI for creating and managing detailed **inbound** and **outbound** rules.

**How to Access:**
1. From **Windows Defender Firewall (Control Panel)**, click on **"Advanced settings"** on the left pane.  
   OR  
2. Press `Win + R`, type:
   ```cmd
   wf.msc
   ```
   and press **Enter**.

**What You Can Do:**
- Create new **Inbound** or **Outbound** rules.
- Modify existing rules to block or allow specific ports or applications.
- Delete test rules after verifying them.
- Monitor firewall activity in the **Monitoring** section.

**GUI Sections Overview:**
| Section | Description |
|----------|-------------|
| **Inbound Rules** | Controls incoming network traffic to your computer. |
| **Outbound Rules** | Controls outgoing traffic from your computer. |
| **Connection Security Rules** | Manages how communication between computers is secured (less relevant for this task). |
| **Monitoring** | Displays active and applied firewall rules. |

---

### 3. 🌐 **Control Panel → Network and Sharing Center** (Indirectly Used)

**Purpose:**  
While not directly used to modify firewall rules, this GUI helps you manage **network profiles** which influence firewall behavior.

**How to Access:**
1. Open **Control Panel**.
2. Navigate to **Network and Internet → Network and Sharing Center**.

**What You Can Do:**
- View and change network settings.
- Check if your network connection is set as **Public** or **Private**, as firewall profiles depend on this.

---

## 🧪 Steps to Perform Using GUIs

### Step 1: Open Windows Firewall with Advanced Security
- Go to **Control Panel → Windows Defender Firewall → Advanced Settings**.
- This window is where you’ll create and manage detailed firewall rules.

---

### Step 2: Create a New Inbound Rule
1. In the **Windows Firewall with Advanced Security** window, select **Inbound Rules** (left panel).
2. Click **New Rule...** (right panel).
3. Choose **Port** → click **Next**.
4. Select **TCP** (or **UDP** if required) → enter **Port 23** (for Telnet).
5. Choose **Block the connection** → click **Next**.
6. Apply the rule to all profiles (**Domain**, **Private**, **Public**) → click **Next**.
7. Name the rule — e.g. **"Block Telnet Port 23"** → click **Finish**.

✅ You’ve successfully created a rule to **block inbound Telnet traffic**.

---

### Step 3: Test the Firewall Rule
1. Open **Command Prompt** or **PowerShell**.
2. Try connecting to port 23 using:
   ```powershell
   telnet 127.0.0.1 23
   ```
   or
   ```powershell
   Test-NetConnection -ComputerName 127.0.0.1 -Port 23
   ```
3. If the rule is working, the connection **should fail**.

🟢 Expected Result:  
```
TcpTestSucceeded : False
```

---

### Step 4: Remove the Rule
After testing:
1. Go back to **Windows Firewall with Advanced Security**.
2. Click **Inbound Rules**.
3. Find your test rule (e.g., *Block Telnet Port 23*).
4. Right-click and choose **Delete** to remove it.

✅ This restores the firewall to its previous state.

---

## 🧩 Key Points

- **Windows Firewall with Advanced Security** is the main GUI for detailed rule configuration.  
- **Windows Defender Firewall (Control Panel)** provides basic options and access to advanced settings.  
- **Network and Sharing Center** manages network profiles that influence which firewall rules apply.

---

## 🧠 Outcome
After completing this task, you should be able to:
- Open and navigate firewall configuration GUIs.
- Create inbound and outbound rules.
- Block and test network traffic on a specific port.
- Remove or modify rules as needed.
- Understand how Windows Firewall filters network traffic.

---

## 📸 Deliverables
Include in your report or GitHub repository:
- Screenshot of the **Inbound Rules** window showing your **Block Telnet Port 23** rule.
- Screenshot of **Test-NetConnection** or **telnet** output showing the connection blocked.
- Screenshot showing the rule deleted or disabled.

---

## 🗝️ Key Concepts
**Firewall configuration**, **network traffic filtering**, **ports**, **TCP/UDP**, **Windows Firewall profiles**, **inbound vs outbound rules**

---

**Author:** *Atheeka bi Safa*  
**Date:** *[Submission Date]*  
**Task:** *4-3: Configuring and Testing Firewall Rules (Windows)*
