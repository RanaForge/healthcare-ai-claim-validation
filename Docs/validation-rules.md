# Claim Validation Rules

The AI Agent validates healthcare claim requests using the extracted claim information and patient coverage data.

## Required Claim Information

The following fields are required:

- Claim Number
- Patient ID
- Hospital
- Service Date
- Treatment
- Claim Amount

## Validation Flow

1. Check whether all required claim information is available.
2. Validate the Patient ID against the patient coverage data.
3. Retrieve the patient's available coverage amount.
4. Compare the claim amount with the available coverage.
5. Determine the appropriate claim status.
6. Record the decision in the claim log.
7. Send an automated response when applicable.

## Decision Outcomes

### INCOMPLETE

If required claim information is missing, the claim is marked as:

`INCOMPLETE`

The system sends a response requesting the missing information.

### AUTO APPROVE

If the claim amount is within the patient's available coverage and all required information is valid, the claim can be:

`AUTO_APPROVE`

An automated approval response is generated.

### HUMAN REVIEW

If the claim requires an exception or additional decision-making, it is routed to:

`HUMAN_REVIEW`

A human reviewer makes the final decision.

## Human-in-the-Loop

Claims requiring human intervention are not automatically finalized. They are routed to a human reviewer for further assessment.
