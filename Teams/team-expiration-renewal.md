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
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="1c6a4-103">Microsoft Teams의 팀 만료 및 갱신</span><span class="sxs-lookup"><span data-stu-id="1c6a4-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="1c6a4-104">팀 수가 많은 조직에는 실제로 사용되지 않는 팀이 있는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="1c6a4-105">이는 제품 실험, 단기 팀 공동 작업 또는 조직에서 나가는 팀 소유자를 비롯한 여러 가지 이유로 인해 발생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="1c6a4-106">시간이 지날 때 이러한 팀은 테넌트 리소스에 부담을 누적하고 부담을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="1c6a4-107">관리자가 사용하지 않는 팀의 수를 조정하려면 [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 그룹 만료 정책을 사용하여 사용하지 않는 팀을 자동으로 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="1c6a4-108">팀이 그룹에서 지원하기 때문에 그룹 만료 정책도 자동으로 팀에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="1c6a4-109">팀에 만료 정책을 적용하면 팀 소유자는 팀 만료 날짜 30일, 15일 및 1일 전에 팀 갱신 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="1c6a4-110">팀 소유자가 알림을 받으면 팀  설정에서 지금 갱신을 클릭하여 팀을 갱신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="1c6a4-111">![팀 설정에서 팀을 갱신하는 지금 갱신 단추 스크린샷](media/team-expiration.png "팀 설정에서 팀을 갱신하는 지금 갱신 단추 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="1c6a4-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="1c6a4-112">팀 소유자가 팀을 갱신하지 않는 경우 만료 정책이 끝날 때까지 팀에 더 이상 활동이 없는 경우 팀은 "소프트 삭제" 상태가 됩니다. 즉, 다음 30일 이내에 복원될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="1c6a4-113">팀 자동 갱신</span><span class="sxs-lookup"><span data-stu-id="1c6a4-113">Team auto-renewal</span></span>

<span data-ttu-id="1c6a4-114">갱신을 잊어버렸다가 갱신이 만료될 때 팀 소유자가 팀을 갱신할 수 없는 경우도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="1c6a4-115">이러한 시나리오에서는 활성 사용 팀이 팀에 적용되는 만료 정책으로 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="1c6a4-116">실수로 삭제되지 않도록 그룹 만료 정책에서 팀에 대해 자동 갱신이 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="1c6a4-117">그룹 만료 정책을 설정하면 만료 날짜 전에 채널이 하나 이상 있는 모든 팀이 팀 소유자의 수동 개입 없이 자동으로 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="1c6a4-118">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="1c6a4-118">Known issues</span></span>

<span data-ttu-id="1c6a4-119">**팀 및 기조 그룹의 만료 날짜가 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="1c6a4-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="1c6a4-120">팀이 갱신되기 전에 팀을 백업하는 그룹이 먼저 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="1c6a4-121">갱신의 일부로 새 만료 날짜가 그룹에 향후 날짜로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="1c6a4-122">이 새 날짜는 Teams에 즉시 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="1c6a4-123">동기화하는 데 최대 24시간이 걸릴 수 있습니다. 팀과 해당 그룹이 만료 날짜 사이에 불일치가 표시될 경우 추가 지원을 구하기 전에 24시간 동안 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a4-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
