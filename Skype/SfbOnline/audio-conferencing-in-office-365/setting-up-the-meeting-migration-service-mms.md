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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: MMS(모임 마이그레이션 서비스)는 백그라운드에서 실행되고 사용자에 대한 비즈니스용 Skype 및 Microsoft Teams 모임을 자동으로 업데이트하는 서비스입니다.
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671644"
---
# <a name="using-the-meeting-migration-service-mms"></a>MMS(모임 마이그레이션 서비스) 사용

MMS(모임 마이그레이션 서비스)는 다음 시나리오에서 사용자의 기존 모임을 업데이트하는 서비스입니다.

- 사용자가 온-프레미스에서 클라우드로 마이그레이션되는 경우
- 관리자가 사용자의 오디오 회의 설정을 변경하는 경우
- 온라인 사용자가 Teams만 업그레이드되거나 TeamsUpgradePolicy의 사용자 모드가 SfBwithTeamsCollabAndMeetings로 설정된 경우
- PowerShell을 사용하는 경우

기본적으로 MMS는 이러한 각 경우에 자동으로 트리거됩니다. 또한 관리자는 PowerShell cmdlet을 사용하여 지정된 사용자에 대한 모임 마이그레이션을 수동으로 트리거할 수 있습니다.

**제한 사항**: 다음 중 어떤 것이 적용되는 경우 모임 마이그레이션 서비스를 사용할 수 없습니다.

- 사용자의 사서함은 Exchange 온-프레미스에서 호스팅됩니다.
- 사용자가 클라우드에서 온-프레미스에서 비즈니스용 Skype 서버 마이그레이션되고 있습니다.

## <a name="how-mms-works"></a>MMS 작동 방식

지정된 사용자에 대해 MMS가 트리거되면 해당 사용자에 대한 마이그레이션 요청이 큐에 배치됩니다. 경합 조건을 방지하기 위해 대기 중인 요청은 최소 90분이 지나기 전까지 의도적으로 처리되지 않습니다. MMS가 요청을 처리하면 다음 작업을 수행합니다.

1. 해당 사용자의 사서함에서 해당 사용자가 구성하고 나중에 예약한 모든 기존 모임을 검색합니다.
2. 사용자의 사서함에 있는 정보에 따라 정확한 시나리오에 따라 해당 사용자에 대한 Teams 새 모임을 업데이트하거나 예약합니다.
3. 전자 메일 메시지에서 모임 세부 정보에서 온라인 모임 블록을 바꿉니다.
4. 모임 이끌이를 대신하여 모든 모임 받는 사람에게 해당 모임의 업데이트된 버전을 보냅니다. 모임 초대자는 전자 메일에 업데이트된 모임 좌표가 포함된 모임 업데이트를 받게 됩니다.

    ![MMS에서 업데이트되는 모임 블록입니다.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

MMS가 트리거되는 시점부터 일반적으로 사용자의 모임이 마이그레이션될 때까지 약 2시간이 걸립니다. 그러나 사용자에게 많은 수의 모임이 있는 경우 시간이 더 오래 걸릴 수 있습니다. MMS에서 사용자에 대해 하나 이상의 모임을 마이그레이션하는 동안 오류가 발생하면 24시간 동안 최대 9번 주기적으로 다시 시도합니다.

**참고**:

- MMS는 모임이 마이그레이션될 때 온라인 모임 정보 블록의 모든 항목을 대체합니다. 따라서 사용자가 해당 블록을 편집한 경우 변경 내용을 덮어씁니다. 온라인 모임 정보 블록 외부의 모임 세부 정보에 있는 모든 콘텐츠는 영향을 받지 않습니다. 즉, 모임 초대에 첨부된 모든 파일이 계속 포함됩니다.
- 웹 Outlook Skype 추가 단추를 클릭하거나 Outlook Skype 모임 추가 기능을 사용하여 예약된 비즈니스용 Skype 또는 Microsoft Teams **모임** 만 마이그레이션됩니다. 사용자가 한 모임에서 새 모임으로 Skype 온라인 모임 정보를 복사하여 붙여넣는 경우 원래 서비스에 모임이 없으므로 새 모임이 업데이트되지 않습니다.
- 모임(화이트보드, 설문 조사 등)을 만들거나 모임에 첨부한 모임 콘텐츠는 MMS 실행 후에 유지되지 않습니다. 모임 이끌이가 사전에 모임에 콘텐츠를 첨부한 경우 MMS가 실행된 후에 콘텐츠를 다시 만들어야 합니다.
- 일정 항목 및 Skype 모임 내의 공유 모임 노트에 대한 링크도 덮어씁니다. OneNote 저장된 실제 모임 노트는 여전히 존재합니다. 덮어쓰여진 공유 노트에 대한 링크일 뿐입니다.
- 참석자가 250명 이상인 모임(이끌이 포함)은 마이그레이션되지 않습니다.
- 초대 본문의 일부 유니코드 문자가 다음 특수 문자 중 하나로 잘못 업데이트될 수 있습니다. ï, -, 1/2.

## <a name="triggering-mms-for-a-user"></a>사용자에 대한 MMS 트리거

이 섹션에서는 다음 각 경우에 MMS가 트리거될 때 발생하는 상황에 대해 설명합니다.

- 사용자가 온-프레미스에서 클라우드로 마이그레이션되는 경우
- 관리자가 사용자의 오디오 회의 설정을 변경하는 경우
- TeamsUpgradePolicy의 사용자 모드가 TeamsOnly 또는 SfBWithTeamsCollabAndMeetings로 설정된 경우(Powershell 또는 Teams 관리 포털 사용)
- PowerShell cmdlet을 사용하는 경우 Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>온-프레미스 사용자를 클라우드로 이동할 때 모임 업데이트

이는 MMS가 사용자에게 보다 원활한 전환을 만드는 데 도움이 되는 가장 일반적인 시나리오입니다. 모임 마이그레이션이 없으면 비즈니스용 Skype 서버 온-프레미스에서 사용자가 구성한 기존 모임은 사용자가 온라인으로 이동하면 더 이상 작동하지 않습니다. 따라서 온-프레미스 관리 도구(또는 `Move-CsUser` 관리 제어판)를 사용하여 사용자를 클라우드로 이동하면 기존 모임이 자동으로 클라우드로 이동되고 TeamsOnly로 변환됩니다.

사용자에게 클라우드로 이동하기 전에 오디오 회의 라이선스가 할당된 경우 전화 접속 좌표로 모임이 만들어집니다. 사용자를 온-프레미스에서 클라우드로 이동하고 해당 사용자가 오디오 회의 사용하려는 경우 사용자를 이동하기 전에 먼저 오디오 회의를 할당하여 모임 마이그레이션이 1개만 트리거되도록 하는 것이 좋습니다.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>사용자의 오디오 회의 설정이 변경되면 모임 업데이트

다음 경우 MMS는 기존 비즈니스용 Skype 및 Microsoft Teams 모임을 업데이트하여 전화 접속 좌표를 추가, 제거 또는 수정합니다.

- 사용자에게 Microsoft 오디오 회의 서비스 라이선스를 할당하거나 제거하는 경우 해당 사용자는 타사 오디오 회의 공급자에 대해 사용하도록 설정되지 않습니다.
- 사용자의 오디오 회의 공급자를 다른 공급자에서 Microsoft로 변경하는 경우 사용자에게 Microsoft 오디오 회의 라이선스가 할당된 경우 자세한 내용은 [오디오 회의 공급자로 Microsoft 할당을](./assign-microsoft-as-the-audio-conferencing-provider.md) 참조하세요. 또한 타사 오디오 회의 공급자[ACP]에 대한 지원은 [이전에 발표된](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md) 대로 2019년 4월 1일에 수명이 종료될 예정입니다.
- 사용자에 대해 오디오 회의를 사용하거나 사용하지 않도록 설정하는 경우
- 공개 모임을 사용하도록 구성된 사용자의 전화 회의 ID를 변경하거나 다시 설정하는 경우
- 사용자를 새 오디오 회의 브리지로 이동하는 경우
- 오디오 회의 브리지의 전화 번호가 할당되지 않은 경우 이는 추가 단계가 필요한 복잡한 시나리오입니다. 자세한 내용은 [오디오 회의 브리지의 전화 번호 변경을 참조하세요](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

사용자의 오디오 회의 설정에 대한 모든 변경 내용이 MMS를 트리거하는 것은 아닙니다. 특히 다음과 같은 두 가지 변경으로 인해 MMS가 모임을 업데이트하지 않습니다.

- 모임 이끌이의 SIP 주소(SIP 사용자 이름 또는 해당 SIP 도메인)를 변경하는 경우
- 명령을 사용하여 조직의 모임 URL을 `Update-CsTenantMeetingUrl` 변경하는 경우

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>TeamsUpgradePolicy를 할당할 때 모임 업데이트

기본적으로 모임 마이그레이션은 사용자에게 with 또는 `mode= SfBWithTeamsCollabAndMeetings`.의 `TeamsUpgradePolicy` `mode=TeamsOnly` 인스턴스가 부여될 때 자동으로 트리거됩니다. 이러한 모드 중 하나를 부여할 때 모임을 마이그레이션하지 않으려면(PowerShell을 사용하는 경우) 사용자의 공존 모드 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` 를 설정할 때(Teams 관리 포털을 사용하는 경우) 확인란을 선택 취소하여 모임을 마이그레이션합니다.

또한 다음 사항에 유의하세요.

- 모임 마이그레이션은 특정 사용자에 대해 부여 `TeamsUpgradePolicy` 할 때만 호출됩니다. *테넌트 전체에* 부여하거나 `mode=SfBWithTeamsCollabAndMeetings` 테넌트 전체에서 부여하는 `TeamsUpgradePolicy` `mode=TeamsOnly` 경우 모임 마이그레이션이 호출되지 않습니다.
- 사용자가 온라인 홈인 경우에만 TeamsOnly 모드를 부여할 수 있습니다. 온-프레미스에 있는 사용자는 앞에서 설명한 대로 이동 `Move-CsUser` 해야 합니다.
- TeamsOnly 또는 SfBWithTeamsCollabAndMeetings 이외의 모드를 부여해도 기존 Teams 모임은 비즈니스용 Skype 모임으로 변환되지 않습니다.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>PowerShell cmdlet을 통해 수동으로 모임 마이그레이션 트리거

관리자는 자동 모임 마이그레이션 외에도 cmdlet `Start-CsExMeetingMigration`을 실행하여 사용자에 대한 모임 마이그레이션을 수동으로 트리거할 수 있습니다. 이 cmdlet은 지정된 사용자에 대한 마이그레이션 요청을 큐에 대기합니다.  필수 `Identity` 매개 변수 외에도 두 개의 선택적 매개 변수 `SourceMeetingType` `TargetMeetingType`를 사용하고 모임을 마이그레이션하는 방법을 지정할 수 있습니다.

**TargetMeetingType:**

- 비즈니스용 Skype `TargetMeetingType Current` 모임은 비즈니스용 Skype 유지되고 Teams 모임은 모임 Teams 유지되도록 지정합니다. 그러나 오디오 회의 좌표가 변경될 수 있으며 온-프레미스 비즈니스용 Skype 모임은 비즈니스용 Skype Online으로 마이그레이션됩니다. TargetMeetingType의 기본값입니다.
- 모임 `TargetMeetingType Teams` 이 비즈니스용 Skype 온라인 또는 온-프레미스에서 호스팅되는지 여부와 관계없이 오디오 회의 업데이트가 필요한지 여부에 관계없이 기존 모임을 Teams 마이그레이션해야 합니다.

**SourceMeetingType:**

- 사용 `SourceMeetingType SfB` 은 비즈니스용 Skype 모임(온-프레미스 또는 온라인)만 업데이트해야 했음을 나타냅니다.
- 사용 `SourceMeetingType Teams` 은 Teams 모임만 업데이트해야 했음을 나타냅니다.
- 사용 `SourceMeetingType All` 은 비즈니스용 Skype 모임과 Teams 모임을 모두 업데이트해야 했음을 나타냅니다. SourceMeetingType의 기본값입니다.

아래 예제에서는 모든 모임이 Teams 마이그레이션되도록 사용자 ashaw@contoso.com 대한 모임 마이그레이션을 시작하는 방법을 보여 줍니다.

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>MMS 관리

Windows PowerShell 사용하여 진행 중인 마이그레이션의 상태를 확인하고, 모임 마이그레이션을 수동으로 트리거하고, 마이그레이션을 완전히 사용하지 않도록 설정할 수 있습니다.

### <a name="check-the-status-of-meeting-migrations"></a>모임 마이그레이션 상태 확인

cmdlet을 `Get-CsMeetingMigrationStatus` 사용하여 모임 마이그레이션의 상태를 확인합니다. 다음은 몇 가지 예입니다.

- 모든 MMS 마이그레이션의 요약 상태를 얻으려면 모든 마이그레이션 상태에 대한 테이블 형식 보기를 제공하는 다음 명령을 실행합니다.

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- 특정 기간 내에 모든 마이그레이션에 대한 전체 세부 정보를 얻으려면 해당 및 `EndTime` 매개 변수를 `StartTime` 사용합니다. 예를 들어 다음 명령은 2018년 10월 1일부터 2018년 10월 8일까지 발생한 모든 마이그레이션에 대한 전체 세부 정보를 반환합니다.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- 특정 사용자에 대한 마이그레이션 상태를 확인하려면 매개 변수를 `Identity` 사용합니다. 예를 들어 다음 명령은 사용자 ashaw@contoso.com 상태를 반환합니다.

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

실패한 마이그레이션이 표시되는 경우 사용자가 해결할 때까지 해당 사용자가 구성한 모임에 전화 접속할 수 없으므로 가능한 한 빨리 이러한 문제를 해결하기 위한 조치를 취합니다. 실패한 상태의 마이그레이션이 표시되면 `Get-CsMeetingMigrationStatus` 다음 단계를 수행합니다.

1. 영향을 받는 사용자를 확인합니다. 다음 명령을 실행하여 영향을 받는 사용자 목록과 보고된 특정 오류를 가져옵니다.

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. 영향을 받는 각 사용자에 대해 LastMessage 속성의 값을 검토하여 모임 마이그레이션에 실패한 이유와 수행할 수정 작업을 확인합니다. 수정 작업이 수행되면 위에서 설명한 대로 PowerShell cmldet을 사용하여 `Start-CsExMeetingMigration` 영향을 받는 사용자에 대한 모임 마이그레이션을 다시 트리거합니다.

3. 마이그레이션이 여전히 작동하지 않는 경우 다음 두 가지 옵션이 있습니다.

    - 사용자가 새 Skype 모임을 만들게 합니다.
    - [고객 지원에 문의하세요](/microsoft-365/Admin/contact-support-for-business-products).

이 cmdlet을 `Get-CsMeetingMigrationStatus` 사용하여 지난 150일 이내에 트리거된 마이그레이션 상태를 검색할 수 있습니다. 150일보다 오래된 마이그레이션에 대한 레코드는 시스템에서 제거됩니다.

### <a name="enabling-and-disabling-mms"></a>MMS 사용 및 사용 안 함

MMS는 기본적으로 모든 조직에서 사용하도록 설정되지만 다음과 같이 사용하지 않도록 설정할 수 있습니다.

- 테넌트에 대해 완전히 사용하지 않도록 설정합니다.
- 오디오 회의와 관련된 변경 내용에 대해서만 사용하지 않도록 설정합니다. 이 경우 사용자가 온-프레미스에서 클라우드로 마이그레이션되거나 TeamsOnly 모드 또는 SfBWithTeamsCollabAndMeetings 모드 `TeamsUpgradePolicy`를 부여할 때 MMS가 계속 실행됩니다.

예를 들어 조직의 오디오 회의 설정을 크게 변경하는 동안 모든 모임을 수동으로 마이그레이션하거나 MMS를 일시적으로 사용하지 않도록 설정할 수 있습니다.

조직에서 MMS를 사용할 수 있는지 확인하려면 다음 명령을 실행합니다. 매개 변수가 .인 경우 MMS를 `MeetingMigrationEnabled` 사용할 수 있습니다 `$true`.

```PowerShell
Get-CsTenantMigrationConfiguration
```

조직에서 MMS를 사용하도록 설정하고 오디오 회의 업데이트에 사용할 수 있는지 확인하려면 출력`Get-CsOnlineDialInConferencingTenantSettings`에서 매개 변수 값을 `AutomaticallyMigrateUserMeetings` 확인합니다. 오디오 회의에 MMS를 사용하거나 사용하지 않도록 설정하려면 다음을 사용합니다 `Set-CsOnlineDialInConferencingTenantSettings`. 예를 들어 오디오 회의에 MMS를 사용하지 않도록 설정하려면 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365 오디오 회의 구입](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[온-프레미스와 클라우드 간에 사용자 이동](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
