---
title: 알려진 문제
ms.author: v-lanac
author: lanachin
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
description: 관리자는 업데이트, 사용자 인터페이스, 하드웨어, 제한 사항, 예상 동작 등 Microsoft 팀 대화방의 알려진 문제 목록에 대해 알아볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 584b71d39552990b3e4009efb177ef4fee61f1a4
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761344"
---
# <a name="known-issues"></a>알려진 문제 
 
이 문서에는 Microsoft 팀 대화방의 알려진 문제점에 대 한 기능 영역별로 나와 있습니다.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Update 

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | 기술 자료 문서 |
|  ---        |      ---             |   ---            | --- |
| 응용 프로그램이 시작 되지 않음 |  응용 프로그램 버전 4.4.41.0로 업데이트 한 후 시스템에서 검은색 화면으로 부팅 하거나 몇 분 후에 로그온 화면으로 이동 합니다. | 이 문제를 해결 하려면 Microsoft 팀 대화방의 단계를 수행 하 여 [버전 4.4.41.0로 업데이트 한 후 응용 프로그램을 시작 하지](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) 않습니다.  | 없음 |
|  SfB 모임 콘텐츠 공유가 전체 화면을 표시 하지 않음         |    비즈니스용 Skype 모임에서 높은 DPI 설정을 사용 하는 채팅방에는 모임에 공유 된 콘텐츠에 회의실 표시 앞면의 전체 화면이 표시 되지 않는 문제가 발생할 수 있습니다. 이는 Windows 10 RDP (원격 데스크톱 프로토콜) API의 기본 문제로 인해 발생 합니다. | `<WinRTRdpEnabled>`이 문제를 해결 하려면 XML 설정을 사용 하 여 Windows 10 RDP API를 사용 하지 않도록 설정 합니다. 사용 하지 않도록 설정 하려면 값을로 지정 해야 `false` 합니다. 자세한 내용은 [XML 구성 파일을 사용 하 여 콘솔 설정 관리](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)를 참조 하세요. | 없음 |
|  앱이 만료 되었습니다.         |    Microsoft 팀 회의실 콘솔에 "시스템 구성 오래 됨" 오류가 표시 됩니다.                |   [Microsoft 팀 대화방 복구 도구 사용](recovery-tool.md)             |  없음 |
|  장치가 지원 되지 않는 버전의 Windows 10으로 업데이트 됨   |    Windows 10 장치가 버전 1803에서 버전 1809 (지원 되지 않음)로 업데이트 되었습니다. 지원 되는 버전은 1903입니다. |   이 문제는 지정 된 일 수 동안 기능 업데이트를 지연할 수 있는 [DeferFeatureUpdatesPeriodinDays setting에 대 한 그룹 정책 또는 MDM 설정이](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) 최대 365 일로 설정 된 경우에 발생할 수 있습니다. <br><br> Windows 10 버전 1809는 Microsoft 팀 대화방에서 지원 되지 않으며 버전 1903이 지원 됩니다. 그러나, 3 월 27 일 현재 2020 버전 1809은 365 일이 하를 초과 합니다. 이 설정이 변경 되지 않으면 Windows에서 버전 1809를 설치 하려고 시도 하며,이 경우 Microsoft 팀 대화방에 문제가 발생할 수 있습니다.<br><br>이 문제를 방지 하려면 업데이트 지연에 대 한 그룹 정책 또는 MDM 설정을 **제거** 합니다. 이렇게 하면 Windows에서 지원 되는 최신 OS 버전으로 업데이트할 수 있습니다. <br><br>**중요** 그룹 정책 또는 MDM 설정을 **제거** (왼쪽에 구성 취소) 하 고 **0으로 설정 하지**않아야 합니다. 정책이 0으로 설정 되 면 Windows에서 지원 되지 않을 수 있는 최신 버전을 사용 합니다. |  없음 |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>사용자 인터페이스 

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | 기술 자료 문서 |
|  ---        |      ---             |   ---            | --- |
|가상 키보드가 없음   | Microsoft 팀 대화방에 정보를 입력 해야 하는 경우 가상 키보드가 표시 되지 않습니다. 이 문제는 Windows 10 버전 1903에서 발생 합니다. | Windows 10에 대 한 2020-04 누적 업데이트 설치, x64 기반 시스템에 대 한 windows 업데이트 (버전 1903)  | 없음 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>하드웨어

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | 기술 자료 문서 |
|  ---        |      ---             |   ---            |   --- |
| 감지 되지 않은 모니터 | Surface Pro (모델 2017) 장치에서 Microsoft 팀 대화방을 실행 하면 모니터가 검색 되지 않습니다. |  Surface Pro 전원 단추를 20 초 이상 누르고 있습니다. 이렇게 하면 장치가 다시 시작 되 고 그래픽 캐시가 지워집니다. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>제한 사항 및 예상 동작

***

Microsoft 팀 대화방은 HDMI 수집 기능 (비디오, 오디오)에 문제가 발생 하는 데 관측 된 HDCP 입력을 지원 하지 않습니다. Microsoft 팀 대화방에 연결 된 스위치에 HDCP 옵션이 설정 되어 있는지 확인 합니다. 

***

원본에서 대기 모드를 해제할 때 자동으로 활성 비디오 원본 (예: MTR 콘솔)으로 전환 하려면 특정 조건이 충족 되어야 합니다. 이 기능은 선택 사항 이지만 Microsoft 팀 공간 소프트웨어에서 지원 되며, 기본 하드웨어에서 기능을 지 원하는 경우 제공 됩니다. 채팅방 표시로 사용 되는 소비자 TV는 HDMI의 CEC (소비자 전자 컨트롤) 기능을 지원 해야 합니다.  선택 된 dock 또는 console (CEC를 지원 하지 않을 수 있음) (제조업체 지원 문서 참조)에 따라 원하는 동작을 사용 하도록 설정 하려면 [HD CTL 100의 extron](https://www.extron.com/article/hdctl100ad) 작업 영역 컨트롤러가 필요할 수 있습니다. 

***

항상 유선 1 Gbps 네트워크 연결을 사용 하 여 필요한 대역폭을 보유 하 고 있는지 확인 합니다. 

***

Microsoft 팀 대화방 장치가 도메인에서 신뢰를 상실 한 경우에는 디바이스에 인증 하 고 설정을 열 수 없게 됩니다. 예를 들어 도메인에 가입한 후 도메인에서 Microsoft 팀 대화방을 제거 하면 신뢰가 손실 됩니다. 해결 방법은 로컬 관리자 계정으로 로그인 하는 것입니다. 
***
Microsoft 팀 대화방은 다중 창 응용 프로그램 이므로 장치의 HDMI 포트에 연결 하 여 앱이 올바르게 작동 하도록 하는 방 디스플레이가 앞에 있어야 합니다. 테스트 하는 경우에는 HDMI 디스플레이가 연결 되어 있는지 확인 하 고, 아직 표시를 구매 하지 않은 경우에는 dummy HDMI 플러그를 사용 해야 합니다.
***
<a name="See"> </a>  
## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 룸 관리](rooms-manage.md)
