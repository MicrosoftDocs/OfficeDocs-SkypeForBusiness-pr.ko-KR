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
description: 관리자는 업데이트, 사용자 인터페이스, 하드웨어 및 제한 사항 및 예상 동작을 포함하여 Microsoft Teams 회의실에 대한 알려진 문제 목록에 대해 알 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c32e35f0ea95d81fcb597c18a12a8f48fe4c7b2
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662633"
---
# <a name="known-issues"></a>알려진 문제 
 
이 문서에서는 기능 영역의 Microsoft Teams 회의실에 대해 알려진 문제를 나열합니다.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>업데이트 

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | KB 문서 |
|  ---        |      ---             |   ---            | --- |
| 애플리케이션이 시작되지 않는 경우 |  애플리케이션 버전 4.4.41.0으로 업데이트한 후 시스템이 검은색 화면으로 부팅되거나 몇 분 후에 로그온 화면으로 이동됩니다. | 이 문제를 해결하기 위해 [버전 4.4.41.0으로](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) 업데이트한 후 Microsoft Teams Rooms 애플리케이션의 단계에 따라 시작되지 않습니다.  | 없음 |
|  SfB 모임 콘텐츠 공유에 전체 화면이 표시되지 않습니다.         |    비즈니스용 Skype 모임에서 높은 DPI 설정을 사용하여 회의실 앞에 회의실이 표시될 경우 모임에 공유된 콘텐츠가 회의실 디스플레이 전면에 전체 화면이 표시되지 않는 문제가 있을 수 있습니다. 이는 Windows 10 RDP(원격 데스크톱 프로토콜) API의 기반 문제로 인해 발생했습니다. | `<WinRTRdpEnabled>`XML 설정을 사용하여 Windows 10 RDP API를 사용하지 않도록 설정하여 이 문제를 해결합니다. 사용하지 않도록 설정하려면 값을 으로 지정해야 `false` 합니다. 자세한 내용은 XML 구성 파일을 사용하여 콘솔 설정 [관리를 참조하세요.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | 없음 |
|  앱의 기간이 지난 경우         |    Microsoft Teams 회의실 콘솔에 "시스템 구성이 최신이 아니다." 오류가 표시됩니다.                |   [Microsoft Teams 회의실 복구 도구 사용](recovery-tool.md)             |  없음 |
|  지원되지 않는 Windows 10 버전으로 디바이스 업데이트   |    Windows 10 디바이스가 버전 1803에서 버전 1809로 업데이트되었습니다. 이 디바이스는 지원되지 않습니다. 지원되는 버전은 1903입니다. |   지정된 일 수 동안 기능 업데이트를 연기할 수 있는 [DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) 설정에 대한 그룹 정책 또는 MDM 설정이 최대 365일로 설정되어 있는 경우 이 문제가 발생될 수 있습니다. <br><br> Windows 10 버전 1809는 Microsoft Teams 회의실에서 지원되지 않는 반면 버전 1903은 지원됩니다. 그러나 2020년 3월 27일을 현재 버전 1809는 365일이 넘습니다. 이 설정을 변경하지 않는 경우 Windows는 버전 1809를 설치하려고 시도하여 Microsoft Teams 회의실에 문제가 발생할 수 있습니다.<br><br>이 상황을 방지하려면 **업데이트** 연기에 대한 그룹 정책 또는 MDM 설정을 제거합니다. 이렇게 하면 Windows에서 지원되는 최신 OS 버전으로 업데이트할 수 있습니다. <br><br>**중요** 그룹 정책 또는 MDM  설정을 제거해야 합니다(구성되지 않은 왼쪽), **0으로 설정하지 않습니다.** 정책이 0으로 설정된 경우 Windows는 지원되지 않을 수 있는 사용 가능한 최신 버전을 사용하게 됩니다. |  없음 |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>사용자 인터페이스 

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | KB 문서 |
|  ---        |      ---             |   ---            | --- |
|가상 키보드 누락   | Microsoft Teams 회의실에 정보를 입력해야 하는 경우 가상 키보드가 나타나지 않습니다. 이 문제는 Windows 10 버전 1903에서 발생합니다. | Windows 업데이트를 통해 x64 기반 시스템용 Windows 10용 2020-04 누적 업데이트, 버전 1903을 설치합니다.  | 없음 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>하드웨어

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | KB 문서 |
|  ---        |      ---             |   ---            |   --- |
| 모니터가 검색되지 않습니다. | Surface Pro(모델 2017) 장치에서 Microsoft Teams 회의실을 실행하면 모니터가 검색되지 않습니다. |  Surface Pro 전원 단추를 20초 이상 누릅니다. 이 작업을 실행하면 디바이스가 다시 시작하고 그래픽 캐시를 지워야 합니다. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>제한 사항 및 예상 동작

**_

Microsoft Teams 회의실은 HDMI 통합 기능(비디오, 오디오)에 문제가 발생하여 관찰된 HDCP 입력을 지원하지 않습니다. Microsoft Teams 회의실에 연결된 스위치에 HDCP 옵션이 꺼져 있는지 주의해야 합니다. 

_*_

원본이 대기 모드에서 해제될 때 현재 비디오 원본(예: MTR 콘솔)으로 자동 전환하려면 특정 조건이 충족되어야 합니다. 이 기능은 선택 사항이지만 기본 하드웨어가 이 기능을 지원하는 Microsoft Teams Rooms 소프트웨어에서 지원됩니다. 전면 디스플레이로 사용되는 소비자 TV는 HDMI의 CEC(Consumer Electronics Control) 기능을 지원해야 합니다.  선택한 도크 또는 콘솔에 따라(CEC를 지원하지 않을 수 있습니다. 제조업체 지원 설명서 참조), Crestron의 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 또는 [Extron의 Extron HD CTL 100과](https://www.extron.com/article/hdctl100ad) 같은 컨트롤러가 필요한 경우 원하는 동작을 사용하도록 설정할 수 있습니다. 

_*_

항상 유선 1Gbps 네트워크 연결을 사용하여 필요한 대역폭을 보장합니다. 

_*_

Microsoft Teams Rooms 장치가 도메인과 신뢰를 잃는 경우 디바이스에 인증하고 설정을 열 수 없습니다. 예를 들어 도메인에 가입된 후 도메인에서 Microsoft Teams 회의실을 제거하면 신뢰가 손실됩니다. 해결 해결은 로컬 관리자 계정으로 로그인하는 것입니다. 
_*_ Microsoft Teams 회의실은 다중 창 응용 프로그램으로, 앱이 제대로 작동하려면 장치의 HDMI 포트에 회의실 디스플레이를 연결해야 합니다. HDMI 디스플레이가 연결되어 있는지 확인하거나 테스트 중일 때 아직 디스플레이를 구입하지 않은 경우 더미 HDMI 플러그를 사용해야 합니다.
_** <a name="See"> </a>  
## <a name="see-also"></a>참고 항목

[Microsoft Teams 회의실 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 룸 관리](rooms-manage.md)
