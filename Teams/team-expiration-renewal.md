---
title: Microsoft Teams의 팀 만료 및 갱신
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
description: 팀 만료 및 갱신 및 Microsoft 365 그룹 만료 정책을 사용하여 Microsoft Teams에서 사용하지 않는 팀을 자동으로 정리하는 방법에 대해 자세히 배워야 합니다.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809408"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams의 팀 만료 및 갱신

팀 수가 많은 조직에는 실제로 사용되지 않는 팀이 있는 경우가 종종 있습니다. 이는 제품 실험, 단기 팀 공동 작업 또는 조직에서 나가는 팀 소유자를 비롯한 여러 가지 이유로 인해 발생될 수 있습니다. 시간이 지날 때 이러한 팀은 테넌트 리소스에 부담을 누적하고 부담을 줄 수 있습니다.  

관리자가 사용하지 않는 팀의 수를 조정하려면 [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 그룹 만료 정책을 사용하여 사용하지 않는 팀을 자동으로 정리할 수 있습니다. 팀이 그룹에서 지원하기 때문에 그룹 만료 정책도 자동으로 팀에 적용됩니다.

팀에 만료 정책을 적용하면 팀 소유자는 팀 만료 날짜 30일, 15일 및 1일 전에 팀 갱신 알림을 받게 됩니다. 팀 소유자가 알림을 받으면 팀  설정에서 지금 갱신을 클릭하여 팀을 갱신할 수 있습니다.

![팀 설정에서 팀을 갱신하는 지금 갱신 단추 스크린샷](media/team-expiration.png "팀 설정에서 팀을 갱신하는 지금 갱신 단추 스크린샷")

팀 소유자가 팀을 갱신하지 않는 경우 만료 정책이 끝날 때까지 팀에 더 이상 활동이 없는 경우 팀은 "소프트 삭제" 상태가 됩니다. 즉, 다음 30일 이내에 복원될 수 있습니다.

## <a name="team-auto-renewal"></a>팀 자동 갱신

갱신을 잊어버렸다가 갱신이 만료될 때 팀 소유자가 팀을 갱신할 수 없는 경우도 있을 수 있습니다. 이러한 시나리오에서는 활성 사용 팀이 팀에 적용되는 만료 정책으로 삭제될 수 있습니다.  

실수로 삭제되지 않도록 그룹 만료 정책에서 팀에 대해 자동 갱신이 자동으로 설정됩니다. 그룹 만료 정책을 설정하면 만료 날짜 전에 채널이 하나 이상 있는 모든 팀이 팀 소유자의 수동 개입 없이 자동으로 갱신됩니다.

## <a name="known-issues"></a>알려진 문제

**팀 및 기조 그룹의 만료 날짜가 일치하지 않습니다.**

팀이 갱신되기 전에 팀을 백업하는 그룹이 먼저 갱신됩니다. 갱신의 일부로 새 만료 날짜가 그룹에 향후 날짜로 설정됩니다. 이 새 날짜는 Teams에 즉시 표시되지 않을 수 있습니다. 동기화하는 데 최대 24시간이 걸릴 수 있습니다. 팀과 해당 그룹이 만료 날짜 사이에 불일치가 표시될 경우 추가 지원을 구하기 전에 24시간 동안 기다릴 수 있습니다.
