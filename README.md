# Emergency Disaster Assistance Application (ServiceNow Scoped App)

## 🛠️ Architecture & Technical Overview
A fully encapsulated, custom ServiceNow application built in a scoped environment designed to manage civilian humanitarian aid requests dynamically during emergency responses. 

### Key Technical Implementations:
* **Custom Data Modeling:** Created custom tables extending the core `Task` framework, leveraging structural field mapping and role-based access controls.
* **Overridden Sequence Engines:** Configured localized Number Maintenance rules (`ERXXXXXXX`) to safely decouple tracking protocols from native incident lifecycles.
* **Client-Side Dynamics:** Developed targeted UI Policies to enforce runtime conditional rendering and mandatory fields (`Funding Amount Requested`) based on localized inputs.
* **Server-Side Gatekeepers:** Authored a robust `Before Update` Business Rule tracking previous state differentials to strictly enforce workflow validation policies.
* **Automated Stakeholder Loops:** Designed HTML/CSS notification engines featuring contextual dynamic scripting variables for real-time stakeholder escalation.
