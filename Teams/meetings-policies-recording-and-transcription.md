---
title: 녹음/녹화 및 전사를 위한 모임 정책 관리
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: 기록 및 전사를 위해 Teams에서 모임 정책 설정을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 06a05d2eb8a8c1542b79fa4c37b68ea4a3aa6d32
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436762"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>& 기록 기록을 위한 모임 정책 설정

이 문서에서는 Teams 모임의 녹음/녹화 및 기록과 관련된 모임 정책 설정에 대해 설명합니다. 이러한 설정은 모임 **모임 정책** 아래의 팀 관리 센터에서 찾을 수 **있습니다** > .

## <a name="transcription"></a>전사

이는 이끌이별 정책과 사용자별 정책의 조합입니다. 이 설정은 모임 녹음/녹화 재생 중에 캡션 및 전사 기능을 사용할 수 있는지 여부를 제어합니다. 녹음/녹화를 시작한 사람은 이러한 기능이 레코딩에서 작동하려면 이 설정을 켜야 합니다.

이 설정을 켜면 모임 기록에서 **검색**, **참조** 및 **대본** 을 사용하는 모임 기록과 함께 저장된 대본의 사본이 생성됩니다.

## <a name="cloud-recording"></a>클라우드 기록

이 설정은 이끌이별 정책과 사용자별 정책의 조합이며 모임을 기록할 수 있는지 여부를 제어합니다. 참가자에 대한 정책 설정이 켜져 있고 동일한 조직의 인증된 사용자인 경우 모임 이끌이 또는 다른 모임 참가자가 녹음/녹화를 시작할 수 있습니다.

페더레이션 사용자 및 익명 사용자와 같은 조직 외부의 사용자는 녹음/녹화를 시작할 수 없습니다. 게스트는 녹음을 시작하거나 중지할 수 없습니다.

![녹음/녹화 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

다음 예를 살펴봅시다.

| 사용자                 | 모임 정책         | 클라우드 녹음/녹화 허용 |
|----------------------|------------------------|-----------------------|
| Daniela              | 전역                 | 해제                   |
| Amanda               | Location1MeetingPolicy | 설정                    |
| John(외부) | 해당 사항 없음         | 해당 사항 없음        |

- Daniela가 조직한 모임은 녹음할 수 없습니다.
- 아만다는 다니엘라가 주최한 모임을 녹음할 수 없다.
- Amanda가 조직한 모임은 녹음/녹화할 수 있습니다.
- 다니엘라는 아만다가 주최한 모임을 녹음할 수 없습니다.
- 존은 아만다가 조직한 모임을 녹음할 수 없다.

클라우드 모임 녹음/녹화에 대해 자세히 알아보려면 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.

## <a name="meetings-automatically-expire"></a>모임이 자동으로 만료됩니다.

이 설정은 모임 녹음/녹화가 자동으로 만료되는지 여부를 제어합니다. 이 설정을 켜면 기본 만료 시간(일 단위로 측정)을 설정하는 옵션이 제공됩니다.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="자동 모임 만료 설정의 Teams 관리 센터의 스크린샷":::

이 설정은 이전 기록에서 사용하는 스토리지의 양을 줄이는 간단한 도구를 제공합니다. OneDrive 및 SharePoint 시스템은 모든 모임 녹음/녹화에서 설정된 만료를 모니터링하고 만료 날짜에 자동으로 녹음/녹화를 휴지통으로 이동합니다.

### <a name="default-expiration-time"></a>기본 만료 시간

새로 만든 모든 모임 녹음/녹화의 기본 만료일은 120일입니다. 이 기능이 켜진 후 생성된 모든 녹음/녹화는 생성 날짜 120일 후에 삭제됩니다.

> [!NOTE]
> A1 사용자의 최대 기본 만료 시간은 30일입니다.

#### <a name="changing-default-expiration-time"></a>기본 만료 시간 변경

관리자는 PowerShell 또는 Teams 관리 센터에서 기본 만료 시간 설정을 편집할 수 있습니다. 변경 내용은 해당 시점부터 새로 만든 모임 녹음/녹화에만 영향을 줍니다. 해당 날짜 이전에 만든 녹음/녹화에는 영향을 주지 않습니다.

관리자는 기존 모임 녹음/녹화의 만료 시간을 변경할 수 없습니다. 이 작업은 기록을 소유하는 사용자의 결정을 보호하기 위해 수행됩니다. 모임과 통화는 모두 이 설정으로 제어할 수 있습니다.

만료 값은 일 수의 정수입니다.  다음과 같이 설정할 수 있습니다.

- 최소값: **1**
- 최대값: **99999**
- 녹음/녹화가 만료되지 않도록 PowerShell에서 만료 시간을 **-1** 로 설정할 수도 있습니다.

예제 PowerShell 명령:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>규정 준수

최종 사용자가 제어하는 모든 녹음/녹화의 만료 날짜를 수정할 수 있으므로 법적 보호를 위해 모임 만료 설정에 의존해서는 안 됩니다.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Microsoft Purview에서 만료 설정 및 Microsoft 365 보존 정책 기록

파일 보존은 파일 삭제보다 우선합니다. Purview 보존 정책을 사용하는 Teams 모임 녹음/녹화는 보존 기간이 완료될 때까지 Teams 모임 녹음/녹화 만료 정책에서 삭제할 수 없습니다. 예를 들어 파일이 5년 동안 유지되고 Teams 모임 녹음/녹화 만료 정책이 60일 동안 설정된 Purview 보존 정책이 있는 경우 Teams 모임 녹음/녹화 만료 정책은 5년 후에 녹음/녹화를 영구적으로 삭제합니다.

Teams 모임 녹음/녹화 만료 정책과 삭제 날짜가 다른 Purview 삭제 정책이 있는 경우 파일은 두 날짜의 가장 빠른 시간에 삭제됩니다. 예를 들어 1년 후에 파일이 삭제되고 Teams 모임 녹음/녹화 만료가 120일 동안 설정된다는 Purview 삭제 정책이 있는 경우 Teams 모임 녹음/녹화 만료 정책은 120일 후에 파일을 삭제합니다.

이를 방지하는 Purview 보존 정책이 없는 한 사용자는 만료 날짜 이전에 기록을 수동으로 삭제할 수 있습니다. 보존 기간에 있는 녹음/녹화가 사용자가 수동으로 삭제하는 경우 녹음/녹화는 보존 보존 라이브러리에 보관됩니다. 그러나 녹화는 최종 사용자에게 삭제된 것으로 표시됩니다. 자세한 내용은 [SharePoint 및 OneDrive의 보존에 대해 알아보기를 참조하세요](/microsoft-365/compliance/retention-policies-sharepoint#how-retention-works-for-sharepoint-and-onedrive).

### <a name="deletion-of-recordings"></a>녹음/녹화 삭제

녹음/녹화는 일반적으로 만료 날짜 후 하루 이내에 삭제되지만 드문 경우는 5일 정도 걸릴 수 있습니다. 녹음이 만료되면 파일 소유자는 전자 메일 알림을 받게 되며 녹음/녹화를 복구하기 위해 휴지통으로 전달됩니다.

> [!NOTE]
> 만료 날짜에 기록이 휴지통으로 이동되고 만료 날짜 필드가 지워집니다. 휴지통에서 기록을 복구하는 경우 만료 날짜가 지워졌기 때문에 이 기능에 의해 다시 삭제되지 않습니다.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Stream(클래식) 마이그레이션된 기록 만료

Stream(클래식) 마이그레이션된 녹음/녹화에는 만료 집합이 제공되지 않습니다. 대신 관리자는 보존하려는 녹음/녹화만 마이그레이션하는 것이 좋습니다. 자세한 내용은 [Stream(클래식) 마이그레이션 설명서에서](/stream/streamnew/stream-classic-to-new-migration-overview) 확인할 수 있습니다.

## <a name="store-recordings-outside-of-your-country-or-region"></a>국가 또는 지역 외부에 녹음/녹화 저장

이 정책은 모임 레코드를 다른 국가 또는 지역에 영구적으로 저장할 수 있는지 여부를 제어합니다. 이 기능을 사용하도록 설정하면 기록을 마이그레이션할 수 없습니다. 클라우드 모임 및 녹음/녹화가 저장되는 위치에 대한 자세한 내용은 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.

## <a name="related-topics"></a>관련 주제

- [Teams에서의 모임 정책 관리](meeting-policies-overview.md)
- [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
- [클라우드 모임 녹음/녹화](cloud-recording.md)
- [모임을 예약할 수 있는 사용자 관리](manage-who-can-schedule-meetings.md)
