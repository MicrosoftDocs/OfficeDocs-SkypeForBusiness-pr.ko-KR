---
title: Android Microsoft Teams 사용자 인터페이스 설정
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Android 디바이스에서 사용자 인터페이스를 설정하는 Teams 방법을 알아보습니다.
ms.openlocfilehash: c1872fffef3f21c3fec6a9c693b02e218d5d8337
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503769"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Android Microsoft Teams 사용자 인터페이스 설정

Microsoft Teams Android 디바이스는 로그인된 계정에 할당된 라이선스 유형에 따라 특정 사용자 인터페이스를 표시할 수 있습니다. 이 동작을 오버라이드하고 표시되는 인터페이스를 제어할 수 있습니다. 이 문서에서는 기본 사용자 인터페이스를 선택한 방법과 Powershell 정책을 사용하여 인터페이스를 변경할 수 있는 방법을 자세히 설명합니다.

Android 디바이스에는 세 가지 유형의 Teams 있습니다.

1. 사용자
2. 공용 영역
3. 모임

E3 [](/microsoftteams/user-access) 또는 E5 라이선스와 같은 계정에 사용자 라이선스를 할당하는 경우 Teams 디바이스는 대부분의 사용자 시나리오에 완벽하게 기능되는 기본 최종 사용자 인터페이스를 표시합니다. 그러나 디바이스가 공통 영역 전화 또는 회의실과 같은 특정 기능을 수행하는 경우 이러한 사용에 대한 특정 사용자 인터페이스가 있습니다.

다음 세 이미지는 사용자 계정에 할당된 라이선스에 따라 사용자 인터페이스가 변경되는 방법을 보여 니다. 

## <a name="end-user-interface"></a>최종 사용자 인터페이스 

사용자 계정에 E5 라이선스가 할당됩니다. 이 라이선스는 사용자 라이선스이기 때문에 디바이스에 기본 최종 사용자 인터페이스가 표시됩니다.

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="사용자 모드 인터페이스.":::

## <a name="common-area-interface"></a>공용 영역 인터페이스

이 이미지에서 사용자 계정에 공용 영역 라이선스가 전화 [있습니다](/microsoftteams/set-up-common-area-phones). 공용 영역 전화는 주로 전화를 걸고 받는 데 사용됩니다. 따라서 다이얼 패드가 디스플레이에 표시됩니다.

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="공용 영역 전화 인터페이스입니다.":::

## <a name="meeting-interface"></a>모임 인터페이스

이 이미지는 라이선스가 할당된 사용자 [Microsoft Teams 룸 스탠더드 보여줍니다](/MicrosoftTeams/rooms/rooms-licensing). Teams 룸 라이선스는 회의실 또는 공유 공간에서 사용할 수 있으므로 사용자 인터페이스가 변경되어 일정 보기를 표시하여 모임에 쉽게 참가할 수 있습니다.

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="모임 인터페이스입니다.":::

> [!NOTE]
> 사용자 인터페이스를 변경해도 라이선스가 부여된 다른 기능을 사용할 수 있는 기능에는 영향을 주지 않습니다. 예를 들어 Team Rooms 라이선스의 기본 보기가 일정 보기인 경우에도 계정이 올바르게 라이선스 및 구성된 경우 PSTN(공용 스위치 전화 네트워크) 전화를 걸고 받을 수 있습니다.

> [!IMPORTANT]
> 인터페이스의 다른 요소가 변경됩니다. 예를 들어 최종 사용자가 공용 영역 전화 또는 회의실 디바이스에서 로그인하지 못하게 하려면 이러한 디바이스의 "로그인" 옵션은 관리자 권한이 액세스해야 하는 설정 메뉴의 일부로 이동합니다.

## <a name="override-automatic-user-interface-detection"></a>자동 사용자 인터페이스 감지를 오버라이드합니다.

경우에 따라 의도한 용도와 일치하지 않는 계정에 라이선스를 할당하도록 선택할 수 있습니다. 예를 들어 Android에서 로그인하기 위한 계정에 사용자 라이선스를 Teams 룸 수 있습니다. 기본적으로 회의실 인터페이스 대신 최종 사용자 인터페이스가 표시됩니다. 기본 인터페이스를 오버라이드하려면 새 IP Teams 전화 [정책을](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 만들고 해당 계정에 적용됩니다.

> [!NOTE]
> 사용자 계정에 할당된 라이선스에는 원하는 사용자 인터페이스와 적어도 동일한 라이선스 자격이 있어야 합니다. 공용 영역 전화 라이선스는 공용 영역 전화 사용자 인터페이스만 허용합니다. 회의실 라이선스를 사용하면 회의실 및 공용 영역 전화 사용자 인터페이스를 사용할 수 있습니다. E3 또는 E5 라이선스는 모든 로그인 모드를 지원합니다.

다음은 자동 라이선스 검색을 오버라이드하는 방법을 예로 들 수 있습니다. 이 예제에서는 E3 라이선스가 할당된 conf-adams@contoso.com 회의실 리소스 계정이 할당된 것으로 가정합니다. 이 계정이 로그인하면 사용자가 회의실 사용자 인터페이스를 볼 수 있습니다.

### <a name="create-a-new-policy-and-assign-to-user"></a>새 정책 만들기 및 사용자에게 할당

1. 원격 Windows PowerShell 세션을 시작하고 다음 cmdlet을 사용하여 Microsoft Teams 연결합니다.

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 새 IP Teams 전화 "MeetingSignIn"으로 로그인 모드를 설정합니다.

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 이제 회의실 리소스 계정에 이 새 정책을 할당할 수 있습니다.

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

회의실 리소스 계정에 정책을 부여한 후 정책 할당이 복제될 때까지 기다려야 합니다. 또한 디바이스에서 로그인하고 다시 로그인해야 합니다.

## <a name="impact-on-microsoft-teams-admin-center"></a>관리 Microsoft Teams 영향

Microsoft Teams 관리 센터를 사용하면 디바이스를 관리할 Microsoft Teams 있습니다. Teams 관리 센터를 사용하여 디바이스 관리에 대한 자세한 내용은 [Microsoft Teams.](device-management.md)


Teams 관리 센터는 휴대폰을 관리하는 Teams 기능을 제공합니다. 휴대폰은 사용자 전화, 공용 지역 전화 및 전화 회의 전화의 기능에 따라 세 개의 탭 중 하나에 필터링됩니다. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="관리 센터의 Teams 헤더입니다.":::

사용자 인터페이스 검색과 Teams 계정에 할당된 라이선스에 따라 휴대폰이 분류됩니다. 예를 들어 공용 영역 전화 라이선스가 할당된 계정이 휴대폰에 로그인하는 경우 해당 휴대폰은 기본 모든 휴대폰 섹션과 공용 영역 전화 섹션에 모두 **표시됩니다**.

휴대폰이 다른 섹션에 표시될 경우 휴대폰에 다른 라이선스를 할당하거나 위에서 설명한 대로 Teams IP 전화 수 [있습니다](#override-automatic-user-interface-detection).
