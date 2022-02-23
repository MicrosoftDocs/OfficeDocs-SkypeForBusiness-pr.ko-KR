---
title: 알려진 문제
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 업데이트, 사용자 인터페이스Microsoft Teams 룸 하드웨어 및 제한 사항 및 예상 동작을 포함하여 알려진 문제에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5322020d37e3251aa54a20afecba353dd6335f55
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926321"
---
# <a name="known-issues"></a>알려진 문제 
 
이 문서에서는 기능 영역으로 Microsoft Teams 룸 알려진 문제를 나열합니다.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>업데이트 

| 문제 제목 |  동작 \/ 증상 | 알려진 해결 방법 | KB 문서 |
|  ---        |      ---             |   ---            | --- |
| 에지가 검색되지 않을 때 화이트보드/콘텐츠 카메라가 콘텐츠 향상에 실패합니다. | 4.11.12.0으로 업데이트한 후 콘텐츠 카메라의 보기에 화이트보드 가장자리가 없는 경우 카메라가 카메라 보기에서 모든 콘텐츠를 향상/오버레이하지 않습니다.| 카메라 보기의 모든 콘텐츠를 개선하기 위해 향후 릴리스에 포함되는 수정 내용입니다. 해결 방법을 통해 화이트보드에 상자에 적용된 화가 테이프를 사용하여 콘텐츠 카메라가 콘텐츠를 포커스하고 향상시키는 데 사용할 수 있는 가장자리를 일시적으로 제공할 수 있습니다. | 없음 |
| Edge 브라우저 자동 시작 | 빌드하기 전에 Edge 브라우저 97.0.1072.62는 디바이스가 시작될 때 Microsoft Teams 룸 앱과 함께 자동으로 시작됩니다. | 사용자 상호 작용이 필요하지 않고 2022년 1월 17일 월요일 또는 그 전에 자동으로 해결됩니다. 더 빠른 해결이 필요한 경우: 에지가 Microsoft Teams 함께 시작하면 URL edge://settings/help 자동으로 다운로드하고 적용해야 합니다. 업데이트가 적용된 후 브라우저에서 '다시 시작'을 선택합니다. Edge Azure IoT 닫고 시스템을 다시 부트하면 문제가 해결됩니다. | 없음 |
| 갤러리 참가자 비디오 분할   |  9명 이상의 원격 참가자가 있는 모임에 공유 콘텐츠가 없는 경우 모임이 이중 전면 디스플레이 모드인 경우 자체 미리 보기가 있는 회의실 전면 디스플레이의 비디오 1개가 오디오로 표시될 수 있습니다. 또한 실제 오디오 참가자 수보다 적은 수의 오디오 참가자가 이중 전면 디스플레이에 표시됩니다. | 문제는 향후 업데이트에서 해결됩니다. | 없음 |
| 애플리케이션이 시작되지 않습니다. |  애플리케이션 버전 4.4.41.0으로 업데이트한 후 시스템이 검은색 화면으로 부팅되거나 몇 분 후에 로그인 화면으로 이동합니다. | 이 문제를 Microsoft Teams 룸 [4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) 버전으로 업데이트한 후 애플리케이션이 시작되지 않는 경우의 단계를 따릅니다.  | 없음 |
|  콘텐츠 공유 후 모임 볼륨이 낮음         |   Microsoft Teams 룸 20H2 Windows 10 HDMI를 통해 콘텐츠를 공유한 후 미디어 및 모임 볼륨이 감소했습니다. 이 문제는 20H2의 오디오 Windows 10 발생했습니다. | 이 문제의 수정은 애플리케이션 버전 [4.9.12.0에서 사용할 수 있습니다](/microsoftteams/rooms/rooms-release-note#49120-7282021). | 없음 |
|  최신 앱         |    Microsoft Teams 룸 콘솔에는 "시스템 구성이 최신" 오류가 표시됩니다.                |   [복구 Microsoft Teams 룸 사용](recovery-tool.md)             |  없음 |
|  지원되지 않는 버전으로 업데이트된 디바이스 Windows 10   |    Windows 10 버전 1803에서 버전 1809로 업데이트된 디바이스는 지원되지 않습니다. 지원되는 버전은 1903입니다. |   지정한 기간 동안 기능 업데이트를 연기할 수 있는 [DeferFeatureUpdatesPeriodinDays](/windows/deployment/update/waas-configure-wufb) 설정에 대한 그룹 정책 또는 MDM 설정이 최대 365일로 설정되어 있는 경우 이 문제가 일어날 수 있습니다. <br><br> Windows 10 버전 1809는 지원되지 Microsoft Teams 룸 버전 1903이 지원됩니다. 그러나 2020년 3월 27일 현재 버전 1809는 365일이 넘습니다. 이 설정이 변경되지 않은 경우 Windows 버전 1809를 설치하려고 시도하면 문제가 발생할 수 Microsoft Teams 룸.<br><br>이 상황을 방지하려면 업데이트 **연기** 에 대한 그룹 정책 또는 MDM 설정을 제거합니다. 이렇게 하면 Windows 지원되는 최신 OS 버전으로 업데이트할 수 있습니다. <br><br>**중요:** 그룹 정책 또는 MDM 설정을 제거해야 **합니다** (구성되지 않은 왼쪽) **0으로 설정하지 않습니다**. 정책이 0으로 설정되어 있는 Windows 지원되지 않을 수 있는 최신 사용 가능한 버전을 사용하게 됩니다. |  없음 |



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

전면 행은 방 전면 디스플레이의 레이아웃 선택기에서 '미리 보기'로 표시됩니다. 향후 더 많은 기능 및 개선이 추가될 예정입니다. 다음 제한은 릴리스 후 주소입니다.

- 전면 행 레이아웃은 방 전면 단일 디스플레이에 최대 4명 비디오 참가자를 표시합니다. 이중 전면에 최대 9개 비디오가 표시됩니다. 이러한 참가자는 마지막 활성 발표자에서 선택됩니다.

- 전면 행에는 100% 크기 조정이 있는 1080p 디스플레이가 필요합니다. 방 전면 디스플레이의 글꼴 크기가 너무 작거나 방의 필요를 위해 큰 경우 화면 전면의 크기 및 해상도 변경 [](rooms-operations.md#change-scale-and-resolution) 을 참조하여 표시 설정을 조정합니다.

***

Microsoft Teams 룸 HDMI 인제스트 기능(비디오, 오디오)에 문제가 발생하기 위해 관찰된 HDCP 입력을 지원하지 않습니다. 스위치에 연결된 스위치가 HDCP 옵션을 Microsoft Teams 룸 있는지 주의하세요. 

***

룸 전면 디스플레이가 MTR 콘솔과 같은 활성 비디오 원본으로 자동으로 전환하려면 원본이 대기 모드에서 절전 모드로 해제될 때 특정 조건을 충족해야 합니다. 이 기능은 선택 사항이지만 기본 Microsoft Teams 룸 소프트웨어에서 지원됩니다. 기본 하드웨어가 기능을 지원합니다. 전면 디스플레이로 사용되는 소비자 TV는 HDMI의 CEC(소비자 전자 제어) 기능을 지원해야 합니다.  선택한 도크 또는 본체에 따라 크레스트론의 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 또는 [Extron의 Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) 과 같은 컨트롤러가 필요한 경우 원하는 동작을 사용하도록 설정할 수 있습니다. 제조업체의 지원 설명서를 참조하여 dock 또는 콘솔이 CEC를 지원하는지 확인합니다.

또한 방 전면 디스플레이로 사용되는 소비자 TV는 소프트웨어의 안정성 문제를 Microsoft Teams 룸 있습니다. 이는 대기 모드의 불일치 구현, 활성 비디오 원본 선택 및 잘못된 EDID 정보를 디바이스에 Microsoft Teams 룸 기인합니다. 알려진 증상은 대기에서 깨어나서 응답하지 않는 Microsoft Teams 룸 화면 앞의 검은색/회색 화면입니다.  소비자 TV를 사용할 때 문제가 발생하는 경우 FSR 비디오 제품 그룹에서 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E)와 같은 구성 가능한 [EDID 컨트롤러 또는 EDID](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143) 에뮬레이터를 Emulator 것이 좋습니다.

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
