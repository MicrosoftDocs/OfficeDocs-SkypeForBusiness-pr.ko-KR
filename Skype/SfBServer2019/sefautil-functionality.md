---
title: 2019년 비즈니스용 Skype 서버 Skype PowerShell에서 SEFAUtil 기능 사용 지원
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: '요약: PowerShell을 사용하여 누적 업데이트 1을 설치한 후 비즈니스용 Skype 서버 2019에서 SEFAUtil 기능을 가져오는 방법을 알아봅니다.'
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676540"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>2019년 비즈니스용 Skype 서버 PowerShell을 통해 SEFAUtil 기능 사용

SEFAUtil(보조 확장 기능 활성화)을 사용하면 비즈니스용 Skype 서버 관리자 및 지원 센터 에이전트가 비즈니스용 Skype 서버 사용자를 대신하여 대리자 벨소리, 착신 전환 및 그룹 통화 픽업 설정을 구성할 수 있습니다. 또한 SEFAUtil을 사용하면 관리자가 특정 사용자에 대한 호출 라우팅 설정을 쿼리할 수 있습니다.

비즈니스용 Skype 서버 2019년 7월 누적 업데이트를 설치한 후 SEFAUtil을 통해서만 사용할 수 있었던 다음 기능은 Skype PowerShell에서도 사용할 수 있습니다.

- [착신 전환 설정](#call-forwarding-settings)
- [위임 설정](#delegation-settings)
- [팀 구성원 및 관련 설정](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>착신 전환 설정

관리자는 PowerShell에서 다음 명령을 사용하여 착신 전환 설정을 변경할 수 있습니다.

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

이 명령은 지정된 사용자의 착신 전환 설정을 개체로 반환하고 화면에 동일하게 표시합니다.

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

이 명령은 지정된 사용자의 착신 전환 설정을 수정합니다. 이 명령은 지정된 사용자의 착신 전환 설정을 개체로 반환하고 화면에 동일하게 표시합니다. 명령이 성공하지 못하면 적절한 오류 메시지가 표시됩니다.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

이 명령은 사용자의 착신 전환 설정을 사용하지 않도록 설정합니다(여기서는 두 가지 매개 변수 예제를 보여 줍니다).

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

이 명령은 사용자의 착신 전환 설정을 수정합니다.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

이 명령은 동시 링 설정을 수정합니다(다시 두 개의 매개 변수 예제를 사용하여 음성 메일에 응답하지 않는 경우와 다른 매개 변수에 응답하지 않는 두 번째 매개 변수 예).

## <a name="delegation-settings"></a>위임 설정

관리자는 PowerShell에서 다음 명령을 사용하여 위임 설정을 변경할 수 있습니다.

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

이 명령은 대리자 목록의 개체를 반환하고 지정된 사용자의 대리자 목록을 표시합니다. 명령이 성공하지 못하면 적절한 오류 메시지가 표시됩니다.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

이 명령은 지정된 사용자의 위임 설정을 수정하고 대리자 목록의 개체를 반환하며 대리자 목록을 표시합니다. 명령이 성공하지 못하면 적절한 오류 메시지가 표시됩니다.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

이 명령은 대리자를 추가하거나 제거합니다.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

이 명령은 대리자 목록을 특정 대리자로 설정합니다.

## <a name="team-members-and-related-settings"></a>팀 구성원 및 관련 설정

관리자는 PowerShell에서 다음 명령을 사용하여 팀 구성원 및 관련 설정을 변경할 수 있습니다.

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

이 명령은 팀 구성원 목록이 포함된 개체를 반환하고 화면에 개체를 표시합니다. 명령이 성공하지 못하면 적절한 오류 메시지가 표시됩니다.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

이 명령은 지정된 사용자의 팀 구성원 목록을 수정하고, 팀 구성원 목록이 포함된 개체를 반환하고, 화면에 개체를 표시합니다. 명령이 성공하지 못하면 적절한 오류 메시지가 표시됩니다.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

이 명령은 팀 구성원을 추가하거나 제거합니다.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

이 명령은 팀 목록을 특정 멤버로 설정합니다.

## <a name="more-information"></a>추가 정보

온-프레미스 배포의 경우 이 기능에 도입된 cmdlet은 아래 지정된 액세스 수준에 따라 다음 그룹의 멤버만 실행할 수 있습니다.

- CsAdministrator – 모든 cmdlet에 대한 가져오기 및 설정
- CsVoiceAdministrator - 모든 cmdlet에 대한 가져오기 및 설정
- CsHelpDesk - 모든 cmdlet에 대한 가져오기

이러한 관리자 역할에 대한 자세한 내용은 [비즈니스용 Skype 서버 제어판 관리자 만들기를 참조하세요](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). 관리자는 서버 컴퓨터에 직접 또는 원격으로 로그온하여 이러한 cmdlet에 액세스할 수 있습니다.
하이브리드 배포의 경우 비즈니스용 Skype 관리자는 모든 cmdlet에 대해 Get 및 Set를 호출할 수 있어야 합니다. 역할의 전체 목록에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> 서버 자동 검색을 사용하도록 설정해야 합니다. cmdlet을 사용하기 위한 추가 라이선스 요구 사항은 도입되지 않습니다.
