Risks

Sr. No| Risk Description| Owner / POC| Probability H/M/L| Impact H/M/L| Mitigation
1| Delay in availability of AWS/Salesforce test environments or required access may impact testing timelines.| TBC| M| H| Raise access requests early and track environment readiness.
2| Delay in API/integration readiness may impact API and E2E testing.| TBC| M| H| Confirm API contracts, endpoints and integration readiness before test execution.
3| Variability in LLM-generated summaries may impact validation results.| TBC| M| H| Define evaluation criteria, golden summaries and LLM validation thresholds.
4| Inadequate or unrepresentative transcript test data may limit LLM validation coverage.| TBC| M| H| Prepare representative raw transcripts covering different scenarios and complexity levels.
5| PII or sensitive information in test transcripts may create data/privacy risk.| TBC| L| H| Use approved test data and validate PII detection/redaction before LLM processing.
6| Changes to prompt/model configuration may affect previously validated summary results.| TBC| M| M| Track model/prompt versions and execute regression validation for significant changes.

Assumptions

Sr. No| Assumption
1| Required Salesforce, AWS and API test environments will be available before the respective test phase.
2| Required access to AWS services, Salesforce and API endpoints will be provided to the QA team.
3| Claude Haiku 4.5 will be the agreed model for the initial LLM validation.
4| Raw transcript test data and corresponding golden/reference summaries will be available before LLM validation.
5| API specifications/contracts and expected request/response details will be available for API testing.
6| Required logs/monitoring information will be accessible to QA for investigation of integration failures, where required.

Issues

Sr. No| Issue| Resolution Strategy
1| No known QA blocking issues at the time of test plan preparation.| Track new issues in Jira and review during test execution/defect triage.

Dependencies

Sr. No| Dependency| Tasks/Event Impacted| Owner
1| Salesforce test environment and CRT application| Component, API Integration, E2E, Regression| TBC
2| AWS environment and required service access| API Integration, LLM Validation, E2E| TBC
3| API Gateway / TYK API availability and API specifications| API Integration, E2E| TBC
4| AWS Lambda / orchestration services| API Integration, E2E| TBC
5| AWS Connect transcript availability| Transcript retrieval and E2E testing| TBC
6| S3 transcript storage and DynamoDB metadata| Transcript/metadata validation and E2E| TBC
7| AWS Comprehend / Guardrails for PII detection and redaction| PII validation and E2E| TBC
8| AWS Bedrock – Claude Haiku 4.5 access| LLM Validation and E2E| TBC
9| Raw transcript test data and golden/reference summaries| LLM Validation| QA / BA
10| Approved prompts and LLM evaluation criteria| LLM Validation| TBC
11| Authentication/access mechanism including required tokens| API Integration and E2E| TBC
