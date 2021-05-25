---
title: 2019년 8월 PowerShell에서 SEFAUtil 기능 사용 비즈니스용 Skype 서버 지원
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 누적 업데이트 1을 설치한 후 PowerShell을 사용하여 비즈니스용 Skype 서버 2019에서 SEFAUtil 기능을 얻는 방법을 학습합니다.'
ms.openlocfilehash: fa7bccaa30b559bf694274471b1f8883e8482861
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629007"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>2019년 8월 PowerShell을 통해 SEFAUtil 비즈니스용 Skype 서버 사용

SEFAUtil(보조 확장 기능 활성화)을 사용하면 비즈니스용 Skype 서버 관리자 및 헬프데스크 에이전트가 사용자 대신 위임 벨 울림, 통화 전달 및 그룹 통화 선택 설정을 구성할 비즈니스용 Skype 서버 있습니다. 또한 관리자는 이 도구를 사용하여 특정 사용자에 대해 게시된 통화 라우팅 설정을 쿼리할 수 있습니다. 비즈니스용 Skype 서버 2019년 7월 누적 업데이트를 설치한 후 현재 SEFAUtil을 통해서만 관리할 수 있는 다음 기능도 PowerShell을 통해 관리할 수 있습니다.

- [전달 설정](#call-forwarding-settings)
- [위임 설정](#delegation-settings)
- [팀 구성원 및 관련 설정](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>전달 설정

관리자는 PowerShell에서 다음 cmdlet을 사용하여 통화 전달 설정을 변경할 수 있습니다.

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

이 cmdlet은 지정한 사용자의 호출 전달 설정을 개체로 반환하고 화면에 동일하게 표시합니다.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

이 cmdlet은 지정된 사용자의 통화 전달 설정을 수정합니다. 이 cmdlet은 지정된 사용자의 호출 전달 설정을 개체로 반환하고 성공할 경우 동일한 설정을 화면에 표시합니다. 오류가 발생하면 적절한 오류 메시지가 표시됩니다.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

이 cmdlet은 사용자의 통화 전달 설정을 사용하지 않도록 설정합니다(여기서는 두 가지 다른 매개 변수 예 표시).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

이 cmdlet은 사용자의 통화 전달 설정을 수정합니다.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

이 cmdlet은 동시 벨 울림 설정을 수정합니다(두 개의 매개 변수 예제와 함께 하나는 음성메일에 대한 답이 없는 경우와 다른 링에 대한 답이 없는 두 번째 매개 변수 예).

## <a name="delegation-settings"></a>위임 설정

관리자는 PowerShell에서 다음 cmdlet을 사용하여 위임 설정을 변경할 수 있습니다.

- `Get-CsuserDelegates -Identity <UserIdParameter>`

이 cmdlet은 대리인 목록의 개체를 반환하고 성공할 경우 지정된 사용자의 대리인 목록을 나타냅니다. 오류가 발생하면 적절한 오류 메시지가 표시됩니다.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

이 cmdlet은 지정된 사용자의 위임 설정을 수정하고, 대리인 목록의 개체를 반환하고, 성공할 경우 대리인 목록을 나타냅니다. 오류가 발생하면 적절한 오류 메시지가 표시됩니다. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

이 cmdlet은 대리자를 추가하거나 제거합니다.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

이 cmdlet은 대리인 목록을 특정 대리인으로 설정합니다.

## <a name="team-members-and-related-settings"></a>팀 구성원 및 관련 설정

관리자는 PowerShell에서 다음 cmdlet을 사용하여 팀 구성원 및 관련 설정을 변경할 수 있습니다.

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

이 cmdlet은 팀 구성원 목록이 포함된 개체를 반환하고 성공한 경우 해당 개체를 화면에 표시합니다. 오류가 발생하면 적절한 오류 메시지가 표시됩니다.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

이 cmdlet은 지정된 사용자의 팀 구성원 목록을 수정하고, 팀 구성원 목록이 포함된 개체를 반환하고, 성공할 경우 해당 개체를 화면에 표시합니다. 오류가 발생하면 적절한 오류 메시지가 표시됩니다.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

이 cmdlet은 팀 구성원을 추가하거나 제거합니다.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

이 cmdlet은 팀 목록을 특정 구성원으로 설정합니다.

## <a name="more-information"></a>추가 정보

사내 배포의 경우 이 기능에 도입된 cmdlet은 아래 지정된 액세스 수준에 따라 다음 그룹의 구성원만 실행할 수 있습니다.

- CsAdministrator – 모든 cmdlet에 대해 Get 및 Set
- CsVoiceAdministrator - 모든 cmdlet에 대해 Get 및 Set
- CsHelpDesk - 모든 cmdlet에 대한 다운로드

이러한 관리자 역할에 대한 자세한 내용은 [Create 비즈니스용 Skype 서버 Control Panel Administrators를 참조하십시오.](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md) 관리자는 서버 컴퓨터에 직접 또는 원격으로 로그온하여 이러한 cmdlet에 액세스할 수 있습니다.
하이브리드 배포의 경우 비즈니스용 Skype 모든 cmdlet에 대해 Get 및 Set를 호출할 수 있습니다. 전체 역할 목록에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요.](/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> 서버 자동 검색을 사용하도록 설정해야 합니다. cmdlet을 사용하기 위한 추가 라이선스 요구 사항은 도입되지 않습니다.
