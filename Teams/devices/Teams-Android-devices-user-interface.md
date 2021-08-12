---
title: Microsoft Teams Android 장치 사용자 인터페이스 설정
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Android 장치에서 사용자 인터페이스를 설정하는 Teams 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: d3b625e4a54a6a9dcb75d0d1518a65b3e91c23185736672458b0fa1bbd6d55e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327354"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Microsoft Teams Android 장치 사용자 인터페이스 설정

Microsoft Teams Android 장치는 로그인된 계정에 할당된 라이선스 유형에 따라 특정 사용자 인터페이스를 표시할 수 있습니다. 이 동작을 다시 설정하고 표시되는 인터페이스를 제어할 수 있습니다. 이 문서에서는 기본 사용자 인터페이스를 선택한 방법과 Powershell 정책을 사용하여 인터페이스를 변경하는 방법에 대해 자세히 설명합니다.

Android 장치에는 세 가지 유형의 사용자 인터페이스가 Teams 있습니다.

1. 사용자
2. 공통 영역
3. 모임

E3 [](/microsoftteams/user-access) 또는 E5 라이선스와 같은 계정에 사용자 라이선스를 할당하는 경우 Teams 장치에는 대부분의 사용자 시나리오에 대해 완벽하게 기능하는 기본 최종 사용자 인터페이스가 표시됩니다. 그러나 장치가 공통 영역 전화 또는 회의실과 같은 특정 기능을 수행하는 경우 이러한 사용에 대한 특정 사용자 인터페이스가 있습니다.

다음 세 이미지는 사용자 계정에 할당된 라이선스에 따라 사용자 인터페이스가 변경되는 방법을 보여 주며, 첫 번째 이미지에서 사용자 계정에 E5 라이선스가 할당됩니다. 이는 사용자 라이선스이기 때문에 장치에 기본 최종 사용자 인터페이스가 표시됩니다.

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="사용자 모드 인터페이스":::

이 이미지에서 사용자 계정에 공통 영역 전화 라이선스가 [할당되어 있습니다.](/microsoftteams/set-up-common-area-phones) 공통 영역 전화는 주로 전화 통화를 걸고 받는 데 사용됩니다. 따라서 다이얼 패드가 디스플레이에 표시됩니다.

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="공통 영역 전화 인터페이스":::

마지막으로, 이 이미지에는 표준 라이선스가 할당된 Microsoft Teams 룸 [계정이](/MicrosoftTeams/rooms/rooms-licensing) 표시됩니다. Teams 룸 라이선스는 회의실 또는 공유 공간에서 사용하기 위한 것이기 때문에 사용자 인터페이스가 변경되어 일정 보기를 표시하여 모임에 쉽게 참가할 수 있습니다.

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="모임 인터페이스":::

> [!NOTE]
> 사용자 인터페이스를 변경해도 사용이 허가된 다른 기능을 사용하는 기능에는 영향을 주지 않습니다. 예를 들어 Team Rooms 라이선스의 기본 보기가 일정 보기이어도 계정이 올바르게 라이선스가 부여 및 구성된 경우에도 PSTN(Public Switch Telephone Network) 전화 통화를 걸고 받을 수 있습니다.

> [!IMPORTANT]
> 인터페이스의 다른 요소는 변경됩니다. 예를 들어 최종 사용자가 공통 영역 전화 또는 회의실 장치에서 로그인하지 못하게 하려면 이러한 장치의 "서명" 옵션이 설정 메뉴의 일부로 이동하여 관리자 권한이 액세스해야 합니다.

## <a name="override-automatic-user-interface-detection"></a>자동 사용자 인터페이스 검색을 어버라이트합니다.

경우에 따라 의도한 용도와 일치하지 않는 계정에 라이선스를 할당하도록 선택할 수 있습니다. 예를 들어 Android에서 로그인하기 위한 계정에 사용자 라이선스를 Teams 룸 있습니다. 기본적으로 회의실 인터페이스 대신 최종 사용자 인터페이스가 표시됩니다. 기본 인터페이스를 오버라이드하려면 새 Teams IP 전화 [정책을](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 만들어 해당 계정에 적용합니다.

> [!NOTE]
> 사용자 계정에 할당된 라이선스에는 원하는 사용자 인터페이스와 적어도 동일한 라이선스 권리 권리가 있어야 합니다. 공통 영역 전화 라이선스는 공통 영역 전화 사용자 인터페이스만 허용합니다. 회의실 라이선스를 통해 회의실 및 공통 영역 전화 사용자 인터페이스를 사용할 수 있습니다. E3 또는 E5 라이선스는 모든 로그인 모드를 지원합니다.

다음은 자동 라이선스 검색을 오버라우하는 방법의 예입니다. 이 예에서는 이름이 conf-adams@contoso.com 회의실 리소스 계정에 E3 라이선스가 할당된 것으로 가정합니다. 이 계정이 로그인하면 사용자가 회의실 사용자 인터페이스를 볼 수 있습니다.

### <a name="create-a-new-policy-and-assign-to-user"></a>새 정책 만들기 및 사용자에게 할당

1. 원격 Windows PowerShell 세션을 시작하고 다음 cmdlet을 Microsoft Teams 연결합니다.

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. IP Teams 정책을 전화 로그인 모드를 "MeetingSignIn"으로 설정:

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 이제 이 새 정책을 회의실 리소스 계정에 할당할 수 있습니다.

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

회의실 리소스 계정에 정책을 부여한 후 정책 할당이 복제될 때까지 기다려야 합니다. 또한 장치에서 로그인하고 다시 로그인해야 합니다.
