**🔗 Integration Framework: Data Governance + Laserfiche Cloud**

**1\. Departmental Records Coordinators**

- **Role Expansion**: Each department's Records Coordinator becomes the operational steward of both policy and platform.
- **Responsibilities**:
  - Maintain and update the department's master classification and retention table.
  - Ensure metadata accuracy and lifecycle compliance.
  - Serve as liaison between policy enforcement and Laserfiche automation.

**2\. Laserfiche Form Architecture**

- **Form Design**:
  - Dropdowns for DocClass and Doctype sourced from the department's master table.
  - Auto-populated fields for Abbr, RMCutoff, RMRetention, RMSeries, ExpReq, and SecTag.
  - Optional fields for notes, attachments, and submitter identity.
- **Form Logic**:
  - Upon submission, workflows:
    - File the document into the correct repository path.
    - Apply metadata (classification, retention, security).
    - Trigger retention automation.

**3\. Master Table Schema (Example)**

| **DocClass** | **Doctype**        | **Abbr**  | **RMCutoff**                | **RMRetention** | **RMSeries** | **ExpReq** | **SecTag** |
| ------------ | ------------------ | --------- | --------------------------- | --------------- | ------------ | ---------- | ---------- |
| Contracts    | Amendment-Addendum | CNT-AMND  | TR03-Expiration-Date        | Keep 06 Years   | 7288         | Yes        | Restricted |
| Contracts    | Consulting         | CNT-CNSL  | TR03-Expiration-Date        | Keep 06 Years   | 7284         | Yes        | Restricted |
| Contracts    | Equipment Lease    | CNT-ELEAS | TR02-Closed-Settled-Expired | Keep 06 Years   | 7278         | Review     | Restricted |

- **Note**: This table should be maintained in a centralized governance repository (Laserfiche is preferred) and version-controlled. Each update should trigger a refresh of the Laserfiche Data Management List per Department.

**4\. Governance Alignment**

- **Policy Enforcement**:
  - Laserfiche workflows enforce retention schedules and classification rules as defined by the records Coordinator and approved by the Governance Committee.
  - Metadata tags ensure auditability and lifecycle traceability.
- **Oversight**:
  - CDO and City Clerk monitor compliance via Laserfiche audit reports.
  - City Auditor can run stewardship audits using metadata logs and workflow histories.

**5\. Operational Enhancements**

- **Training & SOPs for each Department**:
  - - A tailored SOP for using the Laserfiche Document Upload form.
      - A checklist for updating the master Classification table.