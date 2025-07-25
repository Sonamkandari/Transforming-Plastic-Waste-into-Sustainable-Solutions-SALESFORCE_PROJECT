# 🗃️ Data Management - Re Plastic Innovations

This document outlines the setup and configuration of custom Salesforce objects, fields, roles, and app settings related to Re Plastic Innovations.

---

## 📦 Custom Objects & Fields

### 1. **Re Plastic Innovations Plastic Waste**

#### Step-by-step field creation:

1. Create a new field and select the data type  
   ![Step 1](https://github.com/user-attachments/assets/c27a5f1f-f7ae-4ba4-9069-7be75a55f2ea)

2. Enter details: Field Name and API Name  
   ![Step 2](https://github.com/user-attachments/assets/0c7ee8d0-bea9-4f0f-be84-0ca917adc509)

3. Set field-level security  
   ![Step 3](https://github.com/user-attachments/assets/85d22cf9-8e61-4d7c-a77a-042389f475cc)

4. Add the field to relevant page layouts  
   ![Step 4](https://github.com/user-attachments/assets/8335dd14-e5bf-49c1-be56-998393b8cf63)

#### Additional Fields Created:
![All Fields](https://github.com/user-attachments/assets/ea8235cb-c8c5-489d-b209-80d7813ba5b3)

---

### 2. **Re Plastic Innovations Recycling Center**

#### Field creation process:

1. Create a new field and select the data type  
   ![Step 1](https://github.com/user-attachments/assets/0788f3a2-2600-4f1a-a054-2ba4715db6b8)

2. Enter Field Name and API Name  
   ![Step 2](https://github.com/user-attachments/assets/3b1cacc7-db1b-4dff-a0ec-055d72a2d723)

3. Set field-level security  
   ![Step 3](https://github.com/user-attachments/assets/bda9fced-bd9a-4524-8925-462ba05b4220)

4. Add to page layouts  
   ![Step 4](https://github.com/user-attachments/assets/e7968bc7-26e1-49f1-87cc-575a46bc484b)

#### Additional Fields Created:
![All Fields](https://github.com/user-attachments/assets/0943c672-13bc-4fa7-a405-d2e552930115)

---

### 3. **Re Plastic Innovations Recycled Product**

- Created all necessary fields  
  ![Fields](https://github.com/user-attachments/assets/992fdaca-083b-4112-b26d-3324724d51ac)

---

### 4. **Re Plastic Innovations Order**

- Created all necessary fields  
  ![Fields](https://github.com/user-attachments/assets/8ec8730c-6c21-43e1-8237-1ddc57167c06)

---

### 5. **Re Plastic Innovations Restock Request**

- Created all necessary fields  
  ![Fields](https://github.com/user-attachments/assets/5f8b99bb-ded9-43a0-bf2b-2ffe69765056)

---

## 📁 Tabs

Custom tabs were created for each object to enable easy navigation and accessibility within the Salesforce app.

---

## ⚙️ App Manager Setup

**App Name:** Re Plastic Innovations  
**Developer Name:** *(auto-populated)*  
**Description:** Provide a clear and meaningful description  
**Image:** Optional  
**Primary Color Hex:** Use default  

![App Manager](https://github.com/user-attachments/assets/ec99525f-aeea-4fa8-a5fe-1652917bf356)

### Navigation Items Added:
![Navigation](https://github.com/user-attachments/assets/83b1efff-592d-40b0-ad4c-448c0f464c87)

---

## 🏷️ Data Management Fields

Fields created:

- **Weight**
- **Type**
- **Re Plastic Innovations Recycling Center** (lookup field)

For the objects previously listed.

![Field Overview](https://github.com/user-attachments/assets/34effb82-7c2c-4612-ae2a-d67f4ad58d69)

---

## 🔐 Data Security - Roles

Defined role hierarchy:

1. **Sales Representative** reports to **CEO**
2. **Warehouse Supervisor** reports to **Sales Representative**

![Role Hierarchy 1](https://github.com/user-attachments/assets/c445dca1-0568-4740-94d0-5ef3e335a704)  
![Role Hierarchy 2](https://github.com/user-attachments/assets/17cd301d-4208-42aa-8681-44705afd61c2)

---

## 🔐 Data Security – Profiles

The following profiles were created and configured to manage object-level access permissions:

![Profiles](https://github.com/user-attachments/assets/8eba060f-0209-4d69-8adc-e997522b0e37)

After creating the profiles, access was granted to relevant objects as follows:

---

### 👤 **Profile: Platform 1**

- **Re Plastic Innovations Plastic Waste** – Read / Create  
- **Re Plastic Innovations Restock Request** – Read-Only

---

### 👤 **Profile: Platform 2**

- **Re Plastic Innovations Order** – Read / Create  
- **Account** – Read / Create  
- **Re Plastic Innovations Plastic Waste** – Read-Only  
- **Re Plastic Innovations Recycled Product** – Read-Only

---

### 👤 **Profile: Platform 3**

- **All Custom Objects** – Read / Create / Edit  
  (Full access to all Re Plastic Innovations custom objects)

---

# 📘 RePlastic Innovations – Salesforce Configuration

---

## 🔐 Data Security – Users

- Created **three users**:

  ![Users Creation](https://github.com/user-attachments/assets/65c99b2c-8d10-4576-8df9-09ff422d053b)

---

## 🛡️ Data Security – Record-Level Sharing

- Setup Organization-Wide Defaults as **Private**.
- Configured sharing rules to grant record access:

  ![Sharing Settings Overview](https://github.com/user-attachments/assets/dea14fa7-20ea-4fa7-9171-e540fff3f6b2)

### Sharing Rules:

1. **Recycling Manager access to Plastic Waste records**
   - Only the *Recycling Manager* role can access the `Re_Plastic_Innovations_Plastic_Waste__c` collection.

2. **Create Owner-Based Sharing Rule**
   - Navigate via **Steel Production object** → *New Sharing Rule*
   
   ![New Sharing Rule Setup](https://github.com/user-attachments/assets/aaa1b02e-aa3b-4af9-896b-e885b212704b)

3. **Additional Sharing Rules:**

   - **Sales Representative** gets **Read** access to the `Re_Plastic_Innovations_Recycled_Product__c` object  
     (shared: CEO → Sales Rep)
   - **Warehouse Supervisor** gets **Read** access to the `Re_Plastic_Innovations_Restock_Request__c` object  
     (shared: Sales Rep → Warehouse Supervisor)

   ![More Sharing Rules](https://github.com/user-attachments/assets/05810f82-fb4e-40e7-949d-4a54622edb0b)

---

## ⚙️ Data Configuration & Testing

### 🧮 Formula Field Testing

- ![Formula Testing 1](https://github.com/user-attachments/assets/c997bda4-2f06-40a2-af8c-61f752f5c2c9)  
- ![Formula Testing 2](https://github.com/user-attachments/assets/fd9c4189-291e-4eee-bad3-30e248644c42)

---

### 🛡️ Validation Rules

- **Quantity Not Zero Rule**  
  Prevents orders with a quantity of 0.
  ![Validation Rule Quantity](https://github.com/user-attachments/assets/ee27fdac-5488-46bc-be70-a2128f5f5ad8)

- **Plastic Waste Rule on Re_Plastic_Innovations__c**
  ![Plastic Waste Validation](https://github.com/user-attachments/assets/478681ad-4e17-4f60-8ebc-d8b4721ced92)

---

## 🔁 Process Automation Using Flows

- Automated stock flow creation:
  ![Flow Screenshot 1](https://github.com/user-attachments/assets/1a6ca1d2-98be-4236-b416-b4c92f63563f)

- Additional flow steps:
  ![Flow Screenshot 2](https://github.com/user-attachments/assets/1f189266-5378-43e4-9d8e-28d3c4d6ee61)
  ![Flow Screenshot 3](https://github.com/user-attachments/assets/33941032-d723-47ad-a9a5-242a5705d63b)

### ✅ Completed Flow

- ![Completed Flow](https://github.com/user-attachments/assets/7a647458-29c7-4c2b-a63c-36804d2059f7)

### 🧪 Flow Testing

- Created a test record to trigger the flow and validated with timestamp:
  ![Flow Testing](https://github.com/user-attachments/assets/a215d745-cb29-4df4-b8b7-5e83cd13ab30)

---

## 💻 Apex Code

### 🔧 Apex Class: `InventoryManager`

- Handles:
  - Reducing stock after an order
  - Creating restock requests
  - Processing approved restocks

![InventoryManager Code](https://github.com/user-attachments/assets/04cd9ac4-ddbb-477f-9386-2ffe2d2524fb)
![InventoryManager Snippet](https://github.com/user-attachments/assets/99c6ab83-942c-4e44-a6d3-6b724f5d579a)

---

### 🔄 Apex Triggers

#### 📦 Trigger: `UpdateStockAfterOrder`
- Object: `Re_Plastic_Innovations_Order__c`
- Purpose: Reduces stock and creates restock request if needed.
![Trigger Order](https://github.com/user-attachments/assets/3dba82b3-746a-4fd0-8298-195cc27550ca)

#### ✅ Trigger: `UpdateStockAfterRestockApproval`
- Object: `Re_Plastic_Innovations_Restock_Request__c`
- Purpose: When a restock request is approved, the stock is updated automatically.
![Trigger Restock](https://github.com/user-attachments/assets/68a41125-037e-401d-8aff-56f74446e50e)

---

## 📧 Email Notification

- Created a class to **send email to the Warehouse Manager** when stock is successfully updated.
- Called this logic from within the trigger.

![Email Logic](https://github.com/user-attachments/assets/d280a446-e45a-48ca-99f0-ba46f2879661)

---

---












