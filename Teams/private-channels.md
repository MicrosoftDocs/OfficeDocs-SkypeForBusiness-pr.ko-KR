---
title: Microsoft Teams의 비공개 채널
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams에서 비공개 채널을 사용하고 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 912a9f7f9330bcc8da167c7435048d1ec8c28284
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269883"
---
# <a name="private-channels-in-microsoft-teams"></a>Microsoft Teams의 비공개 채널

Microsoft Teams의 비공개 채널은 팀 내 공동 작업을 위한 집중적인 공간을 만들어 줍니다. 비공개 채널의 소유자나 구성원인 팀 사용자만 채널에 액세스할 수 있습니다. 이미 팀 구성원인 경우 게스트를 포함한 모든 사용자가 비공개 채널의 구성원으로 추가될 수 있습니다.

관리할 추가 팀을 따로 만들 필요 없이 정보를 알아야 하는 사람에게만 공동 작업을 제한하려거나 특정 프로젝트에 할당된 그룹 간의 커뮤니케이션을 용이하게 하려는 경우 비공개 채널을 사용하는 것이 좋습니다.

예를 들어 다음과 같은 경우에 비공개 채널이 유용합니다.

- 팀의 여러 사용자가 별도의 팀을 만들지 않고도 공동 작업을 할 수 있는 집중적인 공간입니다.
- 팀 내 일부 그룹의 사람들은 예산, 자원 조달, 전략적 배치 등과 같은 중요한 정보를 논의하기 위해 비공개 채널을 희망합니다.

비공개 채널을 나타내는 자물쇠 아이콘. 비공개 채널의 구성원으로 추가된 사용자만 비공개 채널을 볼 수 있고 여기에 참여할 수 있습니다.

비공개 채널이 만들어지면 해당 채널이 상위 팀에 연결되어 다른 팀으로 이동할 수 없습니다. 또한 비공개 채널은 표준 채널로 전환할 수 없으며, 그 반대로도 전한할 수 없습니다.

[비공개 채널을 다른 유형의 채널과 비교합니다](/microsoftteams/teams-channels-overview#channel-feature-comparison).

![팀 내 비공개 채널의 스크린샷.](media/private-channels-in-teams.png)

## <a name="private-channel-creation"></a>비공개 채널 만들기

기본적으로 팀 소유자 또는 팀 구성원은 비공개 채널을 만들 수 있습니다. 게스트는 만들 수 없습니다. 비공개 채널을 만드는 기능은 팀 수준 및 조직 수준에서 관리됩니다. 관리자는 [정책](teams-policies.md)을 사용하여 조직의 어떤 사용자가 비공개 채널을 만들도록 허용되는지를 제어할 수 있습니다. 정책을 설정한 후 팀의 **설정** 탭에서 팀 소유자는 구성원이 비공개 채널을 만들 수 있는 기능을 설정하거나 해제할 수 있습니다.

비공개 채널을 만드는 사람은 비공개 채널 소유자가 되며 비공개 채널 소유자만 구성원을 직접 채널에 추가하거나 채널에서 제거할 수 있습니다. 비공개 채널 소유자는 본인이 만든 비공개 채널에 팀 구성원(게스트 포함)을 추가할 수 있습니다. 비공개 채널의 구성원은 보안이 적용된 대화 공간을 갖게 되며, 새로 추가된 구성원도 해당 비공개 채널의 모든 대화(기존 대화도)를 볼 수 있습니다.

팀 소유자는 팀 내 모든 비공개 치널의 이름을 볼 수 있으며, 팀 내 어떤 비공개 채널이든 삭제할 수도 있습니다. (삭제된 비공개 채널은 삭제된 후 30일 이내에 복원할 수 있습니다.) 팀 소유자가 비공개 채널의 구성원이 아니면 대화 또는 비공개 채널 내 파일 및 비공개 채널의 구성원 목록을 볼 수 없습니다.

팀 구성원은 자신이 추가된 비공개 채널만 볼 수 있습니다.

## <a name="adding-and-removing-owners-and-members"></a>소유자와 구성원 추가 및 제거

비공개 채널 소유자가 하나 이상의 비공개 채널을 운영하는 마지막 소유자일 경우 Teams 클라이언트를 통해 제거할 수 없습니다.

비공개 채널 소유자가 조직을 떠나거나 팀과 연결된 Microsoft 365 그룹에서 제거될 경우 비공개 채널의 구성원이 자동으로 비공개 채널 소유자로 승격합니다.

팀 구성원이 나가거나 팀에서 제거될 경우 해당 사용자는 팀 내 모든 비공개 채널에서도 나가거나 제거됩니다. 사용자가 팀에 다시 추가될 경우 팀 내 비공개 채널에도 다시 추가되어야 합니다.

## <a name="channel-owner-settings"></a>채널 소유자 설정

각 비공개 채널에는 구성원 추가 및 제거, 탭 추가, 그리고 전체 채널에 대한 @멘션 기능 등 채널 소유자가 관리할 수 있는 고유한 설정이 있습니다. 이러한 설정은 상위 팀 설정과는 독립됩니다. 비공개 채널을 만들면 상위 팀에서 설정이 상속되며, 이후에 해당 설정을 변경하면 상위 팀 설정과 독립적으로 지정됩니다.

비공개 채널 소유자는 **채널 관리** 를 클릭한 후 **구성원** 및 **설정** 탭을 사용하여 구성원을 추가하거나 제거하고 설정을 편집할 수 있습니다.

![비공개 채널 설정의 스크린샷.](media/private-channels-in-teams-channel-settings.png)

## <a name="private-channel-owner-and-member-actions"></a>비공개 채널 소유자 및 구성원 작업

다음 표에는 소유자, 구성원 및 게스트가 비공개 채널에서 수행할 수 있는 작업이 나와 있습니다.

|작업  |팀 소유자|팀 구성원|팀 게스트|비공개 채널 소유자|비공개 채널 구성원|비공개 채널 게스트|
|---------|---------|---------|---------|---------|---------|---------|
|비공개 채널 만들기|관리자가 제어|관리자 및 팀 소유자가 제어|아니요|해당 없음|해당 없음|해당 없음|
|비공개 채널 삭제|예|아니요|아니요|예|아니요|아니요|
|비공개 채널 나가기|해당 없음|해당 없음|해당 없음|예(마지막 소유자가 아닌 경우)|예|예|
|비공개 채널 편집|아니요|해당 없음|해당 없음|예|아니요|아니요|
|삭제된 비공개 채널 복원|예|아니요|아니요|예|아니요|아니요|
|구성원 추가|아니요|해당 없음|해당 없음|예|아니요|아니요|
|설정 편집|아니요|해당 없음|해당 없음|예|아니요|아니요|
|탭 및 앱 관리|아니요|해당 없음|해당 없음|예, 팀용 앱을 설치해야 합니다.|채널 소유자가 제어|아니요|

## <a name="private-channel-sharepoint-sites"></a>비공개 채널 SharePoint 사이트

각 비공개 채널에는 고유한 SharePoint 사이트가 있습니다. 별도의 사이트는 비공개 채널 파일에 대한 액세스 권한이 비공개 채널의 구성원에게만 제한되도록 하기 위함입니다. 이러한 사이트는 기본적으로 문서 라이브러리를 통해 만들어지며, [사이트 관리 인터페이스](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04)를 통해 전체 기능이 적용된 사이트로 손쉽게 업그레이드할 수 있습니다. 각 사이트는 상위 팀의 사이트와 동일한 지역에서 만들어집니다. 이러한 간단한 사이트에는 사용자 지정 템플릿 ID인 "TEAMCHANNEL#0" 또는 "TEAMCHANNEL#1"이 있어 PowerShell 및 Graph API를 통해 더욱 손쉽게 관리할 수 있습니다. 

> [!NOTE]
> 채널의 소유자 또는 구성원 권한이 있는 사용자만 공유 채널 사이트의 콘텐츠에 액세스할 수 있습니다. 부모 팀의 사용자와 관리자도 해당 콘텐츠에 액세스할 수 없습니다(채널 구성원인 경우 제외).

비공개 채널 사이트는 데이터 분류를 동기화하고 게스트 액세스 권한을 상위 팀의 사이트에서 상속합니다. 사이트 소유자와 구성원 그룹의 구성원 자격은 Teams 내 비공개 채널의 구성원 자격과 동기화되어 유지됩니다. 비공개 채널 사이트에 대한 사이트 사용 권한은 SharePoint를 통해 독립적으로 관리할 수 없습니다. 

Teams는 비공개 채널 사이트의 수명 주기를 관리합니다. 사이트가 Teams 외부에서 삭제될 경우 비공개 채널이 여전히 활성화되어 있는 상태이면 백그라운드 작업에서 4시간 내에 사이트를 복원합니다.

비공개 채널 또는 비공개 채널을 포함하는 팀이 복원되면 사이트도 함께 복원됩니다. 비공개 채널 사이트가 복원된 상태에서 비공개 채널에 대해 30일의 일시 삭제 기간이 지난 경우 해당 사이트는 독립 실행형 사이트로 작동합니다.

> [!NOTE]
> Microsoft Teams에서 새 팀, 비공개 채널 또는 공유 채널을 만들면 SharePoint의 팀 사이트가 자동으로 만들어집니다. 이 팀 사이트에 대한 사이트 설명 또는 분류를 편집하려면 [Microsoft Teams에서 해당 채널의 설정](https://support.microsoft.com/office/change-a-team-s-data-security-classification-in-teams-bf39798f-90d2-44fb-a750-55fa05a56f1d)으로 이동하세요.
>
> [Microsoft Teams에 연결된 팀 사이트](/SharePoint/teams-connected-sites) 관리에 대해 자세히 알아보세요.

## <a name="compliance-copies-of-private-channel-messages"></a>비공개 채널 메시지의 준수 복사본

비공개 채널로 전송된 메시지의 준수 복사본은 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함으로 전달됩니다. 준수 복사본의 제목에는 전송된 비공개 채널에서 보냈다는 걸 나타내는 서식이 지정됩니다.

비공개 채널 메시지의 eDiscovery 검색을 수행하는 방법에 대한 자세한 내용은 [비공개 채널의 eDiscovery](ediscovery-investigation.md#ediscovery-of-private-and-shared-channels)를 참조하세요.

## <a name="considerations-around-file-access-in-private-channels"></a>비공개 채널의 파일 액세스에 대한 고려 사항

비공개 채널에서 새 OneNote 전자 필기장을 만든 경우 추가 사용자도 해당 전자 필기장에 액세스할 수 있습니다. 이는 비공개 채널 SharePoint 사이트에 있는 다른 항목에 대한 액세스를 사용자와 공유하는 것과 같은 방식입니다.

사용자에게 SharePoint를 통해 비공개 채널의 전자 필기장에 대한 액세스를 부여할 경우 팀 또는 비공개 채널에서 해당 사용자를 제거해도 전자 필기장에 대한 사용자의 액세스 권한은 제거되지 않습니다.

기존 전자 필기장이 비공개 채널의 탭으로 추가될 경우 비공개 채널에 대한 액세스는 변경되지 않습니다. 전자 필기장은 기존 사용 권한을 보존합니다.

## <a name="private-channel-limitations"></a>비공개 채널 제한 사항

현재 비공개 채널은 커넥터와 탭(Stream, Planner 및 Forms 제외)만 지원합니다. Microsoft에서는 메시징 확장 기능과 Bot을 포함하여 모든 앱을 개인 채널에 대해 지원하기 위한 작업을 진행하고 있습니다.

각 팀에는 최대 30개의 비공개 채널이 있을 수 있으며 각 비공개 채널은 최대 250명의 구성원을 보유할 수 있습니다. 팀당 표준 채널이 200개로 제한된 데에 더해 비공개 채널도 30개로 제한되는 것입니다. 

기존 팀에서 팀을 만들면 기존 팀의 비공개 채널은 복사되지 않습니다.

비공개 채널은 다른 채널 유형으로 변환할 수 없습니다.

비공개 채널의 알림은 누락된 활동 전자 메일에 포함되지 않습니다.

채널 모임을 예약할 수 없습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft Teams의 공유 채널](/MicrosoftTeams/shared-channels)

[Teams의 팀 및 채널 개요](teams-channels-overview.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Microsoft Graph API를 사용하여 Teams에서 작업](/graph/api/resources/teams-api-overview)

[채널 리소스 종류](/graph/api/resources/channel)
