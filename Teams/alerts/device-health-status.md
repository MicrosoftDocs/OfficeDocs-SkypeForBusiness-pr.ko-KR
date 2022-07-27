---
title: Microsoft Teams 디바이스 모니터링 및 경고
author: cazawideh
ms.author: czawideh
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 모니터링 및 경고 기능을 사용하여 Teams 디바이스의 상태를 사전에 모니터링하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 81994e3462fe678c40506d6a11b343ba733995cd
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023809"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams 디바이스 상태 모니터링

Microsoft Teams 관리 센터의 디바이스 상태 모니터링은 다양한 Teams 디바이스의 상태를 사전에 모니터링하는 기능을 제공합니다. 조직의 모니터링된 디바이스가 오프라인 상태가 되면 디바이스의 오프라인 상태를 모니터링하고 실시간으로 경고를 수신합니다.  

시작하기 전에 테넌트에 팀/채널 만들기 권한이 필요합니다. [자세히 알아보세요](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>디바이스 상태 규칙 구성

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **알림 & 경고** > **규칙을** 선택합니다.

   ![관리 센터의 규칙 섹션입니다.](../media/select-rules.png)

2. **규칙** 페이지에서 **디바이스 상태 규칙을** 선택합니다.

3. 디바이스를 선택하여 경고를 사용하도록 설정하는 상태 규칙을 구성합니다.

    ![Teams 디바이스 상태 규칙 페이지.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>규칙 구성 해석


|필드 |설명  |
|--------|-------------|
|**규칙 유형**   |디바이스 상태 규칙은 효과적으로 관리하는 데 도움이 됩니다. Teams 디바이스 및 디바이스 관리 유형으로 분류됩니다. 나중에 디바이스 관리 유형의 더 많은 규칙을 사용하여 다른 관련 기능을 모니터링할 수 있습니다(예: 비정상 디바이스 및 디바이스의 로그인 상태 포함).|
|**조건**   |디바이스가 오프라인으로 전환되면 디바이스의 상태를 모니터링할 수 있습니다. Teams 관리 센터의 디바이스 관리에 대해 [자세히 알아봅니](../devices/device-management.md)다. |
|**범위**   |규칙 평가 빈도를 언급하여 디바이스 상태를 모니터링할 빈도를 지정할 수 있습니다. 기본적으로 팀 디바이스는 오프라인으로 전환할 경우 거의 실시간으로 모니터링됩니다. |
|**디바이스 사용자**   |로그인한 사용자를 기반으로 하여 사전 예방적 오프라인 조각상 모니터링이 필요한 디바이스를 지정할 수 있습니다. 자세한 내용은 [구성에 대한 디바이스 선택을](#select-devices-for-configuration) 참조하세요. |
|**작업** >  **채널 경고**   |작업 섹션에서 경고를 받을 팀 채널을 지정할 수 있습니다. 현재 관리 **경고 및 알림이라는** 기본 팀과 **MonitoringAlerts** 라는 채널이 만들어집니다. 여기서 알림이 전달됩니다. <BR/> <BR/> 테넌트에서 전역 관리자 및 Teams 관리자가 이 기본 팀에 자동으로 추가됩니다.|
|**작업** >  **웹후크 (웹후크)**   |외부 웹후크를 사용하여 알림을 받을 수도 있습니다(선택 사항). JSON 알림 페이로드가 전송될 웹후크 섹션에서 외부 공용 웹후크 URL을 지정합니다. <BR/> <BR/>  웹후크를 통해 알림 페이로드를 조직의 다른 시스템과 통합하여 사용자 지정 워크플로를 만들 수 있습니다.<br/><br/> 

**웹후크에 대한 JSON 페이로드 스키마:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string"} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **샘플 JSON 페이로드**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         "DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": "Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>구성을 위한 디바이스 선택

1. 해당 디바이스에 로그인한 사용자를 선택하여 모니터링하려는 Teams 디바이스를 선택할 수 있습니다. **디바이스 사용자** 섹션에서 **추가** 를 선택합니다.

2. 디바이스 상태를 모니터링할 사용자를 하나 이상 선택합니다.

   ![디바이스 상태 규칙에 사용자를 추가합니다.](../media/select-device-users.png )

   선택한 사용자 목록은 **디바이스 사용자** 섹션에 표시됩니다. 사용자를 추가하거나 제거하여 이 목록을 수정할 수 있습니다.

선택한 사용자 목록에서 사용하는 모든 로그인 디바이스는 오프라인 상태에 대해 모니터링됩니다.

## <a name="notifications-in-teams-client"></a>Teams 클라이언트의 알림

알림은 **관리 경고 및 알림** 팀의 자동 생성된 **MonitoringAlerts** 채널에 전달됩니다. 디바이스가 오프라인으로 전환된 후 15분 이내에 경고가 수신됩니다. 

디바이스 오프라인 알림에는 다음 정보가 포함될 수 있습니다.

- 오프라인 상태인 디바이스 이름입니다.
- 오프라인 디바이스의 사용자입니다.
- 디바이스가 오프라인 상태가 된 시간입니다. (현재 시간은 UTC로 표시됩니다.)
- 경고를 발생시킨 규칙의 유형입니다.
- 경고가 발생하는 이유입니다.
