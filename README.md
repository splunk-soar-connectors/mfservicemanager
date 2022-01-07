[comment]: # "Auto-generated SOAR connector documentation"
# Micro Focus Service Manager

Publisher: Splunk Community  
Connector Version: 1\.3\.1  
Product Vendor: MicroFocus  
Product Name: Service Manager  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.6\.19142  

This app supports a variety of object management actions on Micro Focus Service Manager \(formerly HPE Service Manager\)

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Service Manager asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  required  | string | URL for the API \(e\.g\. https\://api\.itsm\.com/\)
**username** |  required  | string | Username
**password** |  required  | password | Password for User

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[create incident](#action-create-incident) - Create an incident  
[get incident](#action-get-incident) - Get incident details  
[update incident](#action-update-incident) - Update incident details  
[close incident](#action-close-incident) - Close an incident  
[create change](#action-create-change) - Create a change  
[get change](#action-get-change) - Get change information  
[close change](#action-close-change) - Close out a change  
[create configuration](#action-create-configuration) - Create a configuration item  
[get object](#action-get-object) - Get object information  
[update object](#action-update-object) - Update an object  
[close object](#action-close-object) - Close an object  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'create incident'
Create an incident

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**title** |  required  | Title for the incident | string | 
**description** |  required  | Description of the incident | string | 
**service** |  required  | Service associated with the incident | string | 
**area** |  required  | Area for the incident \(e\.g\. Application\) | string | 
**subarea** |  required  | Subarea for the incident \(e\.g\. Availability Issue\) | string | 
**assignment\_group** |  required  | Assignment group for the incident | string | 
**fields** |  optional  | JSON containing field values | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.area | string | 
action\_result\.parameter\.assignment\_group | string | 
action\_result\.parameter\.description | string | 
action\_result\.parameter\.fields | string | 
action\_result\.parameter\.service | string | 
action\_result\.parameter\.subarea | string | 
action\_result\.parameter\.title | string | 
action\_result\.data\.\*\.Area | string | 
action\_result\.data\.\*\.AssignmentGroup | string | 
action\_result\.data\.\*\.Category | string | 
action\_result\.data\.\*\.Description | string | 
action\_result\.data\.\*\.Impact | string | 
action\_result\.data\.\*\.IncidentID | string |  `itsm incident id` 
action\_result\.data\.\*\.JournalUpdates | string | 
action\_result\.data\.\*\.OpenTime | string | 
action\_result\.data\.\*\.OpenedBy | string | 
action\_result\.data\.\*\.Phase | string | 
action\_result\.data\.\*\.ProblemType | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.data\.\*\.Service | string | 
action\_result\.data\.\*\.Status | string | 
action\_result\.data\.\*\.Subarea | string | 
action\_result\.data\.\*\.Title | string | 
action\_result\.data\.\*\.UpdatedBy | string | 
action\_result\.data\.\*\.UpdatedTime | string | 
action\_result\.data\.\*\.Urgency | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get incident'
Get incident details

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Incident ID | string |  `itsm incident id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.id | string |  `itsm incident id` 
action\_result\.data\.\*\.Area | string | 
action\_result\.data\.\*\.AssignmentGroup | string | 
action\_result\.data\.\*\.Category | string | 
action\_result\.data\.\*\.Description | string | 
action\_result\.data\.\*\.Impact | string | 
action\_result\.data\.\*\.IncidentID | string |  `itsm incident id` 
action\_result\.data\.\*\.JournalUpdates | string | 
action\_result\.data\.\*\.OpenTime | string | 
action\_result\.data\.\*\.OpenedBy | string | 
action\_result\.data\.\*\.Phase | string | 
action\_result\.data\.\*\.ProblemType | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.data\.\*\.Service | string | 
action\_result\.data\.\*\.Status | string | 
action\_result\.data\.\*\.Subarea | string | 
action\_result\.data\.\*\.Title | string | 
action\_result\.data\.\*\.UpdatedBy | string | 
action\_result\.data\.\*\.UpdatedTime | string | 
action\_result\.data\.\*\.Urgency | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'update incident'
Update incident details

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Incident ID | string |  `itsm incident id` 
**description** |  optional  | Incident description | string | 
**assignee** |  required  | Assignee | string | 
**assignment\_group** |  optional  | Assignment group | string | 
**title** |  optional  | Incident title | string | 
**category** |  optional  | Incident category | string | 
**contact** |  optional  | Contact | string | 
**impact** |  optional  | Impact of the incident \(1\-4\) | numeric | 
**affected\_ci** |  optional  | Affected CI | string | 
**area** |  optional  | Area | string | 
**subarea** |  optional  | Subarea | string | 
**urgency** |  optional  | Urgency of the incident \(1\-4\) | numeric | 
**journal\_updates** |  required  | Journal updates \(newline\-separated\) | string | 
**service** |  optional  | Service | string | 
**ticket\_source** |  optional  | Ticket source | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.affected\_ci | string | 
action\_result\.parameter\.area | string | 
action\_result\.parameter\.assignee | string | 
action\_result\.parameter\.assignment\_group | string | 
action\_result\.parameter\.category | string | 
action\_result\.parameter\.contact | string | 
action\_result\.parameter\.description | string | 
action\_result\.parameter\.impact | numeric | 
action\_result\.parameter\.journal\_updates | string | 
action\_result\.parameter\.service | string | 
action\_result\.parameter\.subarea | string | 
action\_result\.parameter\.ticket\_source | string | 
action\_result\.parameter\.title | string | 
action\_result\.parameter\.urgency | numeric | 
action\_result\.parameter\.id | string |  `itsm incident id` 
action\_result\.data\.\*\.Area | string | 
action\_result\.data\.\*\.AssignmentGroup | string | 
action\_result\.data\.\*\.Category | string | 
action\_result\.data\.\*\.Description | string | 
action\_result\.data\.\*\.Impact | string | 
action\_result\.data\.\*\.IncidentID | string |  `itsm incident id` 
action\_result\.data\.\*\.JournalUpdates | string | 
action\_result\.data\.\*\.OpenTime | string | 
action\_result\.data\.\*\.OpenedBy | string | 
action\_result\.data\.\*\.Phase | string | 
action\_result\.data\.\*\.ProblemType | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.data\.\*\.Service | string | 
action\_result\.data\.\*\.Status | string | 
action\_result\.data\.\*\.Subarea | string | 
action\_result\.data\.\*\.Title | string | 
action\_result\.data\.\*\.UpdatedBy | string | 
action\_result\.data\.\*\.UpdatedTime | string | 
action\_result\.data\.\*\.Urgency | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'close incident'
Close an incident

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Incident ID | string |  `itsm incident id` 
**assignee** |  required  | Assignee | string | 
**closure\_code** |  required  | Closure code | string | 
**solution** |  required  | Solution | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.assignee | string | 
action\_result\.parameter\.closure\_code | string | 
action\_result\.parameter\.id | string |  `itsm incident id` 
action\_result\.parameter\.solution | string | 
action\_result\.data\.\*\.Area | string | 
action\_result\.data\.\*\.AssignmentGroup | string | 
action\_result\.data\.\*\.Category | string | 
action\_result\.data\.\*\.Description | string | 
action\_result\.data\.\*\.Impact | string | 
action\_result\.data\.\*\.IncidentID | string |  `itsm incident id` 
action\_result\.data\.\*\.JournalUpdates | string | 
action\_result\.data\.\*\.OpenTime | string | 
action\_result\.data\.\*\.OpenedBy | string | 
action\_result\.data\.\*\.Phase | string | 
action\_result\.data\.\*\.ProblemType | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.data\.\*\.Service | string | 
action\_result\.data\.\*\.Status | string | 
action\_result\.data\.\*\.Subarea | string | 
action\_result\.data\.\*\.Title | string | 
action\_result\.data\.\*\.UpdatedBy | string | 
action\_result\.data\.\*\.UpdatedTime | string | 
action\_result\.data\.\*\.Urgency | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'create change'
Create a change

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**title** |  required  | Title for the change | string | 
**description** |  required  | Description of the change | string | 
**reason** |  required  | Reason for the change | string | 
**impact** |  required  | Impact of the change | string | 
**service** |  required  | Service associated with the change | string | 
**category** |  required  | Category for the change | string | 
**subcategory** |  required  | Subcategory for the change | string | 
**assignment\_group** |  required  | Assignment group for the change | string | 
**change\_coordinator** |  required  | Change coordinator for the change | string | 
**no\_implementation\_effect** |  required  | Effect of not implementing the change | string | 
**implementation\_start** |  required  | Scheduled implementation start for the change | string | 
**implementation\_end** |  required  | Scheduled implementation end for the change | string | 
**fields** |  optional  | JSON containing field values | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.assignment\_group | string | 
action\_result\.parameter\.category | string | 
action\_result\.parameter\.change\_coordinator | string | 
action\_result\.parameter\.description | string | 
action\_result\.parameter\.fields | string | 
action\_result\.parameter\.impact | string | 
action\_result\.parameter\.implementation\_end | string | 
action\_result\.parameter\.implementation\_start | string | 
action\_result\.parameter\.no\_implementation\_effect | string | 
action\_result\.parameter\.reason | string | 
action\_result\.parameter\.service | string | 
action\_result\.parameter\.subcategory | string | 
action\_result\.parameter\.title | string | 
action\_result\.data\.\*\.CustomerVisible | boolean | 
action\_result\.data\.\*\.EffectOfNotImplementing | string | 
action\_result\.data\.\*\.Impact | string | 
action\_result\.data\.\*\.Service | string | 
action\_result\.data\.\*\.Urgency | string | 
action\_result\.data\.\*\.description\.structure\.Description | string | 
action\_result\.data\.\*\.header\.ApprovalStatus | string | 
action\_result\.data\.\*\.header\.AssignmentGroup | string | 
action\_result\.data\.\*\.header\.Category | string | 
action\_result\.data\.\*\.header\.ChangeCoordinator | string | 
action\_result\.data\.\*\.header\.ChangeID | string |  `itsm object id` 
action\_result\.data\.\*\.header\.DateEntered | string | 
action\_result\.data\.\*\.header\.InitiatedBy | string | 
action\_result\.data\.\*\.header\.Open | boolean | 
action\_result\.data\.\*\.header\.Phase | string | 
action\_result\.data\.\*\.header\.PlannedEnd | string | 
action\_result\.data\.\*\.header\.PlannedStart | string | 
action\_result\.data\.\*\.header\.Reason | string | 
action\_result\.data\.\*\.header\.RiskAssessment | string | 
action\_result\.data\.\*\.header\.Status | string | 
action\_result\.data\.\*\.header\.Subcategory | string | 
action\_result\.data\.\*\.header\.Title | string | 
action\_result\.summary\.success | boolean | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get change'
Get change information

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Change ID | string |  `itsm object id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.id | string |  `itsm object id` 
action\_result\.data\.\*\.CustomerVisible | boolean | 
action\_result\.data\.\*\.EffectOfNotImplementing | string | 
action\_result\.data\.\*\.Impact | string | 
action\_result\.data\.\*\.ImplementationEnd | string | 
action\_result\.data\.\*\.ImplementationStart | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.data\.\*\.ReviewResults | string | 
action\_result\.data\.\*\.Service | string | 
action\_result\.data\.\*\.Urgency | string | 
action\_result\.data\.\*\.close\.ClosingComments | string | 
action\_result\.data\.\*\.close\.ClosureCode | numeric | 
action\_result\.data\.\*\.description\.structure\.Description | string | 
action\_result\.data\.\*\.description\.structure\.ImplementationComments | string | 
action\_result\.data\.\*\.header\.ApprovalStatus | string | 
action\_result\.data\.\*\.header\.AssignedTo | string | 
action\_result\.data\.\*\.header\.AssignmentGroup | string | 
action\_result\.data\.\*\.header\.BackoutDuration | string | 
action\_result\.data\.\*\.header\.Category | string | 
action\_result\.data\.\*\.header\.ChangeCoordinator | string | 
action\_result\.data\.\*\.header\.ChangeID | string |  `itsm object id` 
action\_result\.data\.\*\.header\.ChangeModel | string | 
action\_result\.data\.\*\.header\.CloseTime | string | 
action\_result\.data\.\*\.header\.DateEntered | string | 
action\_result\.data\.\*\.header\.InitiatedBy | string | 
action\_result\.data\.\*\.header\.Open | boolean | 
action\_result\.data\.\*\.header\.Phase | string | 
action\_result\.data\.\*\.header\.PlannedEnd | string | 
action\_result\.data\.\*\.header\.PlannedStart | string | 
action\_result\.data\.\*\.header\.Priority | string | 
action\_result\.data\.\*\.header\.Reason | string | 
action\_result\.data\.\*\.header\.RiskAssessment | string | 
action\_result\.data\.\*\.header\.Status | string | 
action\_result\.data\.\*\.header\.Subcategory | string | 
action\_result\.data\.\*\.header\.Title | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'close change'
Close out a change

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Change ID | string |  `itsm object id` 
**closure\_comments** |  required  | Closure comments for this change \(newline\-separated\) | string | 
**closure\_code** |  required  | Closure code for this change | numeric | 
**review\_results** |  required  | Review results for this change | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.closure\_code | string | 
action\_result\.parameter\.closure\_comments | string | 
action\_result\.parameter\.id | string |  `itsm object id` 
action\_result\.parameter\.review\_results | string | 
action\_result\.data\.\*\.CustomerVisible | boolean | 
action\_result\.data\.\*\.EffectOfNotImplementing | string | 
action\_result\.data\.\*\.Impact | string | 
action\_result\.data\.\*\.ImplementationEnd | string | 
action\_result\.data\.\*\.ImplementationStart | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.data\.\*\.ReviewResults | string | 
action\_result\.data\.\*\.Service | string | 
action\_result\.data\.\*\.Urgency | string | 
action\_result\.data\.\*\.close\.ClosingComments | string | 
action\_result\.data\.\*\.close\.ClosureCode | numeric | 
action\_result\.data\.\*\.description\.structure\.Description | string | 
action\_result\.data\.\*\.description\.structure\.ImplementationComments | string | 
action\_result\.data\.\*\.header\.ApprovalStatus | string | 
action\_result\.data\.\*\.header\.AssignedTo | string | 
action\_result\.data\.\*\.header\.AssignmentGroup | string | 
action\_result\.data\.\*\.header\.BackoutDuration | string | 
action\_result\.data\.\*\.header\.Category | string | 
action\_result\.data\.\*\.header\.ChangeCoordinator | string | 
action\_result\.data\.\*\.header\.ChangeID | string |  `itsm object id` 
action\_result\.data\.\*\.header\.ChangeModel | string | 
action\_result\.data\.\*\.header\.CloseTime | string | 
action\_result\.data\.\*\.header\.DateEntered | string | 
action\_result\.data\.\*\.header\.InitiatedBy | string | 
action\_result\.data\.\*\.header\.Open | boolean | 
action\_result\.data\.\*\.header\.Phase | string | 
action\_result\.data\.\*\.header\.PlannedEnd | string | 
action\_result\.data\.\*\.header\.PlannedStart | string | 
action\_result\.data\.\*\.header\.Priority | string | 
action\_result\.data\.\*\.header\.Reason | string | 
action\_result\.data\.\*\.header\.RiskAssessment | string | 
action\_result\.data\.\*\.header\.Status | string | 
action\_result\.data\.\*\.header\.Subcategory | string | 
action\_result\.data\.\*\.header\.Title | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'create configuration'
Create a configuration item

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**display\_name** |  required  | Display name for the CI | string | 
**ci\_type** |  required  | Type for the CI | string | 
**ci\_subtype** |  required  | Subtype for the CI | string | 
**assignment\_group** |  required  | Assignment group for the CI | string | 
**owner\_individual** |  required  | Contact name for the CI | string | 
**department** |  required  | Department for the CI | string | 
**department\_owner** |  required  | Owner of the department for the CI | string | 
**status** |  required  | Status for the CI | string | 
**fields** |  optional  | JSON containing field values | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ci\_subtype | string | 
action\_result\.parameter\.ci\_type | string | 
action\_result\.parameter\.assignment\_group | string | 
action\_result\.parameter\.department | string | 
action\_result\.parameter\.department\_owner | string | 
action\_result\.parameter\.display\_name | string | 
action\_result\.parameter\.fields | string | 
action\_result\.parameter\.owner\_individual | string | 
action\_result\.parameter\.status | string | 
action\_result\.data\.\*\.AssignmentGroup | string | 
action\_result\.data\.\*\.ConfigurationItem | string | 
action\_result\.data\.\*\.ConfigurationItemSubType | string | 
action\_result\.data\.\*\.ConfigurationItemType | string | 
action\_result\.data\.\*\.Critical | boolean | 
action\_result\.data\.\*\.Department | string | 
action\_result\.data\.\*\.DepartmentOwner | string | 
action\_result\.data\.\*\.DisplayName | string | 
action\_result\.data\.\*\.Environment | string | 
action\_result\.data\.\*\.Location | string | 
action\_result\.data\.\*\.LocationCode | string | 
action\_result\.data\.\*\.Model | string | 
action\_result\.data\.\*\.OS | string | 
action\_result\.data\.\*\.PrimaryService | string | 
action\_result\.data\.\*\.PushGroup | string | 
action\_result\.data\.\*\.SerialNumber | string | 
action\_result\.data\.\*\.Status | string | 
action\_result\.data\.\*\.SystemDown | boolean | 
action\_result\.data\.\*\.TimeZone | string | 
action\_result\.data\.\*\.UpdatedBy | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get object'
Get object information

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Object \(Issue\) ID | string |  `itsm object id` 
**project\_key** |  optional  | Project key to get the issue from | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.id | string |  `itsm object id` 
action\_result\.parameter\.project\_key | string | 
action\_result\.data\.\*\.Change\.CustomerVisible | boolean | 
action\_result\.data\.\*\.Change\.EffectOfNotImplementing | string | 
action\_result\.data\.\*\.Change\.Impact | string | 
action\_result\.data\.\*\.Change\.ImplementationEnd | string | 
action\_result\.data\.\*\.Change\.ImplementationStart | string | 
action\_result\.data\.\*\.Change\.ReviewResults | string | 
action\_result\.data\.\*\.Change\.Service | string | 
action\_result\.data\.\*\.Change\.Urgency | string | 
action\_result\.data\.\*\.Change\.close\.ClosingComments | string | 
action\_result\.data\.\*\.Change\.close\.ClosureCode | numeric | 
action\_result\.data\.\*\.Change\.description\.structure\.Description | string | 
action\_result\.data\.\*\.Change\.description\.structure\.ImplementationComments | string | 
action\_result\.data\.\*\.Change\.header\.ApprovalStatus | string | 
action\_result\.data\.\*\.Change\.header\.AssignedTo | string | 
action\_result\.data\.\*\.Change\.header\.AssignmentGroup | string | 
action\_result\.data\.\*\.Change\.header\.BackoutDuration | string | 
action\_result\.data\.\*\.Change\.header\.Category | string | 
action\_result\.data\.\*\.Change\.header\.ChangeCoordinator | string | 
action\_result\.data\.\*\.Change\.header\.ChangeID | string |  `itsm object id` 
action\_result\.data\.\*\.Change\.header\.ChangeModel | string | 
action\_result\.data\.\*\.Change\.header\.CloseTime | string | 
action\_result\.data\.\*\.Change\.header\.DateEntered | string | 
action\_result\.data\.\*\.Change\.header\.InitiatedBy | string | 
action\_result\.data\.\*\.Change\.header\.Open | boolean | 
action\_result\.data\.\*\.Change\.header\.Phase | string | 
action\_result\.data\.\*\.Change\.header\.PlannedEnd | string | 
action\_result\.data\.\*\.Change\.header\.PlannedStart | string | 
action\_result\.data\.\*\.Change\.header\.Priority | string | 
action\_result\.data\.\*\.Change\.header\.Reason | string | 
action\_result\.data\.\*\.Change\.header\.RiskAssessment | string | 
action\_result\.data\.\*\.Change\.header\.Status | string | 
action\_result\.data\.\*\.Change\.header\.Subcategory | string | 
action\_result\.data\.\*\.Change\.header\.Title | string | 
action\_result\.data\.\*\.Contact\.Active | boolean | 
action\_result\.data\.\*\.Contact\.Company | string | 
action\_result\.data\.\*\.Contact\.ContactName | string | 
action\_result\.data\.\*\.Contact\.CorpStructure | string | 
action\_result\.data\.\*\.Contact\.CostCenter | string | 
action\_result\.data\.\*\.Contact\.CostCentre | string | 
action\_result\.data\.\*\.Contact\.Department | string | 
action\_result\.data\.\*\.Contact\.DepartmentName | string | 
action\_result\.data\.\*\.Contact\.EmployeeID | string | 
action\_result\.data\.\*\.Contact\.FirstName | string | 
action\_result\.data\.\*\.Contact\.FullName | string | 
action\_result\.data\.\*\.Contact\.Group | string | 
action\_result\.data\.\*\.Contact\.LastName | string | 
action\_result\.data\.\*\.Contact\.Location | string | 
action\_result\.data\.\*\.Contact\.LocationCode | string | 
action\_result\.data\.\*\.Contact\.Manager | string | 
action\_result\.data\.\*\.Contact\.TimeZone | string | 
action\_result\.data\.\*\.Contact\.Title | string | 
action\_result\.data\.\*\.Contact\.WorkPhone | string | 
action\_result\.data\.\*\.Device\.AssignmentGroup | string | 
action\_result\.data\.\*\.Device\.ConfigurationItem | string | 
action\_result\.data\.\*\.Device\.ConfigurationItemSubType | string | 
action\_result\.data\.\*\.Device\.ConfigurationItemType | string | 
action\_result\.data\.\*\.Device\.Critical | boolean | 
action\_result\.data\.\*\.Device\.Department | string | 
action\_result\.data\.\*\.Device\.DepartmentOwner | string | 
action\_result\.data\.\*\.Device\.DisplayName | string | 
action\_result\.data\.\*\.Device\.Environment | string | 
action\_result\.data\.\*\.Device\.Location | string | 
action\_result\.data\.\*\.Device\.LocationCode | string | 
action\_result\.data\.\*\.Device\.Model | string | 
action\_result\.data\.\*\.Device\.OS | string | 
action\_result\.data\.\*\.Device\.PrimaryService | string | 
action\_result\.data\.\*\.Device\.PushGroup | string | 
action\_result\.data\.\*\.Device\.SerialNumber | string | 
action\_result\.data\.\*\.Device\.Status | string | 
action\_result\.data\.\*\.Device\.SystemDown | boolean | 
action\_result\.data\.\*\.Device\.TimeZone | string | 
action\_result\.data\.\*\.Device\.UpdatedBy | string | 
action\_result\.data\.\*\.Incident\.Area | string | 
action\_result\.data\.\*\.Incident\.AssignmentGroup | string | 
action\_result\.data\.\*\.Incident\.Category | string | 
action\_result\.data\.\*\.Incident\.Description | string | 
action\_result\.data\.\*\.Incident\.Impact | string | 
action\_result\.data\.\*\.Incident\.IncidentID | string |  `itsm incident id` 
action\_result\.data\.\*\.Incident\.JournalUpdates | string | 
action\_result\.data\.\*\.Incident\.OpenTime | string | 
action\_result\.data\.\*\.Incident\.OpenedBy | string | 
action\_result\.data\.\*\.Incident\.Phase | string | 
action\_result\.data\.\*\.Incident\.ProblemType | string | 
action\_result\.data\.\*\.Incident\.Service | string | 
action\_result\.data\.\*\.Incident\.Status | string | 
action\_result\.data\.\*\.Incident\.Subarea | string | 
action\_result\.data\.\*\.Incident\.Title | string | 
action\_result\.data\.\*\.Incident\.UpdatedBy | string | 
action\_result\.data\.\*\.Incident\.UpdatedTime | string | 
action\_result\.data\.\*\.Incident\.Urgency | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'update object'
Update an object

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Object ID | string |  `itsm object id` 
**update\_fields** |  optional  | JSON containing field values | string | 
**project\_key** |  optional  | Project key to update the object | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.id | string |  `itsm object id` 
action\_result\.parameter\.project\_key | string | 
action\_result\.parameter\.update\_fields | string | 
action\_result\.data\.\*\.Change\.CustomerVisible | boolean | 
action\_result\.data\.\*\.Change\.EffectOfNotImplementing | string | 
action\_result\.data\.\*\.Change\.Impact | string | 
action\_result\.data\.\*\.Change\.ImplementationEnd | string | 
action\_result\.data\.\*\.Change\.ImplementationStart | string | 
action\_result\.data\.\*\.Change\.ReviewResults | string | 
action\_result\.data\.\*\.Change\.Service | string | 
action\_result\.data\.\*\.Change\.Urgency | string | 
action\_result\.data\.\*\.Change\.close\.ClosingComments | string | 
action\_result\.data\.\*\.Change\.close\.ClosureCode | numeric | 
action\_result\.data\.\*\.Change\.description\.structure\.Description | string | 
action\_result\.data\.\*\.Change\.description\.structure\.ImplementationComments | string | 
action\_result\.data\.\*\.Change\.header\.ApprovalStatus | string | 
action\_result\.data\.\*\.Change\.header\.AssignedTo | string | 
action\_result\.data\.\*\.Change\.header\.AssignmentGroup | string | 
action\_result\.data\.\*\.Change\.header\.BackoutDuration | string | 
action\_result\.data\.\*\.Change\.header\.Category | string | 
action\_result\.data\.\*\.Change\.header\.ChangeCoordinator | string | 
action\_result\.data\.\*\.Change\.header\.ChangeID | string |  `itsm object id` 
action\_result\.data\.\*\.Change\.header\.ChangeModel | string | 
action\_result\.data\.\*\.Change\.header\.CloseTime | string | 
action\_result\.data\.\*\.Change\.header\.DateEntered | string | 
action\_result\.data\.\*\.Change\.header\.InitiatedBy | string | 
action\_result\.data\.\*\.Change\.header\.Open | boolean | 
action\_result\.data\.\*\.Change\.header\.Phase | string | 
action\_result\.data\.\*\.Change\.header\.PlannedEnd | string | 
action\_result\.data\.\*\.Change\.header\.PlannedStart | string | 
action\_result\.data\.\*\.Change\.header\.Priority | string | 
action\_result\.data\.\*\.Change\.header\.Reason | string | 
action\_result\.data\.\*\.Change\.header\.RiskAssessment | string | 
action\_result\.data\.\*\.Change\.header\.Status | string | 
action\_result\.data\.\*\.Change\.header\.Subcategory | string | 
action\_result\.data\.\*\.Change\.header\.Title | string | 
action\_result\.data\.\*\.Contact\.Active | boolean | 
action\_result\.data\.\*\.Contact\.Company | string | 
action\_result\.data\.\*\.Contact\.ContactName | string | 
action\_result\.data\.\*\.Contact\.CorpStructure | string | 
action\_result\.data\.\*\.Contact\.CostCenter | string | 
action\_result\.data\.\*\.Contact\.CostCentre | string | 
action\_result\.data\.\*\.Contact\.Department | string | 
action\_result\.data\.\*\.Contact\.DepartmentName | string | 
action\_result\.data\.\*\.Contact\.EmployeeID | string | 
action\_result\.data\.\*\.Contact\.FirstName | string | 
action\_result\.data\.\*\.Contact\.FullName | string | 
action\_result\.data\.\*\.Contact\.Group | string | 
action\_result\.data\.\*\.Contact\.LastName | string | 
action\_result\.data\.\*\.Contact\.Location | string | 
action\_result\.data\.\*\.Contact\.LocationCode | string | 
action\_result\.data\.\*\.Contact\.Manager | string | 
action\_result\.data\.\*\.Contact\.TimeZone | string | 
action\_result\.data\.\*\.Contact\.Title | string | 
action\_result\.data\.\*\.Contact\.WorkPhone | string | 
action\_result\.data\.\*\.Device\.AssignmentGroup | string | 
action\_result\.data\.\*\.Device\.ConfigurationItem | string | 
action\_result\.data\.\*\.Device\.ConfigurationItemSubType | string | 
action\_result\.data\.\*\.Device\.ConfigurationItemType | string | 
action\_result\.data\.\*\.Device\.Critical | boolean | 
action\_result\.data\.\*\.Device\.Department | string | 
action\_result\.data\.\*\.Device\.DepartmentOwner | string | 
action\_result\.data\.\*\.Device\.DisplayName | string | 
action\_result\.data\.\*\.Device\.Environment | string | 
action\_result\.data\.\*\.Device\.Location | string | 
action\_result\.data\.\*\.Device\.LocationCode | string | 
action\_result\.data\.\*\.Device\.Model | string | 
action\_result\.data\.\*\.Device\.OS | string | 
action\_result\.data\.\*\.Device\.PrimaryService | string | 
action\_result\.data\.\*\.Device\.PushGroup | string | 
action\_result\.data\.\*\.Device\.SerialNumber | string | 
action\_result\.data\.\*\.Device\.Status | string | 
action\_result\.data\.\*\.Device\.SystemDown | boolean | 
action\_result\.data\.\*\.Device\.TimeZone | string | 
action\_result\.data\.\*\.Device\.UpdatedBy | string | 
action\_result\.data\.\*\.Incident\.Area | string | 
action\_result\.data\.\*\.Incident\.AssignmentGroup | string | 
action\_result\.data\.\*\.Incident\.Category | string | 
action\_result\.data\.\*\.Incident\.Description | string | 
action\_result\.data\.\*\.Incident\.Impact | string | 
action\_result\.data\.\*\.Incident\.IncidentID | string |  `itsm incident id` 
action\_result\.data\.\*\.Incident\.JournalUpdates | string | 
action\_result\.data\.\*\.Incident\.OpenTime | string | 
action\_result\.data\.\*\.Incident\.OpenedBy | string | 
action\_result\.data\.\*\.Incident\.Phase | string | 
action\_result\.data\.\*\.Incident\.ProblemType | string | 
action\_result\.data\.\*\.Incident\.Service | string | 
action\_result\.data\.\*\.Incident\.Status | string | 
action\_result\.data\.\*\.Incident\.Subarea | string | 
action\_result\.data\.\*\.Incident\.Title | string | 
action\_result\.data\.\*\.Incident\.UpdatedBy | string | 
action\_result\.data\.\*\.Incident\.UpdatedTime | string | 
action\_result\.data\.\*\.Incident\.Urgency | string | 
action\_result\.data\.\*\.ReturnCode | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'close object'
Close an object

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Object ID | string |  `itsm object id` 
**project\_key** |  optional  | Project key to close the object | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.id | string |  `itsm object id` 
action\_result\.parameter\.project\_key | string | 
action\_result\.data | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 