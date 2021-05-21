---
description:  
---
# Escalation policy

>  **Package : spaceone.api.monitoring.v1**

## EscalationPolicy

{% hint style="info" %}
**EscalationPolicy Methods:**

{%  endhint %}


| NO |  Method | Request Type | Response Type | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | [**create**](escalation-policy.md#create)|   [CreateEscalationPolicyRequest](escalation-policy.md#createescalationpolicyrequest) |   [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo) |  |
| 2 | [**update**](escalation-policy.md#update)|   [UpdateEscalationPolicyRequest](escalation-policy.md#updateescalationpolicyrequest) |   [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo) |  |
| 3 | [**set_default**](escalation-policy.md#set_default)|   [EscalationPolicyRequest](escalation-policy.md#escalationpolicyrequest) |   [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo) |  |
| 4 | [**delete**](escalation-policy.md#delete)|   [EscalationPolicyRequest](escalation-policy.md#escalationpolicyrequest) |  [google.protobuf.Empty](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/empty.proto)|  |
| 5 | [**get**](escalation-policy.md#get)|   [GetEscalationPolicyRequest](escalation-policy.md#getescalationpolicyrequest) |   [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo) |  |
| 6 | [**list**](escalation-policy.md#list)|   [EscalationPolicyQuery](escalation-policy.md#escalationpolicyquery) |   [EscalationPoliciesInfo](escalation-policy.md#escalationpoliciesinfo) |  |
| 7 | [**stat**](escalation-policy.md#stat)|   [EscalationPolicyStatQuery](escalation-policy.md#escalationpolicystatquery) |  [google.protobuf.Struct](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/struct.proto)|  | 
 

 
### create
> **POST** /monitoring/v1/escalation-policies
>


| Type | Message |
| :--- | :--- |
| Request | [CreateEscalationPolicyRequest](escalation-policy.md#createescalationpolicyrequest) |
| Response |  [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo)  |
 
 

 
### update
> **PUT** /monitoring/v1/escalation-policy/{escalation_policy_id}
>


| Type | Message |
| :--- | :--- |
| Request | [UpdateEscalationPolicyRequest](escalation-policy.md#updateescalationpolicyrequest) |
| Response |  [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo)  |
 
 

 
### set_default
> **PUT** /monitoring/v1/escalation-policy/{escalation_policy_id}/set-default
>


| Type | Message |
| :--- | :--- |
| Request | [EscalationPolicyRequest](escalation-policy.md#escalationpolicyrequest) |
| Response |  [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo)  |
 
 

 
### delete
> **DELETE** /monitoring/v1/escalation-policy/{escalation_policy_id}
>


| Type | Message |
| :--- | :--- |
| Request | [EscalationPolicyRequest](escalation-policy.md#escalationpolicyrequest) |
| Response | [google.protobuf.Empty](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/empty.proto) |
 
 

 
### get
> **GET** /monitoring/v1/escalation-policy/{escalation_policy_id}
>


| Type | Message |
| :--- | :--- |
| Request | [GetEscalationPolicyRequest](escalation-policy.md#getescalationpolicyrequest) |
| Response |  [EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo)  |
 
 

 
### list
> **GET** /monitoring/v1/escalation-policies
>
> **POST** /monitoring/v1/escalation-policies/search



| Type | Message |
| :--- | :--- |
| Request | [EscalationPolicyQuery](escalation-policy.md#escalationpolicyquery) |
| Response |  [EscalationPoliciesInfo](escalation-policy.md#escalationpoliciesinfo)  |
 
 

 
### stat
> **POST** /monitoring/v1/escalation-policies/stat
>


| Type | Message |
| :--- | :--- |
| Request | [EscalationPolicyStatQuery](escalation-policy.md#escalationpolicystatquery) |
| Response | [google.protobuf.Struct](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/struct.proto) |


## 

## Message

### CreateEscalationPolicyRequest
<table>
  <thead>
    <tr>
      <th style="text-align:left">No</th>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">name</td>
      <td style="text-align:left">string</td>
<td style="text-align:left">✅</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">rules</td>
      <td style="text-align:left"><a href="escalation-policy.md#escalationpolicyrules">list of EscalationPolicyRules</a></td>
<td style="text-align:left">✅</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">repeat_count</td>
      <td style="text-align:left"><a href="https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/type.proto">int32</a></td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">finish_condition</td>
      <td style="text-align:left"><ul>
          	<li>FINISH_CONDITION_NONE</li>
          	<li>ALL</li>
          	<li>HIGH_ONLY</li>
        </ul></td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">project_id</td>
      <td style="text-align:left">string</td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">6</td>
      <td style="text-align:left">tags</td>
      <td style="text-align:left"><a href="https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/struct.proto">google.protobuf.Struct</a></td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">7</td>
      <td style="text-align:left">domain_id</td>
      <td style="text-align:left">string</td>
<td style="text-align:left">✅</td>
<td style="text-align:left"></td>
   </tr>
  </tbody>
</table>



### EscalationPoliciesInfo
| No | Field | Type |  Description |
| :--- | :--- | :--- | :--- |
| 1 | results |[list of EscalationPolicyInfo](escalation-policy.md#escalationpolicyinfo) | |
| 2 | total_count |[int32](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/type.proto) | |

### EscalationPolicyInfo
| No | Field | Type |  Description |
| :--- | :--- | :--- | :--- |
| 1 | escalation_policy_id |string | |
| 2 | name |string | |
| 3 | is_default |bool | |
| 4 | rules |[list of EscalationPolicyRules](escalation-policy.md#escalationpolicyrules) | |
| 5 | repeat_count |[int32](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/type.proto) | |
| 6 | project_id |string | |
| 7 | tags |[google.protobuf.Struct](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/struct.proto) | |
| 8 | domain_id |string | |
| 9 | created_at |string | |

### EscalationPolicyQuery
| No | Field | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | query |[spaceone.api.core.v1.Query](https://spaceone-dev.gitbook.io/api-reference/common-v1/search-query)|❌| |
| 2 | escalation_policy_id |string|❌| |
| 3 | name |string|❌| |
| 4 | domain_id |string|✅| |

### EscalationPolicyRequest
| No | Field | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | escalation_policy_id |string|✅| |
| 2 | domain_id |string|✅| |

### EscalationPolicyRules
| No | Field | Type |  Description |
| :--- | :--- | :--- | :--- |
| 1 | notification_level |string | |
| 2 | escalate_minutes |[int32](https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/type.proto) | |

### EscalationPolicyStatQuery
| No | Field | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | query |[spaceone.api.core.v1.StatisticsQuery](https://spaceone-dev.gitbook.io/api-reference/common-v1/statistics-query)|✅| |
| 2 | domain_id |string|✅| |

### GetEscalationPolicyRequest
| No | Field | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | escalation_policy_id |string|✅| |
| 2 | domain_id |string|✅| |
| 3 | only |list of string|❌| |

### UpdateEscalationPolicyRequest
<table>
  <thead>
    <tr>
      <th style="text-align:left">No</th>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">escalation_policy_id</td>
      <td style="text-align:left">string</td>
<td style="text-align:left">✅</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">name</td>
      <td style="text-align:left">string</td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">rules</td>
      <td style="text-align:left"><a href="escalation-policy.md#escalationpolicyrules">list of EscalationPolicyRules</a></td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">repeat_count</td>
      <td style="text-align:left"><a href="https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/type.proto">int32</a></td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">finish_condition</td>
      <td style="text-align:left"><ul>
          	<li>FINISH_CONDITION_NONE</li>
          	<li>ALL</li>
          	<li>HIGH_ONLY</li>
        </ul></td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">6</td>
      <td style="text-align:left">tags</td>
      <td style="text-align:left"><a href="https://github.com/protocolbuffers/protobuf/blob/master/src/google/protobuf/struct.proto">google.protobuf.Struct</a></td>
<td style="text-align:left">❌</td>
<td style="text-align:left"></td>
   </tr>
    <tr>
      <td style="text-align:left">7</td>
      <td style="text-align:left">domain_id</td>
      <td style="text-align:left">string</td>
<td style="text-align:left">✅</td>
<td style="text-align:left"></td>
   </tr>
  </tbody>
</table>

