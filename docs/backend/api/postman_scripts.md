
# 🧪 Postman Automation Scripts

This guide contains the exact **Scripts** you need to add to your Postman Collection to automate testing.

---

## 📍 Where to Add These Scripts?

1.  **Select the Request** in Postman (e.g., `Admin / Auth / Login`).
2.  Click the **"Scripts"** tab (next to Params, Authorization).
3.  Choose **"Post-response"** (formerly called "Tests").
4.  **Paste the code** provided below into that window.
5.  **Save** the request.

---

## 🏗️ 1. Collection Variables Setup
First, define these variables in your Postman Collection "Variables" tab:

| Variable | Initial Value | Current Value |
|----------|--------------|---------------|
| `baseUrl` | `http://localhost:5000` | `http://localhost:5000` |
| `projectId` | | *(Leave Empty)* |
| `timelineId` | | *(Leave Empty)* |
| `leadId` | | *(Leave Empty)* |
| `adminEmail` | `admin@example.com` | `admin@example.com` |
| `adminPassword` | `your_secret_password` | `your_secret_password` |

---

## 🔐 2. Automation Logic (Scripts)

### A. Admin Login (POST /admin/auth/login)
**Goal:** Verify login succeeded and clear old variables.
**Location:** `Admin / Auth / Login` -> **Scripts** -> **Post-response**

```javascript
// 1. Check status
pm.test("Status is 200", function () {
    pm.response.to.have.status(200);
});

// 2. Clear old IDs (Cleanup for fresh run)
pm.collectionVariables.unset("projectId");
pm.collectionVariables.unset("timelineId");
pm.collectionVariables.unset("leadId");

console.log("Login successful. Old IDs cleared.");
```

---

### B. Create Project (POST /admin/projects)
**Goal:** Capture the new `_id` so we can update/delete it later.
**Location:** `Admin / Projects / Create Project` -> **Scripts** -> **Post-response**

```javascript
// 1. Check status
pm.test("Created successfully", function () {
    pm.response.to.have.status(201);
});

// 2. Capture ID
var jsonData = pm.response.json();
if (jsonData._id) {
    // Set the variable 'projectId' to the ID from the response
    pm.collectionVariables.set("projectId", jsonData._id);
    console.log("Captured Project ID: " + jsonData._id);
} else {
    console.error("No ID found in response!");
}
```

---

### C. Update Project (PUT /admin/projects/:id)
**Goal:** Use the captured ID dynamically.
**Location:** `Admin / Projects / Update Project` -> **Scripts** -> **Post-response**

**👉 IMPORTANT:** Update the Request URL to use the variable:
`{{baseUrl}}/admin/projects/{{projectId}}`

```javascript
// Test that update worked
pm.test("Update successful", function () {
    pm.response.to.have.status(200);
});
```

---

### D. Delete Project (DELETE /admin/projects/:id)
**Goal:** Clean up the resource.
**Location:** `Admin / Projects / Delete Project` -> **Scripts** -> **Post-response**

**👉 IMPORTANT:** Update the Request URL to use the variable:
`{{baseUrl}}/admin/projects/{{projectId}}`

```javascript
pm.test("Deleted successfully", function () {
    pm.response.to.have.status(200);
});
// Optional: Clear the variable after delete
pm.collectionVariables.unset("projectId");
```

---

### E. Create Timeline (POST /admin/timeline)
**Goal:** Capture the timeline `_id`.
**Location:** `Admin / Timeline / Create Timeline` -> **Scripts** -> **Post-response**

```javascript
pm.test("Created timeline item", function () {
    pm.response.to.have.status(201);
});

var jsonData = pm.response.json();
if (jsonData._id) {
    pm.collectionVariables.set("timelineId", jsonData._id);
    console.log("Captured Timeline ID: " + jsonData._id);
}
```

---

### F. Delete Timeline (DELETE /admin/timeline/:id)
**Location:** `Admin / Timeline / Delete Timeline` -> **Scripts** -> **Post-response**

**👉 IMPORTANT:** Update request URL: `{{baseUrl}}/admin/timeline/{{timelineId}}`

```javascript
pm.test("Deleted successfully", function () {
    pm.response.to.have.status(200);
});
```

---

## 🚀 How to Run "Regression Suite"
1. Make sure your local server is running.
2. Open Postman.
3. Click on the **Collection Name** (root folder).
4. Click **"Run Collection"**.
5. Ensure requests are ordered logically:
   - Login
   - Create Project
   - Update Project
   - Delete Project
   - ... repeat for Timeline ...
   - Logout
6. Hit **Run**.
7. Watch green tests pass! ✅
