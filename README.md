# 📄 Convert PDF to HTML using PDF.co and Google Drive

## 📝 Overview  
This n8n workflow automates the process of converting a newly stored PDF file from Google Drive into an HTML file and saving it back to Google Drive. The workflow is triggered whenever a new PDF is uploaded to a specific folder, ensuring seamless conversion and storage without any manual intervention.

This workflow provides an efficient, automated solution for converting PDFs to HTML, eliminating the need for manual file handling and ensuring a smooth document transformation process. It is particularly useful for scenarios where PDFs need to be dynamically converted and stored in an organised manner for web usage, archiving, or further processing..  

### 🔹 Key Features:  
✅ **Automatically triggers** when a new PDF is uploaded.  
✅ **Converts PDF to HTML** using PDF.co API.  
✅ **Saves the converted HTML** file back to Google Drive.  
✅ **No manual intervention required**.  

This solution is ideal for **web usage, archiving, and document processing**, eliminating the need for manual PDF-to-HTML conversion.  

---

## ✅ Prerequisites  

Before setting up this workflow, ensure the following:  

1️⃣ **PDF.co API Key**  
   - Sign up at **[PDF.co](https://pdf.co/)** and obtain an API key for PDF-to-HTML conversion.  

2️⃣ **Google Drive Authentication**  
   - Ensure proper authentication is configured for **Google Drive in n8n**.  

---

## ⚙️ Customization Options  

🔹 Modify the API request to **convert PDFs into other formats** like **Text, CSV, or XML**.  
🔹 Extend the **IF Node** to **reject files based on size or other properties**.  
🔹 Send a **notification** once the conversion is complete via **Email or Telegram Node**.  

---

## 🔄 Workflow Steps  

### **Step 1: Google Drive Trigger (Watch for New Files)**
📌 **Action**: Detects when a new file is uploaded to a specific Google Drive folder.  

- Add a **Google Drive Trigger Node** in n8n.  
- Authenticate using your **Google OAuth2 credentials**.  
- Select the folder to **monitor for new files**.  
- Set the trigger to **activate when a new file is added**.  
- Click **"Execute Node"** to test.  
- Click **"Save"**.  

---

### **Step 2: IF Node (Check if File is a PDF)**
📌 **Action**: Ensures only PDF files proceed to the conversion step.  

- Add an **IF Node** in n8n.  
- Add a condition to **check if the file extension is `.pdf`**.  
  - ✅ **If true** → Proceed to the next step.  
  - ❌ **If false** → Stop the workflow.  
- Click **"Execute Node"** to test.  
- Click **"Save"**.  

---

### **Step 3: HTTP Request Node (Convert PDF to HTML)**
📌 **Action**: Sends the PDF file to PDF.co for conversion.  

- Add an **HTTP Request Node** in n8n.  
- Set the **Method** to `POST`.  
- Enter the **PDF.co API endpoint** for PDF-to-HTML conversion.  
- Add the **API Key** in the Headers.  
- Send the **binary PDF data** as the request body.  
- Click **"Execute Node"** to test.  
- Click **"Save"**.  

---

### **Step 4: Function Node (Convert Response to Binary)**
📌 **Action**: Transforms the API response into a binary file.  

- Add a **Function Node** in n8n.  
- Write a **JavaScript function** to process the API response.  
- Click **"Execute Node"** to test.  
- Click **"Save"**.  

---

### **Step 5: Google Drive Node (Save Converted HTML File)**
📌 **Action**: Uploads the converted HTML file to Google Drive.  

- Add a **Google Drive Node** in n8n.  
- Select **"Upload File"** as the action.  
- Authenticate using your **Google Account**.  
- Choose the **destination folder** for storing the HTML file.  
- Map the **binary data** from the Function Node.  
- Click **"Execute Node"** to test.  
- Click **"Save"**.  

---

### **Step 6: Connect & Test the Workflow**  
✅ **Link the nodes** in this order:  
**Google Drive Trigger → IF Node → HTTP Request → Function Node → Google Drive Upload**  

✅ **Run the workflow manually**.  
✅ **Upload a test PDF to Google Drive**.  
✅ **Check Google Drive for the converted HTML file**.  

---

## 📌 Outcome  

Once set up, this workflow will:  
✅ **Automatically convert PDFs** to HTML without manual intervention.  
✅ **Store the converted file** back into Google Drive for easy access.  
✅ **Ensure a streamlined document transformation process**.  

---

## 🚀 About WeblineIndia  

This workflow is built by the **AI development team at WeblineIndia**.  

📌 **Who are we?**  
✔ **25+ years** of software development experience.  
✔ **3,500+ successful projects** delivered across **25+ countries**.  
✔ Expertise in **no-code automation, AI systems, and enterprise solutions**.  

📩 **Need a custom workflow?** Hire our AI developers to build **tailored automation solutions** for your business!  
