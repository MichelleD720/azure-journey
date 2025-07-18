## ✅ **Azure Interview Project Checklist**

**Goal:** Set up a simulated enterprise IT environment
**Total time:** \~2 hours
**Videos:** (https://www.youtube.com/watch?v=OCiN37sjXuw&ab_channel=AndersJensen) (https://www.youtube.com/watch?v=_UuO52KgwGk&ab_channel=JohnSavill%27sTechnicalTraining) (https://www.youtube.com/watch?v=dkvrAYyYg9w&ab_channel=GuideToLearn)

---

### 🔹 **☁️ Step 1: Create a Resource Group**

* [ ] Go to **Azure Portal > Resource Groups**
* [ ] Click “Create”
* [ ] Name it something like `IT-Lab-RG`
* [ ] Choose your region (same for all other resources)

---

### 🔹 **🖥️ Step 2: Create a Windows 11 or Ubuntu Virtual Machine**

* [ ] Go to **Azure Portal > Virtual Machines**
* [ ] Click “Create VM”
* [ ] Choose:

  * OS: **Windows 11 Pro** (for Azure AD join) or **Ubuntu 22.04**
  * Size: **B1s** or **B2s**
  * Inbound port rules: allow **RDP (3389)** for Windows or **SSH (22)** for Linux
* [ ] Set username + password
* [ ] Enable **Boot Diagnostics**
* [ ] Click “Review + Create” → then “Create”

---

### 🔹 **🔐 Step 3: Connect VM to Azure AD (Windows only)**

* [ ] Log into your VM using RDP
* [ ] Go to **Settings > Accounts > Access work or school**
* [ ] Click **“Connect”** → Join to **Azure AD**
* [ ] Sign in with your Azure AD account (or create a user in Azure AD)

---

### 🔹 **🗃️ Step 4: Set Up Azure Storage (Blob or File)**

* [ ] Go to **Azure Portal > Storage Accounts**
* [ ] Click “Create”
* [ ] Name it something like `itlabstorage`
* [ ] Choose region and resource group
* [ ] Once created, go to **Containers** (for Blob) or **File shares**
* [ ] Create a new container: `systemlogs`
* [ ] Upload a sample `.txt` or `.log` file manually

✅ Bonus: Use `rclone` or `azcopy` from your Pi or PC to automate uploads

---

### 🔹 **👥 Step 5: Configure Access Control (IAM)**

* [ ] Go to your **Storage Account > Access Control (IAM)**
* [ ] Add a new role assignment:

  * Role: **Storage Blob Data Reader** or **Contributor**
  * Assign to: Yourself or a test Azure AD user

---

### 🔹 **📜 Optional: Create and Assign Azure AD Users**

* [ ] Go to **Azure Active Directory > Users**
* [ ] Create a new user `test.tech@yourdomain.onmicrosoft.com`
* [ ] Use this user to simulate logins or assign storage/VM access

---

### 🔹 **📈 Optional Add-On: Monitor Logs in Azure Monitor**

* [ ] Go to **Monitor > Logs**
* [ ] Create a **Log Analytics Workspace**
* [ ] Link your VM to the workspace (under VM > Monitoring > Insights)
* [ ] Review basic logs like boot time, CPU, and performance
