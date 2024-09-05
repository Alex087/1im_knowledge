# Attestation

## Enable/Disable RiskIndex

QER\CalculateRiskIndex

## Attestation structure

*Attestation types* include Attestation procedures and group them.

*Attestation procedures* determine base attestation object. For example Business role memberships (PersonInOrg object).
In the object set display attestation record on Portal. You can set displayed properties and columns for groupping. Value Related object indicates link to other table over set XObjectKey ($FK(UID_ADSAccount).XObjectKey$). Fields XObjectKey we set in Grouping columns.

*Compliance frameworks* for classification attestation policies, compliance rules, and company policies according to requirements.  

*Attestation policies* sets concrete conditions for attestation. You can set in Attestation policies Attestation procedure, schedule.  
Sets condition *Where* for select attestation objects in Attestation procedure. If we on Portal set condition for select attestation object then the condition save to *where* in Attestation policy.  
In Attestation policy sets Apprval Policy, which include Approval Workflow with steps for approval attestation.

|      |  |
| ----------- | ----------- |
| Additional approver  possible      |  Specifies whether a current attestor is allowed to instruct another employee as an attestor. This additional attestor has parallel authorization to make approvals for the current attestation case. The attestation case is not passed on to the next approval level until both attestors have made a decision.  This option can only be set for approval levels with a single, manual approval step.      |
| Approval can be delegated   | Specifies whether a current attestor can delegate the attestation to another person. This employee is added to the current approval step as the attestor. This employee then makes the approval decision instead of the attestor who made the delegation. This option can only be set for approval levels with a single, manual approval step.        |
| Approval by affected employee   | Specifies whether the employee who is affected by the approval decision can also approve it. If this option is set, employees to be attested can attest themselves. If this option is not set, use the QER - Attestation - PersonToAttestNoDecide configuration parameter to define whether the employees to be attested can attest themselves.
| Do not show in approval history  | Specifies whether or not the approval step should be displayed in the attestation history. For example, this behavior can be applied to approval steps with the CD - calculated approval procedure, which are used only for branching in the approval workflow. It It makes it easier to follow the attestation history.

https://support.oneidentity.com/technical-documents/identity-manager/8.1.2/attestation-administration-guide/18

## Attestation employee myself  

If employee wants attestation own in Workflow need check "Approval by affected employee"

## Recertifying existing users

**IMPORTANT:** Access to connected target systems may possibly be denied to One Identity Manager users as a result of recertification. You can configure this behavior to meet your company’s requirements. Read the following section thoroughly before you use the recertification function.
One Identity Manager provides an attestation policy for performing cyclical attestation of existing users allowing companies to regularly test and authorize employee master data stored in the One Identity Manager database. Cyclical attestation is triggered through a scheduled task. This resets the certification status for all employees stored in the database. One Identity Manager uses the same procedure for this as for attesting new users. The case is referred to as recertification.
Result of recertification  

  • Certified, activated employees who can access all entitlements assigned to them in One Identity Manager and the connected target systems.  
Company resources are inherited. Account definitions are assigned to internal employees.  
**OR**  
  • Denied and permanently deactivated employees.  
Disable employees cannot log in to One Identity Manager tools. Company resources are not inherited. Account definitions are not automatically assigned. User accounts associated with the employee are also locked or deleted. You can customize the behavior to meet your requirements.

From <https://support.oneidentity.com/technical-documents/identity-manager/8.1.2/attestation-administration-guide/38#TOPIC-1363650>

## Select employees according to conditions
Need change condition in Attestation policy

- [Attestation](#attestation)
  - [Enable/Disable RiskIndex](#enabledisable-riskindex)
  - [Attestation structure](#attestation-structure)
  - [Attestation employee myself](#attestation-employee-myself)
  - [Recertifying existing users](#recertifying-existing-users)
