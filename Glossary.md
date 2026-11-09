> Version 8 is the latest consolidated copy. Live results remain from Version 5; no new API request was made to save this version. Earlier source/history subfolders retain their original labels.

# Version 8 — plain-language terms

## Plain-language glossary

| Term | Meaning in this project |
|---|---|
| POC | Proof of concept: a small implementation used to explore feasibility. It is not automatically ready for real patient deployment. |
| EHR | Electronic health record: the source of the operational patient information represented here by SQLite tables. |
| API | An interface through which the notebook sends a request to a model service and receives a response. A successful request may incur usage charges. |
| API key | A secret credential used to authenticate requests. Saving it is different from proving the service accepts it. |
| Authentication | Verifying access through accepted credentials. It does not answer whether a particular patient record may be used. |
| Authorization | Permission for an action or data access. The saved approval here covers five specified project tests, not an entire deployed healthcare service. |
| Agent | The one language generator that selects tools and drafts answers within the configured workflow. |
| ReAct | The pattern of alternating model decisions and tool observations before a final response. It does not require showing private internal reasoning. |
| Tool | An application-defined function that retrieves a particular type of record or reference content. It is not another autonomous agent. |
| Tool observation | The data or error returned by a tool and added to the message history. An observation is evidence to inspect, not a clinical-quality guarantee. |
| State | The request’s structured information: identity, query, policy decision, messages, evidence, limits, errors and outputs. |
| Policy gate | Application code that applies selected restrictions before generation, such as refusal or immediate-care routing. |
| Guardrail | A constraint intended to reduce a specified risk. Each guardrail has a scope and failure modes; it does not eliminate all risk. |
| Controlled abstention | An intentional decision not to provide requested information when appropriate supporting content is unavailable. It can be correct containment while leaving an information need unmet. |
| Withholding | Removing or not serving a particular part of a draft, such as the observed symptom-based urgency instruction. This may also reduce completeness. |
| Grounding | Connecting a response to retrieved evidence. A response can be partly grounded yet contain additional unsupported claims. |
| Citation provenance | Evidence of where a citation came from and whether it was allowed. It is different from showing that the cited page supports every claim. |
| Claim-to-source support | Checking whether a specific statement is actually supported by its source. A reputable domain alone does not establish this. |
| Approved/screened content | In the code, content passing the current catalog and screening rules. Unless separately reviewed, this does not mean clinician-approved content. |
| Quarantine | Intentional withholding of a reference row because of an identified content or source issue pending review. |
| Schema | The expected fields and structure of data. Correct field names do not guarantee correct values. |
| Parameterized query | A fixed SQL query with values bound separately through placeholders, rather than concatenating patient input into SQL text. |
| Patient scoping | Restricting a record query to the active patient. The active identity must still come from a trustworthy application context. |
| PHI | Protected health information. This project treats clinical observations, traces and saved outputs as potentially sensitive; it does not certify the source dataset as de-identified. |
| Prompt injection | An attempt to make instructions inside a user message or retrieved text override the application’s intended rules. |
| Regression check | A check designed to detect recurrence of a known implementation failure after a change. Passing it does not prove all related inputs are safe. |
| Offline check | A local check that does not invoke the real model service. A local controlled stub can test workflow wiring without evaluating a medical answer. |
| Live run | A run using actual model/API requests. Live does not mean clinically validated, accurate or approved for deployment. |
| Generator turn | One model invocation in the loop. It may request multiple tools or return a draft; it is not necessarily one complete user interaction. |
| Latency | Time taken to return a response. The project did not establish its distribution under realistic load. |
| Overblocking | Rejecting or withholding a request/content item that would otherwise be appropriate. It should be measured alongside missed restrictions. |
| Clinical validation | A structured assessment by qualified reviewers using appropriate cases and criteria. The five-case implementation inspection is not a completed clinical-validation study. |
| ROI | Return on investment: a financial assessment requiring measured benefits and total costs. It has not been established in this POC. |
| Snapshot/provenance | A saved version and a record of where its code, data and results came from. A copied result is not a newly executed test. |



### Additional risk-review terms

| Term | Plain-language meaning |
|---|---|
| Risk | A possibility that an outcome could harm patients, expose data, impair service or mislead a decision. Describing a risk does not mean it occurred. |
| Observed failure | A behavior actually seen in a run, such as the unsupported first medication draft. It is stronger evidence than a hypothetical concern but still has a limited scope. |
| Assumption | A condition relied on but not fully established, such as trustworthy caller identity or suitability of a reference row. Important assumptions need verification. |
| Control | A mechanism intended to reduce a specific failure mode, such as a patient filter or final evidence check. It can have gaps and tradeoffs. |
| Residual risk | The risk remaining after existing controls. A passing check does not imply residual risk is zero. |
| Monitoring signal | Information that may reveal a problem, such as unexpected abstention, ownership failures, unsupported claims or latency spikes. A signal needs an owner and response process. |
| Acceptance evidence | The specific reviewed results needed before approving a change or next stage. A recommendation is not acceptance evidence by itself. |
| False positive / overblocking | Treating an appropriate request as restricted, or withholding useful content unnecessarily. |
| False negative / missed restriction | Failing to detect or contain a request or output that should have been restricted. |
| Release criterion | A requirement agreed before broader use; the current project has not established or met all production release criteria. |
| Operational handoff | An actual connection or transfer to a responsible person/service. Printing a clinician or immediate-care message does not establish a completed handoff. |
| Formal risk scoring | A defined assessment of likelihood/severity using suitable evidence and accountable review. This qualitative document does not perform that assessment. |

### Additional mitigation and assessment terms

| Term | Meaning |
|---|---|
| Risk treatment | An action intended to avoid, remove a defined mechanism, reduce, monitor or otherwise manage a concern. Writing it down does not implement it. |
| Bounded elimination | Removing a specifically defined failure route within a stated interface/artifact, not claiming all related risk is gone. |
| Closure evidence | Implemented and reviewed proof against agreed criteria. A proposal or passing unrelated check is not closure. |
| Coverage mapping | Showing where a requirement is addressed and what evidence/gaps exist. It does not assign a grade. |
| Supporting artifact | A working notebook, report or ZIP used to develop the submission; it is not automatically the required submitted file. |
| Trace sanitization | Reviewing/removing inappropriate sensitive content from an actual captured trace; it must not invent a transcript. |
