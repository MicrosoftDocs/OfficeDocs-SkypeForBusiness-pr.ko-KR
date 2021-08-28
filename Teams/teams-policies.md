---
title: 팀 정책 관리 Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: 조직에서 팀 정책을 사용 및 관리하여 사용자가 팀 및 채널에서 할 수 있는 작업을 제어하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: de5558fbecddff0c4437cf3205aa676d664867f6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629980"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>팀 정책 관리 Microsoft Teams

관리자는 조직의 팀 정책을 사용하여 Microsoft Teams 및 채널에서 조직의 사용자가 할 수 있는 작업을 제어할 수 있습니다. 예를 들어 사용자가 개인 채널을 만들 수 있는지 여부를 설정할 수 있습니다.

관리 센터에서 Teams Teams 관리 Microsoft Teams  >   관리합니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.

전역 정책을 편집하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 전역 정책을 편집하거나 정책을 할당한 후 변경 내용이 적용될 수 있는 데 몇 시간이 걸릴 수 있습니다.

## <a name="create-a-custom-teams-policy"></a>사용자 지정 팀 정책 만들기

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 정책 Teams  >  **Teams 로 이동하세요.**
2. **추가** 를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다.

    ![팀 정책 설정 스크린샷](media/teams-policies.png)
4. 사용자가 개인 채널을  <a name="createchannels"></a> 만들 수 있도록 허용할지 여부에 따라 개인 채널 만들기를 켜거나 끄습니다.

5. **저장** 을 클릭합니다.

## <a name="edit-a-teams-policy"></a>팀 정책 편집

전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 정책 Teams  >  **Teams 로 이동하세요.**
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 원하는 설정을 켜거나 끄고 저장을 **클릭합니다.**

## <a name="assign-a-custom-teams-policy-to-users"></a>사용자에게 사용자 지정 팀 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>관련 주제

[연결된 Teams 채널 사이트 관리](/SharePoint/teams-connected-sites)

[Teams](private-channels.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
