---
title: MMS(모임 마이그레이션 서비스) 사용
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: MMS(모임 마이그레이션 서비스)는 백그라운드에서 실행되고 사용자에 대한 모임 및 비즈니스용 Skype Microsoft Teams 업데이트하는 서비스입니다. MMS는 사용자가 모임 마이그레이션 도구를 실행하여 모임 및 모임을 업데이트할 비즈니스용 Skype Microsoft Teams 위해 디자인되었습니다.
ms.openlocfilehash: db4889bb30ec453a64bfcf760a1233fbc7c1e2f5
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282115"
---
# <a name="using-the-meeting-migration-service-mms"></a>MMS(모임 마이그레이션 서비스) 사용

MMS(모임 마이그레이션 서비스)는 다음 시나리오에서 사용자의 기존 모임을 업데이트하는 서비스입니다.

- 사용자가온-프레미스에서 클라우드로 마이그레이션되는 경우(온라인에서 또는 TeamsOnly로 비즈니스용 Skype 여부).
- 관리자가 사용자의 오디오 회의 설정을 변경하는 경우 
- 온라인 사용자가 Teams 또는 TeamsUpgradePolicy의 사용자 모드가 SfBwithTeamsCollabAndMeetings로 설정된 경우
- PowerShell을 사용하는 경우 


기본적으로 MMS는 이러한 각 경우에 자동으로 트리거됩니다. 관리자가 테넌트 수준에서 사용하지 않도록 설정할 수 있습니다. 또한 관리자는 PowerShell cmdlet을 사용하여 특정 사용자에 대한 모임 마이그레이션을 수동으로 트리거할 수 있습니다.


**제한 사항:** 다음 중 한 가지가 적용되는 경우 모임 마이그레이션 서비스를 사용할 수 없습니다.

- 사용자의 사서함은 프레미스 Exchange 호스트됩니다.
- 사용자가 클라우드에서 프레미스에서 비즈니스용 Skype 서버 마이그레이션됩니다.


## <a name="how-mms-works"></a>MMS 작동 방식

특정 사용자에 대해 MMS가 트리거되면 해당 사용자에 대한 마이그레이션 요청이 큐에 배치됩니다. 레이스 조건을 피하기 위해 대기 중인 요청은 90분 이상이 지날 때까지 고의로 처리되지 않습니다. MMS가 요청을 처리하면 다음 작업을 수행합니다.

1. 해당 사용자가 구성하고 향후에 예약된 모든 기존 모임에 대해 해당 사용자의 사서함을 검색합니다.
2. 사용자의 사서함에 있는 정보에 따라 정확한 시나리오에 따라 해당 사용자의 Teams 비즈니스용 Skype 새 모임을 업데이트하거나 예약합니다.
3. 전자 메일 메시지에서 모임 세부 정보의 온라인 모임 블록을 대체합니다.
4. 모임 이끌이를 대신하여 해당 모임의 업데이트된 버전을 모든 모임 받는 사람에게 보냅니다. 모임 초대자는 전자 메일에 업데이트된 모임 좌표가 있는 모임 업데이트를 받게 됩니다. 

    ![MMS로 업데이트되는 모임 블록](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

MMS가 트리거되는 시간부터 일반적으로 사용자의 모임이 마이그레이션될 때까지 약 2시간이 소요됩니다. 그러나 사용자가 많은 수의 모임을 가지는 경우 시간이 더 오래 걸릴 수 있습니다. MMS에서 사용자에 대해 하나 이상의 모임을 마이그레이션하는 오류가 발생하면 24시간 동안 주기적으로 최대 9번까지 다시 시도합니다.

**참고:**

- MMS는 모임을 마이그레이션할 때 온라인 모임 정보 블록의 모든 것을 대체합니다. 따라서 사용자가 해당 블록을 편집한 경우 해당 변경 내용이 덮어질 것입니다. 온라인 모임 정보 블록 외부의 모임 세부 정보에 있는 콘텐츠는 영향을 받지 않습니다. 즉, 모임 초대에 연결된 모든 파일이 여전히 포함됩니다. 
- 웹에서 비즈니스용 Skype Microsoft Teams 추가 Skype 단추를 클릭하거나 웹용 Outlook  추가 기능을 사용하여 예약된 Skype 모임 또는 Outlook 모임만 마이그레이션됩니다. 사용자가 한 모임에서 새 Skype 온라인 모임 정보를 복사하여 붙여넣는 경우 원래 서비스에 모임이 없는 경우 새 모임은 업데이트되지 않습니다.
- 모임을 만들거나 모임에 연결된 모임 콘텐츠(화이트보드, 설문 조사 등)는 MMS가 실행된 후에 유지되지 않습니다. 모임 이끌이가 모임에 미리 콘텐츠를 첨부한 경우 MMS가 실행된 후에 콘텐츠를 다시 구성해야 합니다.
- 일정 항목의 공유 모임 노트에 대한 링크도 Skype 덮어 덮어 덮습니다. 에 저장된 실제 모임 OneNote 여전히 있습니다. 덮어 덮어 작성된 공유 노트에 대한 링크일 뿐입니다.
- 250명 이상의 참석자가 있는 모임(이끌이 포함)은 마이그레이션되지 않습니다.
- 초대 본문에 있는 일부 유니코드 문자는 다음과 같은 특수 문자 중 하나인 ly, ', 1/2, 으로 잘못 업데이트될 수 있습니다.

## <a name="triggering-mms-for-a-user"></a>사용자에 대한 MMS 트리거

이 섹션에서는 다음 각 경우에 MMS가 트리거될 때 발생하는 작업을 설명합니다.

- 사용자가온-프레미스에서 클라우드로 마이그레이션된 경우
- 관리자가 사용자의 오디오 회의 설정을 변경하는 경우 
- TeamsUpgradePolicy의 사용자 모드가 TeamsOnly 또는 SfBWithTeamsCollabAndMeetings로 설정되는 경우(Powershell 또는 Teams 관리 포털 사용)
- PowerShell cmdlet을 사용하는 경우 Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>클라우드로 사용자를 이동하는 경우 모임 업데이트

MMS가 사용자에게 더 원활한 전환을 만드는 데 도움이 되는 가장 일반적인 시나리오입니다. 모임 마이그레이션이 없는 경우 사용자가 온라인으로 이동하면 비즈니스용 Skype 서버 사용자가 구성한 기존 모임이 더 이상 작동하지 않습니다. 따라서 사용자를 클라우드로 이동하기 위해 프레미스 관리 도구(또는 관리 제어판)를 사용하는 경우 기존 모임은 다음과 같이 자동으로 클라우드로 `Move-CsUser` 이동됩니다.

- 전환을 지정하면 모임이 직접 Teams TeamsOnly 모드로 `MoveToTeams` `Move-CsUser` 전환됩니다. 이 스위치를 사용하려면 CU8 비즈니스용 Skype 서버 2015 이상이 필요합니다. 이러한 사용자는 여전히 비즈니스용 Skype 클라이언트 또는 비즈니스용 Skype 앱을 사용하여 초대할 Skype 모임 있습니다.
- 그렇지 않으면 모임이 온라인 비즈니스용 Skype 마이그레이션됩니다.

두 경우 모두 사용자가 클라우드로 이동하기 전에 오디오 회의 라이선스를 할당한 경우 전화 접속 좌표를 사용하여 모임이 만들어집니다. 사용자를 프레미스에서 클라우드로 이동하고 해당 사용자가 오디오 회의를 사용하려는 경우 먼저 사용자를 이동하기 전에 오디오 회의를 할당하여 모임 마이그레이션이 1개만 트리거되는 것이 좋습니다.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>사용자의 오디오 회의 설정이 변경될 때 모임 업데이트

다음 경우 MMS는 기존 비즈니스용 Skype 업데이트하고 Microsoft Teams 전화 접속 좌표를 추가, 제거 또는 수정합니다.

- 사용자에게 Microsoft 오디오 회의 서비스 라이선스를 할당하거나 제거하는 경우 해당 사용자가 타사 오디오 회의 공급자에 대해 사용하도록 설정되지 않습니다.
- 사용자의 오디오 회의 공급자를 다른 공급자에서 Microsoft로 변경하는 경우 사용자에게 Microsoft 오디오 회의 라이선스가 할당된 경우. 자세한 내용은 오디오 회의 공급자로 Microsoft 할당을 [참조하세요.](./assign-microsoft-as-the-audio-conferencing-provider.md) 또한 이전에 발표한 처럼 타사 오디오 회의 공급자 [ACP]에 대한 지원이 2019년 4월 1일 종료 [예정입니다.](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)
- 사용자에 대한 오디오 회의를 사용하도록 설정하거나 사용하지 않도록 설정하면 됩니다.
- 공개 모임을 사용하도록 구성된 사용자의 회의 ID를 변경하거나 다시 설정하는 경우.
- 사용자를 새 오디오 회의 브리지로 이동하면
- 오디오 회의 브리지의 전화 번호가 부가되지 않은 경우. 추가 단계가 필요한 복잡한 시나리오입니다. 자세한 내용은 오디오 회의 브리지의 전화 번호 [변경을 참조하세요.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

사용자의 오디오 회의 설정에 대한 모든 변경 내용이 MMS를 트리거하지는 않습니다. 특히 다음 두 가지 변경 내용은 MMS에서 모임을 업데이트하지 않습니다.

- 모임 이끌이의 SIP 주소(해당 SIP 사용자 이름 또는 해당 SIP 도메인)를 변경하는 경우
- 명령을 사용하여 조직의 모임 URL을 `Update-CsTenantMeetingUrl` 변경합니다.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>TeamsUpgradePolicy를 할당할 때 모임 업데이트

기본적으로 사용자가 와 또는 의 인스턴스를 부여하면 모임 마이그레이션이 자동으로 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode= SfBWithTeamsCollabAndMeetings` 트리거됩니다. 이러한 모드 중 하나를 부여할 때 모임을 마이그레이션하지 않을 경우(PowerShell을 사용하는 경우) 사용자의 공존 모드(관리자 포털을 사용하는 경우)를 설정할 때 모임을 마이그레이션할 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` 확인란을 Teams 합니다.

또한 다음을 참고합니다.

- 모임 마이그레이션은 특정 사용자에게 부여할 `TeamsUpgradePolicy` 때만 호출됩니다. 테넌트 전체에 부여하거나 부여하는 경우 `TeamsUpgradePolicy` `mode=TeamsOnly` 모임 `mode=SfBWithTeamsCollabAndMeetings` 마이그레이션이 호출되지 않습니다. 
- 사용자가 온라인에 있는 경우 TeamsOnly 모드만 부여할 수 있습니다. 홈이 있는 프레미스 사용자는 앞서 설명한 바와 같이 `Move-CsUser` 이동해야 합니다.
- TeamsOnly 또는 SfBWithTeamsCollabAndMeetings가 아닌 모드를 부여하는 것은 기존 Teams 모임을 비즈니스용 Skype 않습니다.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>PowerShell cmdlet을 통해 수동으로 모임 마이그레이션 트리거

관리자는 자동 모임 마이그레이션 외에도 cmdlet을 실행하여 사용자에 대한 모임 마이그레이션을 수동으로 트리거할 수 `Start-CsExMeetingMigration` 있습니다. 이 cmdlet은 지정된 사용자에 대한 마이그레이션 요청을 큐에 대기합니다.  필요한 매개 변수 외에도 두 개의 선택적 매개 변수가 `Identity` `SourceMeetingType` 필요하며, 을 사용하여 모임을 마이그레이션하는 방법을 지정할 `TargetMeetingType` 수 있습니다.

**TargetMeetingType:**

- 사용은 비즈니스용 Skype 모임에 비즈니스용 Skype 남아 있으며 Teams 모임은 Teams `TargetMeetingType Current` 지정합니다. 그러나 오디오 회의 좌표가 변경될 수 있으며 모든 비즈니스용 Skype 모든 비즈니스용 Skype 온라인으로 마이그레이션됩니다. TargetMeetingType의 기본값입니다.
- 사용은 모임이 온라인 또는 비즈니스용 Skype 여부와 오디오 회의 업데이트가 필요한지 여부에 관계없이 기존 모임을 Teams 마이그레이션해야 를 `TargetMeetingType Teams` 지정합니다. 

**SourceMeetingType:**
- 사용은 비즈니스용 Skype 모임만 업데이트해야 한다고 `SourceMeetingType SfB` 나타냅니다.
- 사용은 `SourceMeetingType Teams` Teams 모임만 업데이트해야 한다고 나타냅니다.
- 사용은 비즈니스용 Skype 모임 및 Teams 모두 업데이트해야 `SourceMeetingType All` 한다고 나타냅니다. SourceMeetingType의 기본값입니다.
    

아래 예제에서는 모든 모임을 ashaw@contoso.com 사용자에 대한 모임 마이그레이션을 시작하는 방법을 Teams.

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>MMS 관리

Windows PowerShell 마이그레이션 상태를 확인하고, 모임 마이그레이션을 수동으로 트리거하고, 마이그레이션을 사용하지 않도록 설정할 수 있습니다. 

### <a name="check-the-status-of-meeting-migrations"></a>모임 마이그레이션 상태 확인

cmdlet을 사용하여 모임 마이그레이션의 상태를 `Get-CsMeetingMigrationStatus` 검사합니다. 다음은 몇 가지 예입니다.

- 모든 MMS 마이그레이션의 요약 상태를 얻게 하려는 경우 모든 마이그레이션 상태의 테이블 보기를 제공하는 다음 명령을 실행합니다.

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 특정 기간 내에 모든 마이그레이션에 대한 전체 세부 정보를 얻게 하려는 경우 및 매개 `StartTime` 변수를 `EndTime` 사용합니다. 예를 들어 다음 명령은 2018년 10월 1일에서 2018년 10월 8일까지 발생한 모든 마이그레이션에 대한 전체 세부 정보를 반환합니다.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 특정 사용자에 대한 마이그레이션 상태를 확인하려는 경우 매개 변수를 `Identity` 사용합니다. 예를 들어 다음 명령은 사용자에 대한 상태를 ashaw@contoso.com.

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
실패한 마이그레이션이 표시되면 사용자가 해당 문제를 해결할 때까지 해당 사용자가 구성한 모임에 전화 접속할 수 없습니다. 실패한 `Get-CsMeetingMigrationStatus` 상태의 마이그레이션이 표시된 경우 다음 단계를 수행합니다.
 
1. 영향을 받는 사용자를 파악합니다. 다음 명령을 실행하여 영향을 받는 사용자의 목록과 보고된 특정 오류를 얻게 됩니다.

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 영향을 받는 각 사용자에 대해 모임 마이그레이션 도구를 실행하여 모임을 수동으로 마이그레이션합니다.

3. 마이그레이션이 모임 마이그레이션 도구에서 여전히 작동하지 않는 경우 다음 두 가지 옵션이 있습니다.

    - 사용자가 새 모임을 Skype 합니다.
    - [지원에 문의합니다.](/microsoft-365/Admin/contact-support-for-business-products)


### <a name="enabling-and-disabling-mms"></a>MMS 사용 및 사용 안 림

MMS는 기본적으로 모든 조직에서 사용하도록 설정되지만 다음과 같이 사용하지 않도록 설정할 수 있습니다.

- 테넌트에 대해 완전히 사용하지 않도록 설정합니다. 
- 오디오 회의와 관련된 변경 내용에만 사용하지 않도록 설정합니다. 이 경우 MMS는 사용자가온-프레미스에서 클라우드로 마이그레이션되거나 TeamsOnly 모드 또는 SfBWithTeamsCollabAndMeetings 모드를 부여할 때 계속 `TeamsUpgradePolicy` 실행됩니다.

예를 들어 조직에 대한 오디오 회의 설정을 크게 변경하는 동안 모든 모임을 수동으로 마이그레이션하거나 MMS를 일시적으로 사용하지 않도록 설정할 수 있습니다.

조직에서 MMS를 사용하도록 설정되어 있는지 확인하기 위해 다음 명령을 실행합니다. 매개 변수가 `MeetingMigrationEnabled` 이면 MMS가 `$true` 활성화됩니다.
```PowerShell
Get-CsTenantMigrationConfiguration
```
MMS를 완전히 사용하도록 설정하거나 사용하지 않도록 설정하려면 명령을 `Set-CsTenantMigrationConfiguration` 사용 합니다. 예를 들어 MMS를 사용하지 않도록 설정하면 다음 명령을 실행합니다.

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
조직에서 MMS를 사용하도록 설정하고 오디오 회의 업데이트에 사용하도록 설정되어 있는지 확인하려는 경우 출력의 매개 변수 값을 `AutomaticallyMigrateUserMeetings` `Get-CsOnlineDialInConferencingTenantSettings` 확인합니다. 오디오 회의에 MMS를 사용하도록 설정하거나 사용하지 않도록 설정하려면 를 사용 `Set-CsOnlineDialInConferencingTenantSettings` 합니다. 예를 들어 오디오 회의를 위해 MMS를 사용하지 않도록 설정하면 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>관련 주제

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[온-프레미스와 클라우드 간에 사용자 이동](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
