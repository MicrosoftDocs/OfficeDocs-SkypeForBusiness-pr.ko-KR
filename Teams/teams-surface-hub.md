---
title: Surface Hub 용 Microsoft 팀 배포
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Surface Hub 용 Microsoft 팀에 대 한 관리자 설정을 구성 합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5634c4ac5e5955d099555cce4f74b57a527662e9
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836938"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Surface Hub 용 Microsoft 팀 배포
======================================

Surface Hub 용 팀을 설치 하기 전에 다음을 수행 해야 합니다.

 □ 하드웨어, 운영 체제 및 기타 요구 사항이 충족 되는지 확인 합니다. 자세한 내용은 [Microsoft Surface Hub 관리 가이드](https://docs.microsoft.com/surface-hub/)를 참조 하세요.<br>
 □ 팀에 필요한 최소 운영 체제 업데이트가 설치 되어 있는지 확인 합니다- [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ 팀 라이선스를 허브 디바이스 계정에 할당 합니다.<br>
 □ 비즈니스용 Skype Online에서 전환 하는 경우 팀 라이선스가 사용자에 게 할당 되었는지 확인 합니다.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Microsoft Store에서 Surface Hub 팀 설치 

이 지침은 Microsoft Store에서 Surface Hub 팀을 설치 하는 데 적합 합니다. 
 
1. Microsoft Store 시작:<br>
   에서. **** > **모든**앱 > **설정**시작을 탭 합니다.<br> b. **Surface Hub 디바이스 계정, 관리를**탭 합니다.<br>
   c. 왼쪽에서 **앱 & 기능** 탭을 탭 합니다.<br> a. 오른쪽에서 **스토어 열기** 단추를 탭 합니다. 
2. Microsoft Store에서 *Microsoft 팀*을 검색 합니다. **Surface Hub 용 Microsoft 팀** 이 표시 됩니다. **앱 다운로드** 단추를 탭 하 여 설치 합니다.  
3. 설치가 완료 되 면 Surface Hub를 다시 시작 합니다. 

> [!NOTE]
> 스토어 목록 페이지에서 **실행** 을 탭 하지 마세요.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>팀을 기본 통화 및 모임 응용 프로그램으로 만들기
 
기본 통화 및 모임 응용 프로그램 정책을 구성 하는 두 가지 옵션이 있습니다. 

- **옵션 1**: USB 키를 통해 구성 
- **옵션 2**: Intune을 통해 MDM을 통해 구성 합니다.
 
### <a name="option-1-configure-via-usb-key"></a>옵션 1: USB 키를 통해 구성 
 
이 [다운로드 페이지](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)에서 패키지를 찾을 수 있습니다. 설치 하려는 패키지에 대해 적절 한 파일을 선택 하 고 USB 키에 복사 합니다. 사용할 올바른 ppkg 파일은 다음과 같이 적용 하려는 기본 응용 프로그램 정책에 따라 달라 집니다. 

|숫자로  |설명  |
|---------|---------|
|0     | 시작 화면에 있는 Skype 기본 앱으로, 팀 회의 이용 가능        |
|1     | 시작 화면의 팀 기본 앱, Skype 모임 이용 가능        |
|2     | 시작 화면의 팀 전용 앱 (Skype 앱을 사용할 수 없음)        |
 
1. Surface Hub 장치에 USB 키를 연결 합니다. 
2. Surface Hub 장치에서 **설정** 앱을 엽니다. 
3. **Surface Hub 디바이스 계정 관리**를 엽니다.
4. **장치 관리**를 엽니다. 
5. **배포 패키지 추가 또는 제거를**클릭 합니다. 
6. **패키지 추가**를 클릭 합니다.
7. 드롭다운 메뉴에서 **이동식 미디어** 옵션을 선택 합니다. 
8. 이전에 USB 키에 복사한 적절 한 <strong>Teamsrtmmode * ppkg</strong> 패키지를 추가 합니다. 
9. Surface Hub 장치를 다시 시작 합니다. 
10. 장치를 다시 시작한 후에는 시작 화면에서 팀 앱을 시작 하 고 일정에서 모임에 참가할 수 있습니다. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>옵션 2: MDM을 통해 구성 (예: Intune) 

Intune을 통해 기본 통화 및 모임 응용 프로그램 정책을 구성 하려면 다음을 사용 합니다. 또한 블로그를 참조 하 고 [Intune을 사용 하 여 Surface Hub 앱 용 Microsoft 팀을 배포](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)합니다.

|설정   |값    |설명    |
|----------|---------|---------|
|패스가      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|데이터 형식 | integer (0-2)   |0-시작 화면에 Skype 선호 앱, 팀 회의 이용 가능<br>1-시작 화면의 팀 기본 앱, Skype 모임 이용 가능<br>2-시작 화면의 팀 전용 앱 (Skype 앱을 사용할 수 없음) |
|작업| Get, Set        |

|설정   |값    |
|----------|---------|
|패스가      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|데이터 형식 | string-Microsoft로 문자열을 팀 응용 프로그램 패키지 ID로 설정 **합니다. MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! 팀** |
|작업| Get, Set        |

Surface Hub 장치를 다시 시작 합니다. 장치를 다시 시작한 후에는 시작 화면에서 팀 앱을 시작 하 고 일정에서 모임에 참가할 수 있습니다.

