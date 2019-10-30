---
title: MMS (모임 마이그레이션 서비스) 사용
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: MMS (모임 마이그레이션 서비스)는 백그라운드에서 실행 되며 사용자를 위해 비즈니스용 Skype 및 Microsoft 팀 모임을 자동으로 업데이트 하는 서비스입니다. MMS는 사용자가 모임 마이그레이션 도구를 실행 하 여 비즈니스용 Skype 및 Microsoft 팀 모임을 업데이트 하지 않아도 되도록 설계 되었습니다.
ms.openlocfilehash: 3f643f20937fd13b0d9576640487da30f17dd7bf
ms.sourcegitcommit: 8db50c46992dccf54c1d4be58d8a0d21ec64ddd0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772282"
---
# <a name="using-the-meeting-migration-service-mms"></a>MMS (모임 마이그레이션 서비스) 사용

이 MMS (모임 마이그레이션 서비스)는 다음과 같은 시나리오에서 사용자의 기존 모임을 업데이트 하는 서비스입니다.

- 사용자가 온-프레미스에서 클라우드로 마이그레이션 (비즈니스용 Skype Online 또는 팀 전용 등)
- 관리자가 사용자의 오디오 회의 설정을 변경 하는 경우 
- 온라인 사용자가 팀 으로만 업그레이드 되거나 TeamsUpgradePolicy의 사용자 모드가 SfBwithTeamsCollabAndMeetings로 설정 된 경우
- PowerShell을 사용 하는 경우 


기본적으로 MMS는 이러한 각 경우에 자동으로 트리거 되지만, 관리자는 테 넌 트 수준에서 사용 하지 않도록 설정할 수 있습니다. 또한 관리자는 PowerShell cmdlet을 사용 하 여 지정 된 사용자에 대 한 모임 마이그레이션을 수동으로 트리거할 수 있습니다.


**제한 사항**: 다음 중 하나라도 적용 되 면 모임 마이그레이션 서비스를 사용할 수 없습니다.

- 사용자의 사서함이 Exchange 온-프레미스에 호스팅 되었습니다.
- 사용자가 클라우드에서 비즈니스용 Skype Server 온-프레미스로 마이그레이션 중입니다.

이러한 상황에서는 최종 사용자가 [모임 마이그레이션 도구](https://www.microsoft.com/en-us/download/details.aspx?id=51659) 를 사용 하 여 자신의 모임을 대신 마이그레이션할 수 있습니다.

## <a name="how-mms-works"></a>MMS 작동 방식

지정 된 사용자에 대해 MMS를 트리거한 경우 해당 사용자에 대 한 마이그레이션 요청이 큐에 저장 됩니다. 경합 상태를 방지 하기 위해 최소 90 분이 없어질 때까지 대기 요청이 처리 되지 않습니다. MMS는 요청을 처리 하 고 나면 다음 작업을 수행 합니다.

1. 해당 사용자가 구성한 모든 기존 모임에 대해 해당 사용자의 사서함을 검색 하 고 나중에 예약 합니다.
2. 사용자의 사서함에 있는 정보에 따라 정확한 시나리오에 따라 팀 또는 비즈니스용 Skype Online에서 해당 사용자의 새 모임을 업데이트 하거나 예약 합니다.
3. 전자 메일 메시지에서 모임 세부 정보에서 온라인 모임 블록을 바꿉니다.
4. 모임 이끌이를 대신 하 여 모든 모임 받는 사람에 게 해당 모임의 업데이트 된 버전을 보냅니다. 모임 초대 대 상자는 전자 메일에 업데이트 된 모임 좌표가 있는 모임 업데이트를 받습니다. 

    ![MMS를 통해 업데이트 되는 모임 블록](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

MMS를 트리거하는 시점부터, 일반적으로 사용자의 모임이 마이그레이션될 때까지 약 2 시간이 소요 됩니다. 그러나 사용자에 게 많은 모임이 있는 경우에는 시간이 오래 걸릴 수 있습니다. MMS에서 사용자에 대 한 하나 이상의 모임을 마이그레이션하는 동안 오류가 발생 하면 24 시간 범위 동안 최대 9 번까지 다시 시도 합니다.

**참고**사항:

- 모임이 마이그레이션될 때 온라인 모임 정보 블록의 모든 내용을 MMS로 바꿉니다. 따라서 사용자가 해당 블록을 편집 하면 해당 변경 내용을 덮어쓰게 됩니다. 온라인 모임 정보 블록 외부의 모임 세부 정보에 있는 모든 콘텐츠는 영향을 받지 않습니다.
- 웹용 Outlook에서 또는 Outlook 용 Skype 모임 추가 기능을 사용 하 여 **skype 모임 추가** 단추를 클릭 하 여 예약 된 비즈니스용 Skype 또는 Microsoft 팀 모임만 마이그레이션됩니다. 사용자가 한 모임에서 Skype online 모임 정보를 복사 하 여 새 모임에 붙여 넣으면 원래 서비스에 모임이 없기 때문에 새 모임이 업데이트 되지 않습니다.
- MMS를 실행 한 후에는 모임에 만들었거나 연결 된 모임 콘텐츠 (화이트 보드, 설문 등)가 유지 되지 않습니다. 모임 이끌이가 미리 모임에 콘텐츠를 첨부 한 경우 MMS를 실행 한 후 콘텐츠를 다시 만들어야 합니다.
- 또한 Skype 모임 내에서 일정 항목의 공유 모임 메모에 대 한 링크도 덮어쓰게 됩니다. OneNote에 저장 된 실제 모임 메모는 그대로 유지 됩니다. 이는 덮어쓴 공유 메모에 대 한 링크입니다.
- 250 개 이상의 참석자 (이끌이 포함)가 포함 된 모임은 마이그레이션되지 않습니다.
- 초대 본문의 일부 유니코드 문자가 ï, ¿, 1/2, 특수 문자 중 하나로 잘못 업데이트 될 수 있습니다.

## <a name="triggering-mms-for-a-user"></a>사용자의 MMS 트리거

이 섹션에서는 다음과 같은 각 경우에 MMS를 트리거할 때 수행 되는 작업에 대해 설명 합니다.

- 사용자가 온-프레미스에서 클라우드로 마이그레이션 되는 경우
- 관리자가 사용자의 오디오 회의 설정을 변경 하는 경우 
- TeamsUpgradePolicy의 사용자 모드가 TeamsOnly 또는 SfBWithTeamsCollabAndMeetings로 설정 된 경우 (Powershell 또는 팀 관리 포털 사용)
- PowerShell cmdlet을 사용 하는 경우 시작-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>온-프레미스 사용자를 클라우드로 이동할 때 모임 업데이트

이는 MMS에서 사용자에 게 원활한 전환을 만들기 위해 사용 하는 가장 일반적인 시나리오입니다. 모임 마이그레이션이 없으면 사용자가 온라인으로 이동 하면 비즈니스용 Skype Server 온-프레미스의 사용자가 구성한 기존 모임이 더 이상 작동 하지 않습니다. 따라서 사용자를 클라우드로 이동 하기 위해 온-프레미스 관리 도구 `Move-CsUser` (또는 관리 제어판)를 사용 하는 경우 다음과 같이 기존 모임이 클라우드로 자동으로 이동 됩니다.

- If `MoveToTeams` 스위치 `Move-CsUser` 를 지정 하면 모임이 팀으로 직접 마이그레이션되고 사용자는 teamsonly 모드에 있는 것입니다. 이 스위치를 사용 하려면 비즈니스용 Skype 서버 2015 (CU8 이상)이 필요 합니다. 이러한 사용자는 비즈니스용 skype 클라이언트 또는 Skype 모임 앱을 사용 하 여 초대를 받을 수 있는 비즈니스용 Skype 모임에 계속 참가할 수 있습니다.
- 그렇지 않으면 모임이 비즈니스용 Skype Online으로 마이그레이션됩니다.

두 경우 모두 사용자에 게 클라우드로 이동 하기 전에 오디오 회의 라이선스가 할당 되 면 전화 접속 좌표를 사용 하 여 모임이 생성 됩니다. 사용자를 온-프레미스에서 클라우드로 이동 하 고 해당 사용자가 오디오 회의를 사용 하려는 경우에는 먼저 오디오 회의를 할당 한 후 1 회의 마이그레이션과만 트리거 되도록 사용자를 이동 하는 것이 좋습니다.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>사용자의 오디오 회의 설정이 변경 될 때 모임 업데이트

다음 경우에 MMS는 전화 접속 좌표를 추가, 제거 또는 수정 하기 위해 기존 비즈니스용 Skype 및 Microsoft 팀 모임을 업데이트 합니다.

- 사용자에 게 Microsoft 오디오 회의 서비스 라이선스를 할당 하거나 제거 하는 경우 해당 사용자는 타사 오디오 회의 공급자에 대해 사용 하도록 설정 되지 않은 것입니다.
- 사용자가 Microsoft 오디오 회의 라이선스를 할당 받은 경우 다른 공급자에서 Microsoft로 사용자의 오디오 회의 공급자를 변경 하는 경우 자세한 내용은 [Microsoft를 오디오 회의 공급자로 지정](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)을 참조 하세요. 또한 [이전에 발표](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)된 것 처럼 2019 년 4 월 1 일에는 제 3 자 오디오 회의 공급자에 대 한 지원이 예약 되어 있다는 점에 유의 하세요.
- 사용자에 대해 오디오 회의를 사용 하거나 사용 하지 않도록 설정 합니다.
- 공용 모임을 사용 하도록 구성 된 사용자의 전화 회의 ID를 변경 하거나 다시 설정 하는 경우
- 사용자를 새 오디오 회의 브리지로 이동 합니다.
- 오디오 회의 브리지의 전화 번호를 할당 하지 않은 경우 이는 추가 단계가 필요한 복잡 한 시나리오입니다. 자세한 내용은 [오디오 회의 브리지에서 전화 번호 변경을](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)참조 하세요.

사용자의 오디오 회의 설정에 대 한 모든 변경 내용이 MMS를 트리거하지는 않습니다. 특히 다음 두 가지 변경 사항으로 인해 MMS 업데이트는 수행 되지 않습니다.

- 모임 이끌이의 SIP 주소 (SIP 사용자 이름 또는 SIP 도메인)를 변경 하는 경우
- `Update-CsTenantMeetingUrl` 명령을 사용 하 여 조직의 모임 URL을 변경 합니다.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>TeamsUpgradePolicy 배정 시 모임 업데이트

기본적으로 모임 마이그레이션은 사용자에 게 `TeamsUpgradePolicy` `mode=TeamsOnly` 또는 `mode= SfBWithTeamsCollabAndMeetings`의 인스턴스가 부여 될 때 자동으로 트리거됩니다. 이러한 모드 중 하나를 허용할 때 모임을 마이그레이션하지 않으려는 경우 (PowerShell을 사용 하는 `MigrateMeetingsToTeams $false` 경우 `Grant-CsTeamsUpgradePolicy` )에서 지정 하거나 확인란을 선택 취소 하 여 사용자의 공존 모드 (팀 관리 포털을 사용 하는 경우)를 설정할 때 모임 마이그레이션을 수행 합니다.

또한 다음을 참고 하세요.

- 모임 마이그레이션은 특정 사용자에 게 부여 `TeamsUpgradePolicy` 하는 경우에만 호출 됩니다. `TeamsUpgradePolicy` `mode=TeamsOnly` 또는 `mode=SfBWithTeamsCollabAndMeetings` *테 넌 트 전체* 를 사용 하 여 부여 하는 경우에는 모임 마이그레이션이 호출 되지 않습니다.
- 사용자에 게 온라인 상태를 유지 하는 경우에만 팀 전용 모드를 부여할 수 있습니다. 온-프레미스 사용자는 앞에서 설명한 대로 사용 하 `Move-CsUser` 여 이동 해야 합니다.
- TeamsOnly 또는 SfBWithTeamsCollabAndMeetings 이외의 모드를 허용 하면 기존 팀 모임이 비즈니스용 Skype 모임으로 전환 되지 않습니다.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>PowerShell cmdlet을 통해 수동으로 모임 마이그레이션 트리거

자동 모임 마이그레이션 외에도 관리자는 cmdlet `Start-CsExMeetingMigration`을 실행 하 여 사용자에 대 한 모임 마이그레이션을 수동으로 트리거할 수 있습니다. 이 cmdlet은 지정 된 사용자에 대 한 마이그레이션 요청을 큐에 대기 시킵니다.  필수 `Identity` 매개 변수 외에도 다음과 같은 두 개의 선택적 매개 변수 `SourceMeetingType` `TargetMeetingType`를 사용 하 여 모임을 마이그레이션하는 방법을 지정할 수 있습니다.

**TargetMeetingType:**

- 을 `TargetMeetingType Current` 사용 하 여 비즈니스용 skype 모임이 비즈니스용 skype 모임 및 팀 모임으로 유지 되도록 지정 합니다. 그러나 오디오 회의 좌표는 변경 될 수 있으며, 온-프레미스 비즈니스용 Skype 모임은 비즈니스용 Skype Online으로 마이그레이션됩니다. 이 값이 TargetMeetingType의 기본값입니다.
- 사용 `TargetMeetingType Teams` 은 모임이 비즈니스용 Skype online 또는 온-프레미스에 호스팅 되었는지 여부와 오디오 회의 업데이트가 필요한 지 여부에 관계 없이 모든 기존 모임을 팀으로 마이그레이션해야 합니다. 

**SourceMeetingType:**
- 을 `SourceMeetingType SfB` 사용 하면 Skype for Business 모임만 (온-프레미스 또는 온라인)으로 업데이트 해야 한다는 것을 나타냅니다.
- 사용 `SourceMeetingType Teams` 은 팀 모임만 업데이트 해야 함을 나타냅니다.
- 을 `SourceMeetingType All` 사용 하 여 Skyep 비즈니스 모임 및 팀 모임 모두를 업데이트 해야 함을 나타냅니다. 이 값이 SourceMeetingType의 기본값입니다.
    

아래 예제에서는 모든 모임이 팀으로 마이그레이션될 수 있도록 사용자 ashaw@contoso.com에 대 한 모임 마이그레이션을 시작 하는 방법을 보여 줍니다.

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>MMS 관리

Windows PowerShell을 사용 하 여 진행 중인 마이그레이션 상태를 확인 하 고, 수동으로 모임 마이그레이션을 시작 하 고, 마이그레이션을 모두 사용 하지 않도록 설정할 수 있습니다. 

### <a name="check-the-status-of-meeting-migrations"></a>모임 마이그레이션 상태 확인

`Get-CsMeetingMigrationStatus` Cmdlet을 사용 하 여 모임 마이그레이션 상태를 확인 합니다. 다음은 몇 가지 예입니다.

- 모든 MMS 마이그레이션에 대 한 요약 상태를 얻으려면 모든 마이그레이션 상태의 표 형식 보기를 제공 하는 다음 명령을 실행 합니다.

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 특정 기간 내의 모든 마이그레이션에 대 한 세부 정보를 모두 보려면 `StartTime` 및 `EndTime` 매개 변수를 사용 합니다. 예를 들어 다음 명령은 2018 년 10 월 1 일부 터 2018 년 10 월 8 일 까지의 모든 마이그레이션에 대해 전체 세부 정보를 반환 합니다.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 특정 사용자에 대 한 마이그레이션 상태를 확인 하려면 `Identity` 매개 변수를 사용 합니다. 예를 들어 다음 명령을 실행 하면 사용자 ashaw@contoso.com의 상태가 반환 됩니다.

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
실패 한 마이그레이션이 표시 되는 경우 이러한 문제를 해결할 때까지 해당 사용자가 구성한 모임에 대 한 전화 접속을 할 수 없기 때문에, 가능한 한 빨리 해결 하기 위해 조치를 취해야 합니다. 에서 `Get-CsMeetingMigrationStatus` 실패 상태의 마이그레이션이 표시 되는 경우 다음 단계를 수행 합니다.
 
1. 어떤 사용자에 게 영향을 미치는지 결정 합니다. 다음 명령을 실행 하 여 영향을 받는 사용자 목록과 보고 된 특정 오류를 가져옵니다.

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 영향을 받는 각 사용자에 대해 모임 마이그레이션 도구를 실행 하 여 모임을 수동으로 마이그레이션합니다.

3. 여전히 마이그레이션이 모임 마이그레이션 도구에서 작동 하지 않으면 다음 두 가지 옵션 중에서 선택 합니다.

    - 사용자가 새 Skype 모임을 만들도록 합니다.
    - [고객 지원에 문의 하세요](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>MMS 사용 및 사용 안 함

MMS는 모든 조직에 대해 기본적으로 사용 하도록 설정 되지만 다음과 같이 사용 하지 않도록 설정할 수 있습니다.

- 테 넌 트에 대해 완전히 사용 하지 않도록 설정 합니다. 
- 오디오 회의 관련 변경 내용에 대해서만 비활성화 합니다. 이 경우 사용자를 온-프레미스에서 클라우드로 마이그레이션하거나 TeamsOnly 모드 또는 SfBWithTeamsCollabAndMeetings 모드를 사용 하도록 허용할 때 MMS는 계속 실행 됩니다 `TeamsUpgradePolicy`.

예를 들어 조직의 오디오 회의 설정을 대폭 변경 하면서 모든 모임을 수동으로 마이그레이션하거나 MMS를 일시적으로 사용 하지 않도록 설정할 수 있습니다.

조직에 MMS를 사용할 수 있는지 확인 하려면 다음 명령을 실행 합니다. 매개 변수가 있는 `MeetingMigrationEnabled` 경우 MMS를 사용할 `$true`수 있습니다.
```
Get-CsTenantMigrationConfiguration
```
MMS를 완전히 사용 하거나 사용 하지 않도록 설정 `Set-CsTenantMigrationConfiguration` 하려면 명령을 사용 합니다. 예를 들어 MMS를 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
조직에서 MMS를 사용 하도록 설정 하 고 오디오 회의 업데이트를 사용 하도록 설정 되어 있는지 확인 하려면 출력에서 `AutomaticallyMigrateUserMeetings` 매개 변수 값을 확인 `Get-CsOnlineDialInConferencingTenantSettings`합니다. 오디오 회의에 대 한 MMS를 사용 하거나 사용 `Set-CsOnlineDialInConferencingTenantSettings`하지 않도록 설정 하려면을 사용 합니다. 예를 들어 오디오 회의에 대 한 MMS를 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>관련 주제

[Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
