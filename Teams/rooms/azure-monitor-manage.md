---
title: Azure Monitor를 사용하여 Microsoft Teams Rooms 디바이스 관리
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: 이 문서에서는 Azure Monitor를 사용하여 통합된 방식으로 Microsoft Teams Rooms 디바이스를 관리하는 방법에 대해 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41375c313940099b6ed6e102e2452290e0817bec
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874768"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure Monitor를 사용하여 Microsoft Teams Rooms 디바이스 관리

이 문서에서는 Azure Monitor를 사용하여 통합된 방식으로 Microsoft Teams Rooms 디바이스를 관리하는 방법에 대해 설명합니다.

Microsoft Teams 회의실 디바이스를 관리할 수 있도록 기본 원격 분석 기능을 제공하도록 Azure Monitor를 구성할 수 있습니다. 자세한 [내용은 Azure Monitor를](azure-monitor-plan.md) 사용하여 Microsoft Teams Rooms 관리 계획 및 [Azure Monitor를](azure-monitor-deploy.md) 사용하여 Microsoft Teams Rooms 관리 배포를 참조하세요. 관리 솔루션이 성숙하면 추가 데이터 및 관리 기능을 사용하여 디바이스 성능에 대한 자세한 보기를 만들 수 있습니다.

## <a name="understand-the-log-entries"></a>로그 항목 이해

Microsoft Teams Rooms 앱이 Windows 이벤트 로그에 해당 정보를 기록할 때 다음 이벤트 설명은 5분마다 이벤트 로그 설명 필드에 삽입됩니다. Microsoft Monitoring Agent는 이러한 레코드를 Azure Monitor의 Log Analytics로 전달하여 Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 배포에서 만든 대시보드로 [구문 분석합니다.](azure-monitor-deploy.md) 대시보드를 사용하여 개별 로그 항목을 보고 필요한 경우 작업 과정을 확인할 수 있습니다.

이벤트 아이디 2000 및 3000은 해당 디바이스가 예상대로 작동하고 있는 것을 나타냅니다. 이벤트 아이디 2001 및 3001은 문제가 발견된 것을 나타냅니다. 이벤트 ID 4000은 설정한 기준 또는 조직의 다른 배포된 디바이스에 비해 예상보다 더 자주 볼 수 있는 경우 작업이 필요할 수 있습니다.

이러한 이벤트 설명을 이해하면 문제를 신속하게 경고하고 추가 문제 해결을 위한 시작점을 제공합니다.

| 이벤트 &nbsp; ID &nbsp; 수준|이벤트 &nbsp; 동작&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|이벤트 &nbsp; 설명&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 정보 | 이는 건강한 하트비트 이벤트입니다. 5분마다 Microsoft Teams Rooms는 Microsoft Teams 또는 Skype for Business에 로그인하고 네트워크 및 Exchange 연결이 있는지 확인합니다. <br> 3개 요소가 모두 true이면 디바이스가 오프라인 상태이거나 하나 이상의 조건이 더 이상 충족되지 때까지 5분마다 이벤트 로그에 이벤트 ID 2000을 기록합니다. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> 이 예제에서는 모든 하트비트 조건이 충족되어 Microsoft Teams Rooms 디바이스가 정상으로 표시되었습니다. 오류가 있는 경우 앱은 이벤트 ID 2001을 대신 기록합니다. |
| 2001  <br> 오류 | 앱 오류 이벤트입니다. 5분마다 Microsoft Teams Rooms는 네트워크 및 Exchange 연결을 통해 Microsoft Teams 또는 비즈니스용 Skype에 로그인하는지 확인합니다. 하나 이상의 요소가 true가 아닌 경우 디바이스가 오프라인 상태이거나 모든 조건이 다시 충족될 때까지 5분마다 EventID 2001을 이벤트 로그에 기록합니다.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  이 예제에서 Microsoft Teams Rooms는 네트워크 연결이 정상이고 앱이 Exchange에 연결되어 있는지 결정했지만 굵게 표시된 부분은 앱이 연결되지 않았다는 것입니다. 디바이스 또는 호스트의 구성 문제일 수 있습니다.  <br> <br> 네트워크 상태는 정상 상태 또는 정상 상태로 표시됩니다. 상태가 상태가 이상한 경우 네트워크 문제가 발생하거나 디바이스가 연결되지 않은 것일 수 있습니다(Exchange 및 Microsoft Teams 또는 비즈니스용 Skype 오류도 있을 수 있습니다).  <br><br> Exchange 상태는 연결 끊기, 연결 해제, AutodiscoveryError(가장 일반적으로 볼 수 있는 오류), GeneralError 또는 ServerVersionNotSupported 중 하나인 연결 상태 또는 다음 중 하나로 표시됩니다. 상태가 연결 중이면 다음 상태 메시지가 전송될 때까지 기다렸다가 다른 오류가 발생하면 Exchange 문제 해결 경험이 있는 관리자에게 문제를 참조하세요.  <br><br>  로그인 _상태(앱이_ 로그인되었음을 나타내는)는 정상 또는  정상 상태로 _표시됩니다._ 상태가 상태가 이상한 경우 기술자에게 보내 추가 조사를 진행합니다. |
| 3000  <br> 정보 | 이 이벤트는 하드웨어 검사를 실행하고 정상인 것으로 확인했습니다. Microsoft Teams Room은 5분마다 회의실 디스플레이, 마이크, 스피커 및 카메라와 같은 구성한 하드웨어 구성 요소가 연결되고 작동하는지 확인합니다. 모든 구성 요소가 정상인 경우 EventID 3000을 이벤트 로그에 쓴다. 연결된 디바이스에 문제가 없는 경우 이 이벤트는 5분마다 작성됩니다.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 이 예제에서는 모든 하드웨어 검사가 전달됩니다. 오류가 있는 경우 앱은 이벤트 ID 3001을 대신 기록합니다. |
| 3001  <br> 오류 이벤트  | 하드웨어 오류 이벤트입니다. Microsoft Teams Rooms 앱은 5분마다 연결된 하드웨어 구성 요소(회의실, 마이크, 스피커, 카메라)의 상태 확인 프로세스가 있습니다. 하나 이상의 구성 요소가 이상한 경우 EventID 3001을 이벤트 로그에 기록합니다. 이 이벤트는 디바이스 문제가 해결될 때까지 5분마다 작성됩니다.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  하드웨어 주변 장치를 정상 또는 정상 상태로 표시됩니다. <br> 이 예제에서는 두  개의 전면 디스플레이가 구성된 것으로, 현재 둘 중 하나를 사용할 수 없습니다. 회의 _마이크 상태는_ 여러 가지 가능한 원인이 있을 수 있는 상태가 손상되지 않습니다.  하나 이상의 리소스가 검사를 통과하지 못했기 때문에 ResourceState는 Unhealthy로 나열됩니다. 추가 조사를 위해 기술자에게 보내기. |
| 4000  <br> 정보  <br> | App Restart 이벤트입니다. 앱이 다시 시작될 때마다 이 이벤트를 Windows 이벤트 로그에 기록합니다.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 앱은 다양한 이유로 다시 시작할 수 있습니다. 동일한 건물과 다른 건물에서 디바이스의 다시 시작 빈도를 비교합니다. 전원 변동 및 오류와 같은 알려진 문제를 염두에 두면 인프라 문제에 대한 단서가 제공될 수 있습니다.|

## <a name="related-topics"></a>관련 주제
 

[Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 계획](azure-monitor-plan.md)

[Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 배포](azure-monitor-deploy.md)
