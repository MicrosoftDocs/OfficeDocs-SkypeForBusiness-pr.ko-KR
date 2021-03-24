---
title: Surface Hub용 Microsoft Teams 배포
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Teams가 기본 호출 및 모임 애플리케이션이 하도록 Surface Hub용 Teams 앱을 설치하고 구성하는 방법에 대해 알아보십시오.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38202fcbb4c2147baae3f745bc2455da6fdff3e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093938"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Surface Hub용 Microsoft Teams 배포
======================================

Surface Hub용 Teams를 설치하기 전에 다음을 해야 합니다.

 □ 하드웨어, 운영 체제 및 기타 요구 사항을 충족하는지 확인합니다. 자세한 내용은 Microsoft Surface Hub 관리 [가이드 를 참조하세요.](/surface-hub/)<br>
 □ Teams에 필요한 최소 운영 체제 업데이트가 설치되어 있는지 [확인합니다. KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Hub 디바이스 계정에 Teams 라이선스를 할당합니다.<br>
 □ 비즈니스용 Skype Online에서 전환하는 경우 Teams 라이선스가 사용자에게 할당되어 있는지 확인하세요.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Microsoft Store에서 Surface Hub용 Teams 설치 

이러한 지침은 Microsoft Store에서 Surface Hub용 Teams를 설치하기 위한 것입니다. 
 
1. Microsoft Store 시작:<br>
   a. 모든 **앱**  >  **설정 시작 을**  >  **탭합니다.**<br> b. **Surface Hub Device 계정, 관리 를 탭합니다.**<br>
   c. 왼쪽에서 앱 & **탭을 탭합니다.**<br> d. 오른쪽에서 저장소 **열기 단추를 탭합니다.** 
2. Microsoft Store에서 Microsoft *Teams를 검색합니다.* **Surface Hub용 Microsoft Teams가** 표시됩니다. 앱 다운로드 **단추를** 탭하여 설치합니다.  
3. 설치가 완료되면 Surface Hub를 다시 시작합니다. 

> [!NOTE]
> 스토어 목록 **페이지에서** 시작을 탭하지 않습니다.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Teams를 기본 호출 및 모임 애플리케이션으로 만들기
 
기본 호출 및 모임 애플리케이션 정책을 구성하는 두 가지 옵션이 있습니다. 

- **옵션 1**: USB 키를 통해 구성합니다. 
- **옵션 2**: Intune과 같은 MDM을 통해 구성합니다.
 
### <a name="option-1-configure-via-usb-key"></a>옵션 1: USB 키를 통해 구성 
 
패키지는 이 다운로드 페이지에서 [찾을 수 있습니다.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) 설치할 패키지에 적합한 패키지를 선택하고 USB 키에 복사합니다. 사용할 올바른 .ppkg 파일은 다음과 같이 적용할 기본 애플리케이션 정책에 따라 달라 니다. 

|번호  |설명  |
|---------|---------|
|0     | 시작 화면에서 Skype 기본 설정 앱, Teams 모임 사용 가능        |
|1     | 시작 화면에서 팀 선호 앱, Skype 모임 사용 가능        |
|2     | 시작 화면의 Teams 전용 앱(Skype 앱을 사용할 수 없습니다)        |
 
1. Surface Hub 디바이스에 USB 키를 연결합니다. 
2. Surface Hub **디바이스에서** 설정 앱을 니다. 
3. **Surface Hub 디바이스 계정 관리 를 를**
4. 디바이스 **관리 를 를 니다.** 
5. **프로비전 패키지 추가 또는 제거를 클릭합니다.** 
6. 패키지 추가 를 **클릭합니다.**
7. 드롭다운 **메뉴에서** 이동식 미디어 옵션을 선택합니다. 
8. 이전에 USB 키에 복사한 <strong>적절한 TeamsRTMMode*.ppkg</strong> 패키지를 추가합니다. 
9. Surface Hub 디바이스를 다시 시작합니다. 
10. 디바이스가 다시 시작된 후 시작 화면에서 Teams 앱을 시작하고 일정에서 모임에 참가할 수 있습니다. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>옵션 2: Intune과 같은 MDM을 통해 구성 

다음을 사용하여 Intune을 통해 기본 호출 및 모임 애플리케이션 정책을 구성합니다. 또한 [Intune을 사용하여 Surface Hub용 Microsoft Teams 앱 배포 블로그를 참조하세요.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|설정   |값    |설명    |
|----------|---------|---------|
|경로      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|데이터 형식 | 정수(0-2)   |0 - 시작 화면에서 Skype 기본 설정 앱, Teams 모임 사용 가능<br>1 - 시작 화면에서 팀 선호 앱, Skype 모임 사용 가능<br>2 - 시작 화면의 Teams 전용 앱(Skype 앱을 사용할 수 없습니다) |
|작업| Get, Set        |

|설정   |값    |
|----------|---------|
|경로      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|데이터 형식 | string - 문자열을 Teams 애플리케이션 패키지 ID로 **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! 팀** |
|작업| Get, Set        |

Surface Hub 디바이스를 다시 시작합니다. 디바이스가 다시 시작된 후 시작 화면에서 Teams 앱을 시작하고 일정에서 모임에 참가할 수 있습니다.