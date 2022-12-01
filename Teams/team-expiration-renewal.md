---
title: Microsoft Teams에서 팀 만료 및 갱신
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
description: 팀 만료 및 갱신 및 Microsoft 365 그룹 만료 정책을 사용하여 Microsoft Teams에서 사용되지 않는 팀을 자동으로 정리하는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4f56c8cbb2d25b05d6c87fa2862e56244d6b9c8
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198800"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams에서 팀 만료 및 갱신

팀이 많은 조직에는 실제로 사용되지 않는 팀이 있는 경우가 많습니다. 이는 제품 실험, 단기 팀 공동 작업 또는 조직을 떠나는 팀 소유자를 비롯한 여러 가지 이유로 인해 발생할 수 있습니다. 시간이 지남에 따라 이러한 팀은 테넌트 리소스를 누적하고 부담을 만들 수 있습니다.  

사용하지 않는 팀 수를 억제하려면 관리자로서 [Microsoft 365 그룹 만료 정책을](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 사용하여 사용하지 않는 팀을 자동으로 정리할 수 있습니다. 팀은 그룹으로 지원되므로 그룹 만료 정책도 팀에 자동으로 적용됩니다.

팀에 만료 정책을 적용하면 팀 소유자는 팀 만료 날짜 30일, 15일 및 1일 전에 팀 갱신에 대한 알림을 받습니다. 팀 소유자가 알림을 받으면 팀 설정에서 **지금 갱신** 을 클릭하여 팀을 갱신할 수 있습니다.

![팀 설정에서 팀을 갱신하는 지금 갱신 단추의 스크린샷](media/team-expiration.png "팀 설정에서 팀을 갱신하는 지금 갱신 단추의 스크린샷")

팀 소유자가 팀을 갱신하지 않고 만료 정책이 끝날 때까지 팀에 대한 추가 활동이 없는 경우 팀은 "일시 삭제됨" 상태가 되어 향후 30일 이내에 복원할 수 있습니다.

## <a name="team-auto-renewal"></a>팀 자동 갱신

팀 소유자가 갱신을 잊어버렸거나 갱신 기한이 지났을 때 자리를 비워 팀을 갱신할 수 없는 경우가 있을 수 있습니다. 이러한 시나리오에서 현재 사용 중인 팀은 팀에 적용되는 만료 정책으로 인해 삭제할 수 있습니다.  

실수로 인한 삭제를 방지하기 위해 그룹 만료 정책의 팀에 대해 자동 갱신이 자동으로 활성화됩니다. 그룹 만료 정책이 설정되면 만료 날짜 전에 팀 구성원이 채널을 하나 이상 방문한 팀은 팀 소유자의 수동 개입 없이 자동으로 갱신됩니다.

## <a name="known-issues"></a>알려진 문제

**팀과 기본 그룹의 만료 날짜가 일치하지 않음**

팀이 갱신되기 전에 팀을 백업하는 그룹이 먼저 갱신됩니다. 갱신의 일부로 새 만료 날짜는 향후 날짜에 대해 그룹에 설정됩니다. 이 새 날짜는 Teams에서 즉시 표시되지 않을 수 있습니다. 동기화하는 데 최대 24시간이 걸릴 수 있습니다. 팀과 해당 기본 그룹의 만료 날짜가 불일치하는 경우 추가 지원을 요청하기 전에 24시간을 기다립니다.