---
title: Azure Monitor를 사용하여 Microsoft Teams 룸 디바이스 모니터링
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: 이 문서에서는 Azure Monitor를 사용하여 Microsoft Teams 룸 디바이스를 통합 방식으로 모니터링하는 방법을 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38238d4b1d0bc33182f002e7dcf6389028315c48
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880212"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure Monitor를 사용하여 Microsoft Teams 룸 디바이스 모니터링

이 문서에서는 Azure Monitor를 사용하여 통합된 방식으로 Microsoft Teams 룸 모니터링하는 방법을 설명합니다.

Microsoft Teams 회의실 디바이스를 모니터링하는 데 도움이 되는 기본 원격 분석을 제공하도록 Azure Monitor를 구성할 수 있습니다. 자세한 내용은 [Azure Monitor를 사용하여 계획 Microsoft Teams 룸 관리](azure-monitor-plan.md) 및 [Azure Monitor를 사용하여 Microsoft Teams 룸 관리 배포](azure-monitor-deploy.md)를 참조하세요. 모니터링 솔루션이 완성되면 다른 데이터 및 모니터링 기능을 사용하여 디바이스 성능에 대한 보다 자세한 보기를 만들 수 있습니다.

## <a name="understand-the-log-entries"></a>로그 항목 이해

다음 이벤트 설명은 Microsoft Teams 룸 앱이 Windows 이벤트 로그에 해당 정보를 기록하는 경우 5분마다 이벤트 로그 설명 필드에 삽입됩니다. Microsoft Monitoring Agent는 이러한 레코드를 Azure Monitor의 Log Analytics에 전달하여 Azure Monitor를 사용하여 [배포 Microsoft Teams 룸 모니터링](azure-monitor-deploy.md)에서 만든 대시보드로 구문 분석합니다. 대시보드를 사용하여 개별 로그 항목을 확인하여 필요한 경우 작업 과정을 확인할 수 있습니다.

이벤트 ID 2000 및 3000은 Teams 룸 예상대로 작동함을 나타냅니다. 이벤트 ID 2001 및 3001은 문제가 발견되었음을 나타냅니다. 이벤트 ID 4000은 설정한 기준 또는 조직의 다른 배포된 디바이스에 비해 예상보다 자주 표시되는 경우 작업이 필요할 수 있습니다.

이러한 이벤트 설명을 이해하면 문제를 신속하게 알리고 추가 문제 해결을 위한 시작점을 제공합니다.

| 이벤트&nbsp;ID&nbsp;수준|이벤트&nbsp;동작&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|이벤트&nbsp;설명&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 정보 | 이것은 건강한 하트비트 이벤트입니다. 5분마다 Microsoft Teams 룸 Microsoft Teams 또는 비즈니스용 Skype 로그인하고 네트워크 및 Exchange 연결이 있는지 확인합니다. <br> 세 가지 요소가 모두 true이면 디바이스가 오프라인 상태가 되거나 하나 이상의 조건이 더 이상 충족되지 않을 때까지 5분마다 이벤트 ID 2000을 이벤트 로그에 기록합니다. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> 이 예제에서는 모든 하트비트 조건이 충족되었고 Microsoft Teams 룸 디바이스가 정상으로 표시되었습니다. 오류가 있는 경우 앱은 이벤트 ID 2001을 대신 기록합니다. |
| 2001  <br> 오류 | 앱 오류 이벤트입니다. 5분마다 Microsoft Teams 룸 Microsoft Teams에 로그인했거나 네트워크 및 Exchange 연결로 비즈니스용 Skype 확인합니다. 하나 이상의 요소가 true가 아닌 경우 디바이스가 오프라인 상태이거나 모든 조건이 다시 충족될 때까지 5분마다 EventID 2001을 이벤트 로그에 기록합니다.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Sign in status: Unhealthy. Teams sign in status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  이 예제에서 Microsoft Teams 룸 네트워크 연결이 정상이고 앱이 Exchange에 연결되었음을 확인했지만 굵게 표시된 부분은 앱이 연결되어 있지 않음을 나타냅니다. 디바이스 또는 호스트의 구성 문제일 수 있습니다.  <br> <br> 네트워크 상태는 정상 또는 비정상으로 표시됩니다. 상태가 비정상 상태인 경우 네트워크 문제가 있거나 디바이스가 분리되었을 수 있습니다(하지만 Exchange 및 Microsoft Teams 또는 비즈니스용 Skype 오류도 있을 수 있음).  <br><br> Exchange 상태는 연결 끊김, 연결 끊김, AutodiscoveryError(가장 일반적으로 표시되는 오류), GeneralError 또는 ServerVersionNotSupported 중 하나로 표시됩니다. 상태가 연결 중이면 다음 상태 메시지가 전송될 때까지 기다립니다. 다른 오류는 Exchange 문제 해결 경험이 있는 관리자에게 문제를 참조하세요.  <br><br>  _로그인 상태_/_Teams 로그인 상태_(앱이 비즈니스용 Skype 또는 Teams에 로그인되었음을 나타낸다)는 _정상_ 또는 _비정상_ 으로 표시됩니다. 상태가 비정상 상태인 경우 기술자를 보내 더 자세히 조사합니다. |
| 3000  <br> 정보 | 이 이벤트는 하드웨어 검사가 실행되었으며 정상으로 확인되었는지 확인합니다. 5분마다 Microsoft Teams 룸 실내 디스플레이, 마이크, 스피커 및 카메라와 같은 구성된 하드웨어 구성 요소가 연결되고 작동하는지 확인합니다. 모든 구성 요소가 정상이면 EventID 3000을 이벤트 로그에 씁니다. 이 이벤트는 연결된 디바이스에 문제가 없는 한 5분마다 작성됩니다.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 이 예제에서는 모든 하드웨어 검사가 통과되었습니다. 오류가 있는 경우 앱은 이벤트 ID 3001을 대신 기록합니다. |
| 3001  <br> 오류 이벤트  | 하드웨어 오류 이벤트입니다. Microsoft Teams 룸 앱에는 5분마다 연결된 하드웨어 구성 요소(방 앞, 마이크, 스피커, 카메라)의 상태를 확인하는 프로세스가 있습니다. 하나 이상의 구성 요소가 비정상이면 EventID 3001을 이벤트 로그에 씁니다. 이 이벤트는 디바이스 문제가 해결될 때까지 5분마다 기록됩니다.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  하드웨어 주변 장치는 정상 또는 비정상으로 표시됩니다. <br> 이 예제에서는 _두 개의 전면_ 디스플레이가 구성되어 있으며 현재 둘 다 사용할 수 없습니다. _회의 마이크 상태가_ _비정상_ 상태이므로 몇 가지 원인이 있을 수 있습니다. 하나 이상의 리소스가 검사를 통과하지 못했기 때문에 ResourceState는 비정상으로 나열됩니다. 추가 조사를 위해 기술자를 보냅니다. |
| 4000  <br> 정보  <br> | 앱 다시 시작 이벤트입니다. 앱을 다시 시작할 때마다 이 이벤트를 Windows 이벤트 로그에 기록합니다.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 앱은 여러 가지 이유로 다시 시작될 수 있습니다. 동일한 건물과 다른 건물에 있는 장치의 재시작 빈도를 비교합니다. 인프라 문제에 대한 단서를 제공할 수 있으므로 전력 변동 및 오류와 같은 알려진 문제에 유의하세요.|

## <a name="related-topics"></a>관련 항목
 

[Azure Monitor를 사용하여 Microsoft Teams 룸 모니터링 계획](azure-monitor-plan.md)

[Azure Monitor를 사용하여 Microsoft Teams 룸 모니터링 배포](azure-monitor-deploy.md)
