---
title: Microsoft 팀에서 팀 만료 및 갱신
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 팀 만료 및 갱신에 대해 알아보고 microsoft 365 그룹 만료 정책을 사용 하 여 Microsoft 팀에서 사용 하지 않은 팀을 자동으로 정리 하는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 16da525051e09f4ed1a7acaf3e9906f59b8b30af
ms.sourcegitcommit: b23d3d583910aa21a62ea69b554ab614c1ae8079
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648589"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft 팀에서 팀 만료 및 갱신

팀 수가 많은 조직에는 실제로 사용 되지 않는 팀이 있는 경우가 많습니다. 제품 실험, 단기 팀 공동 작업 또는 조직 내에서 팀 소유자 등의 여러 가지 이유로 인해이 문제가 발생할 수 있습니다. 시간이 지남에 따라 이러한 팀은 테 넌 트 리소스에 부담을 주지 시킬 수 있습니다.  

사용 하지 않는 팀 수를 설정 하려면 관리자가 [Microsoft 365 그룹 만료 정책을](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 사용 하 여 사용 하지 않는 팀을 자동으로 정리 하면 됩니다. 팀은 그룹에 의해 지원 되므로 그룹 만료 정책도 팀에 자동으로 적용 됩니다.

팀에 만료 정책을 적용 하면 팀 소유자는 팀이 만료 되는 날짜 로부터 30 일, 15 일, 1 일 전에 갱신 알림을 받을 수 있습니다. 팀 소유자가 알림을 받으면 팀 설정에서 **지금 갱신** 을 클릭 하 여 팀을 갱신할 수 있습니다.

![팀 설정에서 팀 갱신을 위한 지금 갱신 단추 스크린샷](media/team-expiration.png "팀 설정에서 팀 갱신을 위한 지금 갱신 단추 스크린샷")

팀 소유자가 팀을 갱신 하지 않고 만료 정책이 끝날 때까지 팀에 추가 활동이 없는 경우 팀은 "일시 삭제 됨" 상태에 놓이게 되며,이는 다음 30 일 내에 복원 될 수 있음을 의미 합니다.

## <a name="team-auto-renewal"></a>팀 자동 갱신

팀 소유자가 팀을 갱신할 수 없는 경우도 있고, 갱신을 완료 했을 때 갱신 되지 않았거나 이전에 발생 한 것이 없기 때문일 수 있습니다. 이러한 시나리오에서는 팀에 적용 되는 만료 정책 때문에 활성 사용 중인 팀이 삭제 될 수 있습니다.  

실수로 삭제 되는 것을 방지 하기 위해 자동 갱신은 그룹 만료 정책에서 팀에 자동으로 설정 됩니다. 그룹 만료 정책이 설정 된 경우 만료 날짜가 되기 전에 모든 팀 구성원 으로부터 최소한 하나의 채널이 방문 하는 팀은 팀 소유자의 수동 개입 없이 자동으로 갱신 됩니다.

## <a name="known-issues"></a>알려진 문제

**팀 및 기본 그룹의 만료 날짜가 일치 하지 않음**

팀을 갱신 하기 전에 먼저 팀을 백업한 그룹이 갱신 됩니다. 갱신의 일부로 이후 날짜에 대 한 새 만료 날짜가 그룹에 설정 됩니다. 팀에서이 새 날짜가 즉시 표시 되지 않을 수 있습니다. 동기화 하는 데 최대 24 시간이 걸릴 수 있습니다. 팀과 기본 그룹의 만료 날짜가 서로 일치 하지 않는 경우에는 24 시간 후에 추가 지원을 검색 합니다.
