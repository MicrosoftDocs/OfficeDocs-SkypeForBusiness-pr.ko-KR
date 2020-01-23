---
title: Azure Monitor를 사용 하 여 Microsoft 팀 회의실 장치 관리
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: 이 문서에서는 Azure Monitor를 사용 하 여 통합 된 방식으로 Microsoft 팀 회의실 장치를 관리 하는 방법을 설명 합니다.
ms.openlocfilehash: 33132d7d72498fd01a156ce28114d1e584d6760c
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269141"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure Monitor를 사용 하 여 Microsoft 팀 회의실 장치 관리

이 문서에서는 Azure Monitor를 사용 하 여 통합 된 방식으로 Microsoft 팀 회의실 장치를 관리 하는 방법을 설명 합니다.

Skype 회의실 장치를 관리 하는 데 도움이 되는 기본 원격 분석을 제공 하도록 Azure Monitor를 구성할 수 있습니다. 자세한 내용은 azure monitor를 [사용 하 여 Microsoft 팀 회의실 관리 계획](azure-monitor-plan.md) 및 [azure monitor를 사용 하 여 microsoft 팀 공간 관리 배포](azure-monitor-deploy.md) 를 참조 하세요. 관리 솔루션이 완성 됨에 따라 추가 데이터 및 관리 기능을 사용 하 여 디바이스 성능에 대 한 자세한 뷰를 만들 수 있습니다.

## <a name="understand-the-log-entries"></a>로그 항목 이해

다음 이벤트 설명은 Microsoft 팀 대화방 앱에서 Windows 이벤트 로그에 해당 정보를 기록할 때 5 분 마다 이벤트 로그 설명 필드에 삽입 됩니다. Microsoft Monitoring Agent는 azure monitor를 [사용 하 여 Microsoft 팀 공간 관리 배포](azure-monitor-deploy.md)에서 만든 대시보드로 이러한 레코드를 구문 분석 하는 데 사용할 수 있습니다. 대시보드를 사용 하 여 개별 로그 항목을 살펴보고 필요한 경우 작업 과정을 확인할 수 있습니다.

이벤트 Id 2000 및 3000는 해당 장치가 예상 대로 작동 하 고 있음을 나타냅니다. 이벤트 Id 2001 및 3001에서는 문제가 발견 되었음을 나타냅니다. 설정한 기준과 조직의 다른 배포 디바이스에 비해 이벤트 ID 4000에는 예상 보다 자주 표시 될 경우 작업이 필요할 수 있습니다.

이러한 이벤트 설명을 이해 하면 문제를 신속 하 게 알려 주는 알림과 추가 문제 해결을 위한 시작 지점을 제공 합니다.

| 이벤트&nbsp;ID&nbsp;수준|이벤트&nbsp;동작&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|이벤트&nbsp;설명&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 방법 | 이것은 정상 하트 비트 이벤트입니다. Microsoft 팀 대화방은 5 분 마다 Microsoft 팀 또는 비즈니스용 Skype에 로그인 되어 있고 네트워크 및 Exchange에 연결 되어 있는지 확인 합니다. <br> 세 가지 요소가 모두 참이 면 장치가 오프 라인 상태가 되거나 하나 이상의 조건이 더 이상 충족 되지 않을 때까지 5 분 마다 이벤트 ID 2000를 이벤트 로그에 기록 합니다. | {"설명": "하트 비트가 정상입니다.", "ResourceState": "정상", "OperationName": "하트 비트", "OperationResult": "Pass", "x": "Windows 10", "OSVersion": "10.0.14393.693", "Alias":<span></span>"alias @contoso .com," DisplayName ":" 표시 이름 "," appversion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" IP v6 주소 "} <br><br> 이 예제에서는 모든 하트 비트 조건이 충족 되었고 Microsoft 팀 대화방 장치가 정상 상태로 표시 되었습니다. 오류가 발생 한 경우 앱은 이벤트 ID 2001를 대신 기록 합니다. |
| 2001  <br> 오류 | 앱 오류 이벤트입니다. Microsoft 팀 대화방은 5 분 마다 네트워크 및 Exchange 연결을 사용 하 여 Microsoft 팀 또는 비즈니스용 Skype에 로그인 되어 있는지 확인 합니다. 하나 이상의 요소가 참이 아닌 경우, 장치가 오프 라인 상태가 되거나 모든 조건이 다시 충족 될 때까지 5 분 마다 이벤트 로그에 EventID 2001을 기록 합니다.  | {"설명": "네트워크 상태: 정상. Exchange 상태: 연결 됨. **로그인 상태: 비정상.** "," ResourceState ":" 비정상 "," OperationName ":" 하트 비트 "," OperationResult ":" Fail "," OS ":" Windows 10 "" 10.0.14393.693 "," Alias ":" 표시 이름 "," AppVersion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" ip v6 주소 "} <br><br>  이 예제에서 Microsoft 팀 대화방은 네트워크 연결이 정상이 고 앱이 Exchange에 연결 되었음을 확인 했지만 굵게 표시 된 부분은 앱이 연결 되지 않은 것을 나타냅니다. 장치 또는 호스트의 구성 문제일 수 있습니다.  <br> <br> 네트워크 상태가 정상 또는 비정상으로 표시 됩니다. 상태가 비정상 인 경우 네트워크 문제가 있거나 장치가 연결 되지 않았을 수 있으 나, 그 후에도 Exchange 및 Microsoft 팀 또는 비즈니스용 Skype 오류가 있는 것입니다.  <br><br> Exchange 상태가 연결 됨 또는 다음 중 하나로 표시 됩니다. 연결 끊김, 연결, AutodiscoveryError (가장 일반적으로 표시 되는 오류), 일반 오류 또는 ServerVersionNotSupported 지원 됩니다. 상태가 연결 중 이라면 다음 상태 메시지가 전송 될 때까지 대기 합니다. 다른 오류에 대해서는 Exchange 문제 해결에 대 한 경험을 통해 관리자의 문제를 참조 하세요.  <br><br>  로그인 상태 (앱이 로그인 되었음을 나타냄)가 정상 또는 비정상으로 표시 됩니다. 상태가 비정상 이면 기술 지원 담당자에 게 추가 조사를 보냅니다. |
| 3000  <br> 방법 | 이 이벤트는 하드웨어 검사가 실행 되었고 정상 인지 확인 합니다. Microsoft 팀 대화방 마다 실내 디스플레이, 마이크, 스피커, 카메라 등 구성 된 하드웨어 구성 요소가 연결 되 고 작동 하는지 확인 합니다. 모든 구성 요소가 정상 상태인 경우 이벤트 로그에 EventID 3000을 기록 합니다. 이 이벤트는 연결 된 장치에 문제가 있는 경우를 제외 하 고 5 분 마다 기록 됩니다.  <br> | {"설명": "HardwareCheckEngine이 정상입니다.", "ResourceState": "정상", "OperationName": "HardwareCheckEngine", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "<span></span>Alias @contoso," DisplayName ":" 표시 이름 "," appversion ":" IPv4Address "," 10.10.10.10 ":" 1.0.38.0 "," IPv6Address ":" ip v6 주소 "}  <br><br> 이 예제에서는 모든 하드웨어 검사를 통과 했습니다. 오류가 발생 한 경우 앱은 이벤트 ID 3001를 대신 기록 합니다. |
| 3001  <br> 오류 이벤트  | 하드웨어 오류 이벤트입니다. Microsoft 팀 대화방 앱에는 5 분 마다 연결 된 하드웨어 구성 요소의 상태를 확인 하는 프로세스 (회의실, 마이크, 스피커, 카메라 앞)가 있습니다. 하나 이상의 구성 요소가 비정상 이면 이벤트 로그에 EventID 3001을 기록 합니다. 이 이벤트는 디바이스의 문제가 해결 될 때까지 5 분 마다 기록 됩니다.   | {"설명": " **방 표시 상태:"가 비정상입니다.** 구성 된 표시 횟수는 2입니다. 실제 표시 개수는 0입니다. **회의 마이크 상태: 비정상.** 컨퍼런스 스피커 상태: 정상. 기본 스피커 상태: 정상. 카메라 상태: 정상. "," ResourceState ":" 비정상 "," OperationName ":" HardwareCheckEngine "," OperationResult ":" Fail "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.1198 "," Alias "" "별칭<span></span>@contoso .com", "DisplayName": "Yosemite 회의실", "appversion": "2.0.58.0", "10.10.10.10": "IPv6Address", "IPv4Address", "IPv6Address", "IPv4Address2": "10.10.10.10"} <br><br>  하드웨어 주변 기기는 정상 또는 비정상으로 표시 됩니다. <br> 이 예제에는 두 개의 채팅방 디스플레이가 구성 되어 있으며 현재는 둘 다 사용할 수 없습니다. 회의 마이크 상태가 비정상으로 되어 다양 한 원인이 발생할 수 있습니다. 적어도 하나 이상의 리소스가 검사를 통과 하지 못했으므로, ResourceState가 비정상으로 나열 됩니다. 추가 조사를 위해 기술자를 보냅니다. |
| 4000  <br> 방법  <br> | 앱 다시 시작 이벤트입니다. 앱이 다시 시작 될 때마다이 이벤트가 Windows 이벤트 로그에 기록 됩니다.  <br> | {"설명": "앱 다시 시작", "ResourceState": "정상", "OperationName": "" OperationResult "," Pass "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.693 "," Alias ":" Alias<span></span>@domain. "," DisplayName ":" 표시 이름 "," appversion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" ip v6 주소 "} <br><br> 다양 한 이유로 앱이 다시 시작 될 수 있습니다. 동일한 건물과 다른 건물에 있는 장치의 다시 시작 빈도를 비교 합니다. 이는 인프라 문제에 대 한 단서를 제공할 수 있으므로 파워 변동 및 오류와 같은 알려진 문제를 염두에 두어야 합니다.|

## <a name="see-also"></a>참고 항목
 

[Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 계획](azure-monitor-plan.md)

[Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 배포](azure-monitor-deploy.md)
