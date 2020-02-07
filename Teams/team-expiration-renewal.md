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
description: 팀 만료 및 갱신 및 Office 365 그룹 만료 정책을 사용 하 여 Microsoft 팀에서 사용 하지 않은 팀을 자동으로 정리 하는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bd9949a23d18eb03c83e50ecd418abbf54c0494
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837898"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="a4c1d-103">Microsoft 팀에서 팀 만료 및 갱신</span><span class="sxs-lookup"><span data-stu-id="a4c1d-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="a4c1d-104">팀 수가 많은 조직에는 실제로 사용 되지 않는 팀이 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="a4c1d-105">제품 실험, 단기 팀 공동 작업 또는 조직 내에서 팀 소유자 등의 여러 가지 이유로 인해이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="a4c1d-106">시간이 지남에 따라 이러한 팀은 테 넌 트 리소스에 부담을 주지 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="a4c1d-107">사용 하지 않는 팀 수를 설정 하려면 관리자가 [Office 365 그룹 만료 정책을](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) 사용 하 여 사용 하지 않는 팀을 자동으로 정리 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-107">To curb the number of unused teams, as an admin, you can use [Office 365 Group expiration policy](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="a4c1d-108">팀은 그룹에 의해 지원 되므로 그룹 만료 정책도 팀에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="a4c1d-109">팀에 만료 정책을 적용 하면 팀 소유자는 팀이 만료 되는 날짜 로부터 30 일, 15 일, 1 일 전에 갱신 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="a4c1d-110">팀 소유자가 알림을 받으면 팀 설정에서 **지금 갱신** 을 클릭 하 여 팀을 갱신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="a4c1d-111">![팀 설정에서 팀 갱신을 위한 지금 갱신 단추 스크린샷](media/team-expiration.png "팀 설정에서 팀 갱신을 위한 지금 갱신 단추 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="a4c1d-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="a4c1d-112">팀 소유자가 팀을 갱신 하지 않으면 팀이 "일시 삭제 됨" 상태로 설정 되며,이는 다음 30 일 내에 복원 될 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="a4c1d-113">팀 자동 갱신</span><span class="sxs-lookup"><span data-stu-id="a4c1d-113">Team auto-renewal</span></span>

<span data-ttu-id="a4c1d-114">팀 소유자가 팀을 갱신할 수 없는 경우도 있고, 갱신을 완료 했을 때 갱신 되지 않았거나 이전에 발생 한 것이 없기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="a4c1d-115">이러한 시나리오에서는 팀에 적용 되는 만료 정책 때문에 활성 사용 중인 팀이 삭제 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="a4c1d-116">실수로 삭제 되는 것을 방지 하기 위해 자동 갱신은 그룹 만료 정책에서 팀에 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="a4c1d-117">그룹 만료 정책이 설정 된 경우 만료 날짜가 되기 전에 모든 팀 구성원 으로부터 최소한 하나의 채널이 방문 하는 팀은 팀 소유자의 수동 개입 없이 자동으로 갱신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a4c1d-118">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="a4c1d-118">Known issues</span></span>

<span data-ttu-id="a4c1d-119">**팀 및 기본 그룹의 만료 날짜가 일치 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="a4c1d-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="a4c1d-120">팀을 갱신 하기 전에 먼저 팀을 백업한 그룹이 갱신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="a4c1d-121">갱신의 일부로 이후 날짜에 대 한 새 만료 날짜가 그룹에 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="a4c1d-122">팀에서이 새 날짜가 즉시 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="a4c1d-123">동기화 하는 데 최대 24 시간이 걸릴 수 있습니다. 팀과 기본 그룹의 만료 날짜가 서로 일치 하지 않는 경우에는 24 시간 후에 추가 지원을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c1d-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
