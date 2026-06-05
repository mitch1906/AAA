AAA Life Insurance – Automation Engineer Take-Home Assessment

Platform:
This solution was developed using UiPath REFramework. I chose REFramework because it provides a structured enterprise automation pattern with separate Init, Get Transaction, Process, and End Process states, along with built-in exception handling and transaction management.

Solution Overview:
The automation processes PDF documents from an input folder and performs classification, extraction, validation, routing, and transaction handling.


Workflow

Trigger:
New documents are detected from a configured input folder.
The solution uses a folder-based transaction model where each PDF file is treated as a separate transaction.

Classify:
Documents are classified into one of the following types:
Application
APS
BankForm
Unknown

Extract:
Required fields are extracted using PDF text extraction and regular expression matching.
Validation checks confirm that required fields are present.

REFramework Design
Init:
Load configuration from config.json
Initialize document collection

Get Transaction:
Retrieve the next PDF document from the input folder
Each file is treated as a transaction item

Process Transaction:
Read PDF text
Classify document
Extract fields
Validate extracted data
Route based on validation and confidence
Display transaction summary information

End Process:
Complete processing


Configuration:
Configuration values are stored externally in config.json.


AI Usage:
ChatGPT was used as a development aid for:
Regular expression generation

All implementation decisions, workflow construction, testing, and final submission preparation were completed by the Mitchell Hammond.

Known Limitations:
Due to time constraints, date format validation and policy number pattern validation were not fully implemented.
Integration with the provided mock Policy Intake API was not fully completed before submission.
File-based audit logging was not completed. The current implementation displays transaction information through UiPath logging and message output during execution
Policy number pattern validation was not implemented.

Future Improvements:
Given additional development time, the following enhancements would be implemented:
Complete Policy Intake API integration with retry and error handling.
Add date format and policy number validation rules.
Implement structured file-based audit logging.
Improve document classification confidence scoring.
Add additional exception handling and reporting.
Expand support for additional document layouts and formats.