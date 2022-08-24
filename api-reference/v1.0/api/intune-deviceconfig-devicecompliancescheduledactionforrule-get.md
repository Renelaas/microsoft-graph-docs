---
title: "Get deviceComplianceScheduledActionForRule"
description: "Read properties and relationships of the deviceComplianceScheduledActionForRule object."
author: "dougeby"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# Get deviceComplianceScheduledActionForRule

Namespace: microsoft.graph

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Read properties and relationships of the [deviceComplianceScheduledActionForRule](../resources/intune-deviceconfig-devicecompliancescheduledactionforrule.md) object.

## Prerequisites
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}?$expand=scheduledActionsForRule($expand=scheduledActionConfigurations)
```

## Optional query parameters
This method supports the [OData Query Parameters](/graph/query-parameters) to help customize the response.

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and [deviceComplianceScheduledActionForRule](../resources/intune-deviceconfig-devicecompliancescheduledactionforrule.md) object in the response body.

## Example

### Request
Here is an example of the request.
``` http
GET https://graph.microsoft.com/1.0/deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}?$expand=scheduledActionsForRule($expand=scheduledActionConfigurations)
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 188
{
    "@odata.context":  "https://graph.microsoft.com/v1.0/$metadata#deviceManagement/deviceCompliancePolicies(scheduledActionsForRule(scheduledActionConfigurations()))/$entity",
    "@odata.type": "#microsoft.graph.windows10CompliancePolicy",
    "id": "{Compliance Policy ID}",
    "createdDateTime": "Date value",
    "description": "Description value",
    "lastModifiedDateTime": "date value",
    "displayName": "Displayname",
    "version": 1,
    "passwordRequired": true,
    "passwordBlockSimple": false,
    "passwordRequiredToUnlockFromIdle": false,
    "passwordMinutesOfInactivityBeforeLock": 5,
    "passwordExpirationDays": 180,
    "passwordMinimumLength": 8,
    "passwordMinimumCharacterSetCount": null,
    "passwordRequiredType": "deviceDefault",
    "passwordPreviousPasswordBlockCount": 24,
    "requireHealthyDeviceReport": false,
    "osMinimumVersion": null,
    "osMaximumVersion": null,
    "mobileOsMinimumVersion": null,
    "mobileOsMaximumVersion": null,
    "earlyLaunchAntiMalwareDriverEnabled": false,
    "bitLockerEnabled": true,
    "secureBootEnabled": true,
    "codeIntegrityEnabled": true,
    "storageRequireEncryption": true,
    "scheduledActionsForRule@odata.context": "https://graph.microsoft.com/v1.0/$metadata#deviceManagement/deviceCompliancePolicies('{Compliance Policy ID}')/microsoft.graph.windows10CompliancePolicy/scheduledActionsForRule(scheduledActionConfigurations())",
    "scheduledActionsForRule": [
        {
            "id": "{Compliance Policy ID}",
            "ruleName": null,
            "scheduledActionConfigurations@odata.context": "https://graph.microsoft.com/v1.0/$metadata#deviceManagement/deviceCompliancePolicies('{Compliance Policy ID}')/microsoft.graph.windows10CompliancePolicy/scheduledActionsForRule('{Compliance Policy ID}')/scheduledActionConfigurations",
            "scheduledActionConfigurations": [
                {
                    "id": "{scheduled action ID}",
                    "gracePeriodHours": 0,
                    "actionType": "block",
                    "notificationTemplateId": "00000000-0000-0000-0000-000000000000",
                    "notificationMessageCCList": []
                }
            ]
        }
    ]
}
```





