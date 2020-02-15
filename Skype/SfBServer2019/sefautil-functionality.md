---
title: 비즈니스용 Skype 서버 2019에서 PowerShell의 SEFAUtil 기능 사용에 대 한 지원
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
description: '요약: 누적 업데이트 1을 설치한 후 PowerShell을 사용 하 여 비즈니스용 Skype 서버 2019의 SEFAUtil 기능을 가져오는 방법을 알아봅니다.'
ms.openlocfilehash: 1a18a954e40ba7a0c72e4d87b4b3c943e827f2a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049140"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019에서 PowerShell을 통해 SEFAUtil 기능 사용

SEFAUtil (보조 확장 기능 활성화)를 사용 하면 비즈니스용 skype 서버 사용자를 대신 하 여 Skype 연결 링, 착신 전환 및 그룹 통화 픽업 설정을 구성할 수 있습니다. 또한 관리자는이 도구를 사용 하 여 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다. 비즈니스용 Skype 서버 2019 7 월 누적 업데이트를 설치한 후에는 SEFAUtil를 통해서만 현재 관리 되는 다음 기능도 PowerShell을 통해 관리할 수 있습니다.

- [착신 전환 설정](#call-forwarding-settings)
- [위임 설정](#delegation-settings)
- [팀 구성원 및 관련 설정](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>착신 전환 설정

관리자는 PowerShell에서 다음 cmdlet을 사용 하 여 착신 전환 설정을 변경할 수 있습니다.

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

이 cmdlet은 지정 된 사용자의 착신 전환 설정을 개체로 반환 하며 화면에 동일 하 게 표시 합니다.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

이 cmdlet은 지정 된 사용자의 착신 전환 설정을 수정 합니다. 이 cmdlet은 지정 된 사용자의 착신 전환 설정을 개체로 반환 하 고 성공을 위해 화면에 동일 하 게 표시 합니다. 오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

이 cmdlet은 사용자의 착신 전환 설정을 사용 하지 않도록 설정 합니다 (여기에는 서로 다른 두 매개 변수 예제가 표시 됩니다).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

이 cmdlet은 사용자의 착신 전환 설정을 수정 합니다.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

이 cmdlet은 SimulRing 설정을 수정 합니다 (두 매개 변수 예, 음성 메일에 응답 하지 않음, 두 번째는 응답 하지 않음).

## <a name="delegation-settings"></a>위임 설정

관리자는 PowerShell에서 다음 cmdlet을 사용 하 여 위임 설정을 변경할 수 있습니다.

- `Get-CsuserDelegates -Identity <UserIdParameter>`

이 cmdlet은 대리자 목록 개체를 반환 하 고 성공한 경우 지정한 사용자의 대리인 목록을 표시 합니다. 오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

이 cmdlet은 지정 된 사용자의 위임 설정을 수정 하 고 대리인 목록의 개체를 반환 하며 성공 여부에 대 한 대리인 목록을 표시 합니다. 오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

이 cmdlet은 대리인을 추가 하거나 제거 합니다.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

이 cmdlet은 위임 목록을 특정 대리인으로 설정 합니다.

## <a name="team-members-and-related-settings"></a>팀 구성원 및 관련 설정

관리자는 PowerShell에서 다음 cmdlet을 사용 하 여 팀 구성원 및 관련 설정을 변경할 수 있습니다.

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

이 cmdlet은 팀 구성원의 목록을 포함 하는 개체를 반환 하 고 성공을 위해 화면에 개체를 표시 합니다. 오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

이 cmdlet은 지정 된 사용자의 팀 구성원 목록을 수정 하 고, 팀 구성원 목록이 들어 있는 개체를 반환 하며, 성공의 경우 화면에 해당 개체를 표시 합니다. 오류가 발생 하는 경우 적절 한 오류 메시지가 표시 됩니다.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

이 cmdlet은 팀 구성원을 추가 하거나 제거 합니다.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

이 cmdlet은 팀 목록을 특정 구성원으로 설정 합니다.

## <a name="more-information"></a>추가 정보

온-프레미스 배포의 경우이 기능에 도입 된 cmdlet은 아래에 지정 된 액세스 수준에 따라 다음 그룹의 구성원만 실행할 수 있습니다.

- CsAdministrator-모든 cmdlet에 대해 Get 및 Set을 사용할 수 있습니다.
- CsVoiceAdministrator-모든 cmdlet을 가져오고 설정 합니다.
- CsHelpDesk-모든 cmdlet 가져오기

이러한 관리자 역할에 대 한 자세한 내용은 [Create Skype For Business Server 제어판 Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)를 참조 하세요. 관리자는 서버 컴퓨터에 직접 또는 원격으로 로그온 하 여 이러한 cmdlet에 액세스할 수 있습니다.
하이브리드 배포의 경우 비즈니스용 Skype 관리자는 모든 cmdlet에 대해 Get 및 Set을 호출할 수 있어야 합니다. 전체 역할 목록에 대 한 자세한 내용은 [Office 365 관리자 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 를 참조 하세요.

> [!NOTE]
> 서버 자동 검색을 사용 하도록 설정 해야 합니다. Cmdlet 사용을 위해 추가 라이선스 요구 사항이 도입 되지는 않습니다.
