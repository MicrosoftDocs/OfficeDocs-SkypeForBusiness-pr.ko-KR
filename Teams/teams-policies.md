---
title: Microsoft Teams에서 채널 정책 관리
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
- chat-teams-channels-revamp
description: 조직에서 팀 채널 정책을 사용하고 관리하여 사용자가 팀 및 채널에서 수행할 수 있는 작업을 제어하는 방법을 알아봅니다.
ms.openlocfilehash: 1223f191550675d5edd7b99a1cf9820fa14c9992
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198560"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Microsoft Teams에서 채널 정책 관리

관리자는 Microsoft Teams의 정책을 사용하여 조직의 사용자가 팀과 채널에서 수행할 수 있는 작업을 제어할 수 있습니다. 예를 들어 사용자가 비공개 또는 공유 채널을 만들 수 있는지 여부를 설정할 수 있습니다.

Microsoft Teams 관리 센터에서 **Teams Teams** >  정책으로 이동하여 팀 **정책을** 관리합니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.

전역 정책을 편집하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 전역 정책을 편집하거나 정책을 할당한 후에는 변경 내용이 적용되는 데 24시간이 걸릴 수 있습니다.

## <a name="channel-policies"></a>채널 정책

팀 채널에는 다음 정책을 사용할 수 있습니다.

|정책|설명|
|:-----|:----------|
|**비공개 채널 만들기**|**켜** 면 팀 소유자와 구성원이 비공개 채널을 만들 수 있습니다. (팀 소유자는 구성원이 각 팀에서 비공개 채널을 만들 수 있는지 제어할 수 있습니다.)|
|**공유 채널 만들기**|**켜** 기 시 팀 소유자는 공유 채널을 만들 수 있습니다. 조직에서 사용할 수 있는 Teams 앱은 공유 채널에서도 사용할 수 있습니다.|
|**공유 채널에 외부 사용자 초대**|**켜** 기일 때 공유 채널의 소유자와 구성원은 조직 간 트러스트가 구성된 조직의 외부 참가자를 초대할 수 있습니다. 조직의 Teams 정책은 이러한 채널에 적용됩니다.|
|**외부 공유 채널 조인**|**켜** 기일 때 사용자는 조직 간 트러스트가 구성된 다른 조직에서 만든 공유 채널에 참여할 수 있습니다. 다른 조직에 대한 Teams 정책은 이러한 채널에 적용됩니다.|

## <a name="create-a-custom-teams-policy"></a>사용자 지정 팀 정책 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams Teams** > **정책** 으로 이동합니다.
2. **추가** 를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다.

    ![팀 정책 설정의 스크린샷.](media/teams-policies.png)
4. 원하는 설정을 켜거나 끈 다음 **저장** 을 클릭합니다.

5. **저장** 을 클릭합니다.

## <a name="edit-a-teams-policy"></a>팀 정책 편집

전역 정책 또는 사용자가 만든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams Teams** > **정책** 으로 이동합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 설정을 켜거나 끈 다음 **저장** 을 클릭합니다.

## <a name="assign-a-custom-teams-policy-to-users"></a>사용자에게 사용자 지정 팀 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>관련 주제

[Teams 연결된 사이트 및 채널 사이트 관리](/SharePoint/teams-connected-sites)

[Teams의 비공개 채널](private-channels.md)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
