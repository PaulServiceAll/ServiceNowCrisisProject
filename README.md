# Emergency Disaster Assistance System

An application built on the ServiceNow platform designed to streamline and manage emergency disaster relief workflows. This solution provides an intuitive front-end portal experience for citizens to securely submit and track their relief requests while maintaining isolated, parameter-driven data access.

## 🚀 Key Features

*   **Disaster Request Ingestion:** Structured intake processing via custom Service Catalog Record Producers.
*   **Secure Citizen Lookup Gateway:** An unauthenticated gatekeeper interface that validates citizen identity tokens securely.
*   **Dynamic Data Isolation:** Seamlessly captures URL query parameters to strictly filter and display individual tracking records without exposing global table data.

---

## 🛠️ System Architecture & Configuration

The tracking subsystem utilizes an entirely configuration-driven, low-code architecture that avoids modifying global ServiceNow master scripts.

### 1. Verification Gateway (Record Producer)
The **Track My Request Gatekeeper** processes the user's initial tracking inquiry. Upon submission, it prevents the creation of a dummy record and formats an encrypted query string targeted at the dashboard:

```javascript
// Build a native URL query that tells the URL Widget exactly how to filter the database rows
var filterString = "u_citizen_name=" + producer.gatekeeper_name + "^u_citizen_email=" + producer.gatekeeper_email;

producer.portal_redirect = "?id=disaster_status_lookup&table=x_1834272_emergenc_disaster_assistance_request&filter=" + encodeURIComponent(filterString);

current.setAbortAction(true);
