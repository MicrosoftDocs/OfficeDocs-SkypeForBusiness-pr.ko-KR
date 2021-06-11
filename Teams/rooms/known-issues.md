---
title: 알려진 문제
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
ms.collection:
- M365-collaboration
description: 관리자는 업데이트, 사용자 인터페이스Microsoft Teams 룸 하드웨어 및 제한 사항 및 예상 동작과 같은 알려진 문제 목록에 대해 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d601db3c028c7c93a97131db48de81bdcab314e4
ms.sourcegitcommit: bd7b4986044f7921b25506488dfed405fc2e7ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877490"
---
# <a name="known-issues"></a>알려진 문제 
 
이 문서에서는 기능 영역으로 Microsoft Teams 룸 알려진 문제를 나열합니다.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>업데이트 

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | KB 문서 |
|  ---        |      ---             |   ---            | --- |
| 애플리케이션이 시작되지 않습니다. |  애플리케이션 버전 4.4.41.0으로 업데이트한 후 시스템이 검은색 화면으로 부팅되거나 몇 분 후에 로그온 화면으로 전환됩니다. | 이 문제를 Microsoft Teams 룸 버전 [4.41.0으로](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) 업데이트한 후 애플리케이션이 시작되지 않는 경우의 단계를 따릅니다.  | 없음 |
|  콘텐츠 공유 후 모임 볼륨이 낮음         |   Microsoft Teams 룸 20H2 Windows 10 HDMI를 통해 콘텐츠를 공유한 후 미디어 및 모임 볼륨이 감소했습니다. 이 문제는 20H2의 오디오 Windows 10 발생했습니다. | 현재 이 문제의 해결방안은 없습니다. 모임 오디오 볼륨(예: 참가자 음성)에 미치는 영향을 줄이기 위해 모든 디바이스에서 HDMI 오디오를 Teams 룸 있습니다. Windows 10 팀에서 문제를 조사하고 있으며 해결이 발견될 때까지 고객 권고는 그대로 유지됩니다. | 없음 |
|  최신 앱         |    Microsoft Teams 룸 콘솔에는 "시스템 구성이 최신" 오류가 표시됩니다.                |   [복구 Microsoft Teams 룸 사용](recovery-tool.md)             |  없음 |
|  지원되지 않는 버전으로 업데이트된 디바이스 Windows 10   |    Windows 10 버전 1803에서 버전 1809로 업데이트된 디바이스는 지원되지 않습니다. 지원되는 버전은 1903입니다. |   지정한 기간 동안 기능 업데이트를 연기할 수 있는 [DeferFeatureUpdatesPeriodinDays](/windows/deployment/update/waas-configure-wufb) 설정에 대한 그룹 정책 또는 MDM 설정이 최대 365일로 설정되어 있는 경우 이 문제가 일어날 수 있습니다. <br><br> Windows 10 버전 1809는 지원되지 Microsoft Teams 룸 버전 1903이 지원됩니다. 그러나 2020년 3월 27일 현재 버전 1809는 365일이 넘습니다. 이 설정이 변경되지 않은 경우 Windows 버전 1809를 설치하려고 시도하면 문제가 발생할 수 Microsoft Teams 룸.<br><br>이 상황을 방지하려면 업데이트 **연기에** 대한 그룹 정책 또는 MDM 설정을 제거합니다. 이렇게 하면 Windows 지원되는 최신 OS 버전으로 업데이트할 수 있습니다. <br><br>**중요** 그룹 정책 또는 MDM  설정을 제거해야 합니다(구성되지 않은 왼쪽) **을 0으로 설정하지 않습니다.** 정책이 0으로 설정되어 있는 Windows 지원되지 않을 수 있는 최신 사용 가능한 버전을 사용하게 됩니다. |  없음 |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>사용자 인터페이스 

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | KB 문서 |
|  ---        |      ---             |   ---            | --- |
|가상 키보드가 누락된 경우   | 가상 키보드에 정보를 입력해야 할 때 나타나지 Microsoft Teams 룸. 이 문제는 버전 Windows 10 1903에서 발생합니다. | x64 기반 시스템에 대한 Windows 10 2020-04 누적 업데이트를 Windows 설치합니다.  | 없음 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>하드웨어

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | KB 문서 |
|  ---        |      ---             |   ---            |   --- |
| 모니터가 검색되지 않은 경우 | Microsoft Teams 룸(모델 2017) Surface Pro 장치에서 실행하면 모니터가 검색되지 않습니다. |  전원 단추를 Surface Pro 20초 이상 누릅니다. 이 작업을 실행하면 디바이스가 다시 시작하고 그래픽 캐시를 지우게 됩니다. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>제한 사항 및 예상 동작

***

Microsoft Teams 룸 HDMI 인제스트 기능(비디오, 오디오)에 문제가 발생하기 위해 관찰된 HDCP 입력을 지원하지 않습니다. 스위치에 연결된 스위치가 HDCP 옵션을 Microsoft Teams 룸 있는지 주의하세요. 

***

대기 모드에서 해제할 때 룸 전면 디스플레이가 활성 비디오 원본(예: MTR 콘솔)으로 자동으로 전환하려면 특정 조건을 충족해야 합니다. 이 기능은 선택 사항이지만 기본 Microsoft Teams 룸 소프트웨어에서 지원됩니다. 기본 하드웨어가 기능을 지원합니다. 전면 디스플레이로 사용되는 소비자 TV는 HDMI의 CEC(소비자 전자 제어) 기능을 지원해야 합니다.  선택한 도크 또는 콘솔(CEC를 지원하지 않을 수 있는 제조업체 지원 설명서 참조)에 따라 Crestron의 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 또는 [Extron의 Extron HD CTL 100과](https://www.extron.com/article/hdctl100ad) 같은 컨트롤러가 필요한 경우 원하는 동작을 사용하도록 설정할 수 있습니다. 

***

항상 유선 1-Gbps 네트워크 연결을 사용하여 필요한 대역폭을 보장합니다. 

***

Microsoft Teams 룸 디바이스가 도메인에 대한 신뢰를 잃는 경우 디바이스에 인증하고 해당 디바이스를 열 수 설정. 예를 들어 도메인에 Microsoft Teams 룸 도메인에서 도메인을 제거하면 신뢰가 손실됩니다. 해결은 로컬 관리자 계정으로 로그인하는 것입니다. 
***
Microsoft Teams 룸 애플리케이션은 다중 창 애플리케이션으로, 앱이 올바르게 작동하려면 디바이스의 HDMI 포트에 연결된 전면 디스플레이가 필요합니다. 테스트 중이고 아직 디스플레이를 구매하지 않은 경우 HDMI 디스플레이가 연결되어 있는지 확인하거나 더미 HDMI 플러그를 사용해야 합니다.
***
<a name="See"> </a>  
## <a name="see-also"></a>참고 항목

[Microsoft Teams 룸 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 룸 관리](rooms-manage.md)
