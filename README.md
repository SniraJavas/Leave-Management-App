# Leave-Management-App
Build the front-end of a small Leave Management System for internal HR use. Employees can apply for leave, managers can view and approve them, and both can see leave balances.

Perfect! Here's an expanded and detailed **Employee Leave Management App Specification** with clearly defined **features, user stories, UI expectations, and testing scenarios** — just like you'd get in a real-world assessment or project.

---

# 📝 **Project Specification: Employee Leave Management App (Angular)**

---

## 📌 Project Title: `leave-manager`

## 👤 Users:

1. **Employee** (can apply for leave, view history and balances)
2. **Manager/Admin** (can view and approve/reject leaves)

---

## 🔧 Technologies:

* Angular 15+
* Angular Material (or TailwindCSS if preferred)
* Reactive Forms
* RxJS (`BehaviorSubject` or Signals)
* Routing + Guards
* LocalStorage or JSON server (for persistence)
* Jasmine + Karma (or Jest) for testing

---

## 🧱 Functional Requirements (User Stories):

---

### ✅ 1. **Apply for Leave**

```gherkin
As an employee,
I want to apply for leave using a form,
So that HR can review and approve my request.
```

**Form Fields:**

* Leave Type: Dropdown (Vacation, Sick, Study, Maternity, etc.)
* Start Date
* End Date
* Reason

**Validation Rules:**

* End Date > Start Date
* Max 20 days total
* Reason required

---

### ✅ 2. **View Leave History**

```gherkin
As an employee,
I want to see all my leave requests,
So I can track their status and history.
```

* Display leave list in a **table** with columns:

  * Date Range
  * Leave Type
  * Status (Pending/Approved/Rejected)
  * Action (View/Cancel if Pending)
* Add filters by leave type and status
* Add pagination or virtual scroll

---

### ✅ 3. **Leave Balance Summary**

```gherkin
As an employee,
I want to see how many leave days I have left,
So I can plan ahead.
```

* Show leave balances per leave type
* Use cards or bar chart (e.g., Angular Material + Chart.js)

---

### ✅ 4. **Approve or Reject Leave (Manager Only)**

```gherkin
As a manager,
I want to approve or reject employee leave requests,
So I can manage resources.
```

* Route: `/admin`
* List of all pending requests
* Click Approve/Reject (trigger confirmation dialog/snackbar)
* Update status instantly

---

### ✅ 5. **Authentication Simulation**

* Use a simple hardcoded switch in a service to simulate login

```ts
isManager = true; // simulate logged-in manager
```

* Use a route guard for `/admin`

---

## 🧪 Testing Scenarios (Minimum Coverage)

| Area           | What to Test | Test Type |
| -------------- | ------------ | --------- |
| **Leave Form** |              |           |

* Validation: missing required fields
* Invalid dates (end before start)
* Max duration exceeded
  \| Unit Tests |
  \| **Leave Service** |
* Adding a new leave
* Approving/rejecting leaves updates the status
* Get all leave history returns accurate data
  \| Unit Tests |
  \| **Leave History Component** |
* Renders correct number of rows
* Filters by type/status
  \| Integration Tests |
  \| **Navbar** |
* Navigation works (routerLink works correctly)
* Auth role shows/hides Admin link
  \| Unit or E2E |
  \| **Admin Panel** |
* Approve/Reject updates status correctly
* Snackbar/confirmation appears
  \| Integration Test |
  \| **Guard** |
* Non-managers cannot access `/admin`
  \| Unit Test |

---

## 🧰 Optional Enhancements

| Feature       | Description                                         |
| ------------- | --------------------------------------------------- |
| Local Storage | Persist leave data across refresh                   |
| JSON Server   | Simulate real API with `json-server`                |
| i18n          | Use `ngx-translate` for text                        |
| Search Filter | Search by reason text                               |
| Dialog Reuse  | Use Angular Material Dialog for both View & Confirm |

---

## 🎯 UX/UI Goals

* Use Angular Material or Tailwind to make it responsive
* Form field error messages shown clearly
* Toast/Snackbar notifications for actions
* Simple navbar with links:

  * Apply
  * History
  * Summary
  * Admin (if manager)

---

## 🧠 Bonus Challenge (Optional)

Create a **role-switcher** toggle (Employee ↔ Manager) in navbar to simulate auth context using a global service or Signal.

---

## ✅ Deliverable Checklist

| Feature                                | Done |
| -------------------------------------- | ---- |
| Leave Form (with validation)           | ☐    |
| Leave History (table, filters)         | ☐    |
| Leave Summary (cards or chart)         | ☐    |
| Admin Approval Panel                   | ☐    |
| Routing + Guard                        | ☐    |
| Form & Service Tests                   | ☐    |
| Nice UI with Material                  | ☐    |
| Optional: localStorage or mock backend | ☐    |

---
