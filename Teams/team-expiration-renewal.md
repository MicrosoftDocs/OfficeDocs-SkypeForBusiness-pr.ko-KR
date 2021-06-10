---
title: 팀 만료 및 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 팀 만료 및 갱신 및 그룹 만료 정책을 사용하여 Microsoft 365 팀에서 사용하지 않는 팀을 자동으로 정리하는 방법에 대해 Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116956"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>팀 만료 및 Microsoft Teams

팀 수가 많은 조직에는 실제로 사용되지 않는 팀이 있는 경우가 있습니다. 이는 제품 실험, 단기 팀 공동 작업 또는 팀 소유자가 조직을 떠날 때와 같은 몇 가지 이유로 인해 일어날 수 있습니다. 시간이 지날 때 이러한 팀은 테넌트 리소스에 대한 부담을 누적하고 만들 수 있습니다.  

사용되지 않는 팀의 수를 줄이기 위해 관리자로 그룹 만료 정책을 사용하여 Microsoft 365 팀을 자동으로 정리할 수 있습니다. [](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 팀이 그룹에서 지원하기 때문에 그룹 만료 정책도 팀에 자동으로 적용됩니다.

팀에 만료 정책을 적용하면 팀 소유자는 팀 만료 날짜 30일, 15일 및 1일 전에 팀 갱신 알림을 받게 됩니다. 팀 소유자가 알림을 받으면 이제  팀 설정에서 갱신을 클릭하여 팀을 갱신할 수 있습니다.

![팀 설정에서 팀을 갱신하는 지금 갱신 단추 스크린샷](media/team-expiration.png "팀 설정에서 팀을 갱신하는 지금 갱신 단추 스크린샷")

팀 소유자가 팀을 갱신하지 않는 경우 만료 정책이 종료될 때까지 팀에 대한 추가 활동이 없는 경우 팀은 "소프트 삭제" 상태로 설정되어 30일 이내에 복원할 수 있습니다.

## <a name="team-auto-renewal"></a>팀 자동 갱신

팀 소유자가 갱신을 잊어버렸다거나 갱신이 기한이 지났기 때문에 팀 소유자가 팀을 갱신할 수 없는 경우도 있습니다. 이러한 시나리오에서는 팀에 적용되는 만료 정책으로 인하여 활성 사용 팀이 삭제될 수 있습니다.  

실수로 삭제되지 않도록 그룹 만료 정책의 팀에 대해 자동 갱신이 자동으로 활성화됩니다. 그룹 만료 정책을 설정하면 만료 날짜 전에 팀 구성원이 하나 이상의 채널을 방문한 모든 팀이 팀 소유자의 수동 개입 없이 자동으로 갱신됩니다.

## <a name="known-issues"></a>알려진 문제

**팀 및 기조 그룹의 만료 날짜가 일치하지 않습니다.**

팀이 갱신되기 전에 팀을 백업하는 그룹이 먼저 갱신됩니다. 갱신의 일환으로 새 만료 날짜가 향후 날짜에 대해 그룹에 설정됩니다. 이 새 날짜는 해당 날짜에 즉시 표시되지 Teams. 동기화하는 데 최대 24시간이 걸릴 수 있습니다. 팀의 만료 날짜와 해당 기조 그룹 간에 불일치가 표시될 경우 추가 지원을 구하기 전에 24시간 기다릴 수 있습니다.