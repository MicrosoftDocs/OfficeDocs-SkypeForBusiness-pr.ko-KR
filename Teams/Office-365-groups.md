---
title: Microsoft 365 그룹 및 Microsoft 팀
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Microsoft 365 그룹 및 그룹 구성원이 Microsoft 팀과 어떻게 작동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456082"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="ca3fd-103">Microsoft 365 그룹 및 Microsoft 팀</span><span class="sxs-lookup"><span data-stu-id="ca3fd-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="ca3fd-104">Microsoft 365 그룹은 Microsoft 365의 응용 프로그램 간 구성원 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="ca3fd-105">Microsoft 365 그룹은 기본 수준에서 SharePoint 팀 사이트, 공유 Exchange 사서함, Planner 및 Power BI 작업 영역을 비롯 한 관련 작업에 대 한 결합 및 구성원 목록이 있는 Azure Active Directory의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="ca3fd-106">Active Directory의 다른 그룹 기반 보안 개체와 마찬가지로 그룹에 사용자를 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![Microsoft 365 그룹 및 관련 서비스를 보여 주는 다이어그램](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="ca3fd-108">기본적으로 Microsoft 365의 사용자는 그룹을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="ca3fd-109">Microsoft 365 그룹에 대 한 자세한 내용은 microsoft [365 그룹](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 및 [IT 설계자 포스터 용 Microsoft 365의 그룹](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 에 대 한 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="ca3fd-110">Microsoft 365 그룹이 팀과 공동 작업 하는 방법</span><span class="sxs-lookup"><span data-stu-id="ca3fd-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="ca3fd-111">팀을 만들 때 팀 구성원을 관리 하기 위해 Microsoft 365 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="ca3fd-112">SharePoint 사이트, Power BI 작업 영역 등 그룹의 관련 서비스가 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="ca3fd-113">팀을 만든 사용자는 해당 그룹의 소유자 인 경우 기존 Microsoft 365 그룹을 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="ca3fd-114">팀의 각 채널에는 문서 라이브러리에 별도의 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="ca3fd-115">문서 라이브러리에서 직접 폴더를 만들면 팀에서 채널을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="ca3fd-116">Outlook 또는 SharePoint에서 Microsoft 365 그룹을 만들면 Outlook에서 그룹 사서함이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="ca3fd-117">팀에서 팀을 만들 때 그룹 사서함은 기본적으로 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="ca3fd-118">**HiddenFromExchangeClientsEnabled** 매개 변수와 함께 [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet을 사용 하 여 사서함을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-118">You can use the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="ca3fd-119">그룹 구성원</span><span class="sxs-lookup"><span data-stu-id="ca3fd-119">Group membership</span></span>

<span data-ttu-id="ca3fd-120">팀 구성원을 제거 하면 Microsoft 365 그룹 에서도 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="ca3fd-121">그룹에서 제거 하면 팀 클라이언트에서 팀과 채널이 즉시 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="ca3fd-122">Microsoft 365 관리 센터를 사용 하 여 그룹에서 사용자를 제거 하는 경우에는 더 이상 SharePoint Online 문서 라이브러리, Yammer 그룹 또는 공유 OneNote와 같은 다른 공동 작업에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="ca3fd-123">그러나 약 2 시간 동안 팀의 채팅 기능에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="ca3fd-124">팀 구성원을 관리 하는 가장 좋은 방법으로, 다른 그룹 연결 작업에 대 한 사용 권한 업데이트가 빠르게 발생 하도록 팀 클라이언트에서 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="ca3fd-125">팀 클라이언트 (예를 들어 Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell을 사용 하 여)를 추가 하거나 제거 하는 경우 변경 내용이 팀에 반영 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="ca3fd-126">그룹 및 팀 삭제</span><span class="sxs-lookup"><span data-stu-id="ca3fd-126">Deleting groups and teams</span></span>

<span data-ttu-id="ca3fd-127">Microsoft 365 그룹을 삭제 하면 영구 Outlook/OWA 대화 및 팀 모임 초대에 대 한 사서함 별칭이 제거 되 고 SharePoint 사이트를 삭제 하도록 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="ca3fd-128">팀을 제거 하는 시간과 Outlook에 미치는 영향 사이에 약 20 분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="ca3fd-129">팀 클라이언트에서 팀을 삭제 하면 해당 팀의 구성원 인 모든 사용자가 보기에서 즉시 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="ca3fd-130">팀 기능을 사용할 수 있는 Microsoft 365 그룹의 구성원을 제거 하는 경우 팀 클라이언트에서 해당 사용자가 제거 된 영향을 받는 사람을 보기에서 제거 하기 전에 약 2 시간이 지연 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="ca3fd-131">수명 주기 옵션의 그룹 및 팀 종료에 대 한 자세한 내용은  [그룹, 팀 및 Yammer에 대 한 주기 옵션 종료](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 와 [Microsoft 팀에서 팀 보관 또는 삭제](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3fd-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca3fd-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ca3fd-132">Related topics</span></span>

[<span data-ttu-id="ca3fd-133">Microsoft 팀의 기초 (비디오)</span><span class="sxs-lookup"><span data-stu-id="ca3fd-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="ca3fd-134">삭제 된 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="ca3fd-134">Restore a deleted Group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)