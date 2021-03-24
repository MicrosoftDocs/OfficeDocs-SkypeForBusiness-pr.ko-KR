---
title: Microsoft 365 그룹 및 Microsoft Teams
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
description: Microsoft 365 그룹 및 그룹 멤버 자격이 Microsoft Teams와 함께 작동하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105244"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="f5843-103">Microsoft 365 그룹 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5843-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="f5843-104">Microsoft 365 그룹은 Microsoft 365의 애플리케이션 간 멤버 자격 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="f5843-105">기본 수준에서 Microsoft 365 그룹은 Azure Active Directory의 개체로, 구성원 목록과 SharePoint 팀 사이트, 공유 Exchange 사서함, Planner 및 Power BI 작업 영역 등 관련 워크로드와의 연관이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="f5843-106">Active Directory의 다른 그룹 기반 보안 개체와 같은 사용자 그룹을 그룹에 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![Microsoft 365 그룹 및 관련 서비스를 보여주는 다이어그램](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="f5843-108">기본적으로 Microsoft 365의 사용자는 그룹을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="f5843-109">Microsoft 365 그룹에 대한 자세한 내용은 [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 그룹 및 IT 설계자용 Microsoft [365](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 그룹 포스터를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5843-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="f5843-110">Microsoft 365 그룹이 Teams와 함께 작동하는 방법</span><span class="sxs-lookup"><span data-stu-id="f5843-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="f5843-111">팀을 만들 때 팀 멤버 자격을 관리하기 위해 Microsoft 365 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="f5843-112">SharePoint 사이트, Power BI 작업 영역 등 그룹의 관련 서비스가 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="f5843-113">팀을 만드는 사람은 해당 그룹의 소유자인 경우 기존 Microsoft 365 그룹을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="f5843-114">팀의 각 채널에는 문서 라이브러리에 별도의 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="f5843-115">문서 라이브러리에서 직접 폴더를 만들면 팀에서 채널이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="f5843-116">Outlook 또는 SharePoint에서 Microsoft 365 그룹을 만들 때 그룹 사서함이 Outlook에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="f5843-117">Teams에서 팀을 만들 때 그룹 사서함은 기본적으로 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="f5843-118">**HiddenFromExchangeClientsEnabled** 매개 변수와 함께 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet을 사용하여 사서함을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-118">You can use the [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="f5843-119">그룹 멤버 자격</span><span class="sxs-lookup"><span data-stu-id="f5843-119">Group membership</span></span>

<span data-ttu-id="f5843-120">팀 구성원을 제거하면 Microsoft 365 그룹도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="f5843-121">그룹에서 제거하면 Teams 클라이언트에서 팀 및 채널이 즉시 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="f5843-122">Microsoft 365 관리 센터를 사용하여 그룹에서 사람을 제거하면 SharePoint Online 문서 라이브러리, 그룹 또는 공유 OneNote와 같은 다른 공동 작업 Yammer 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="f5843-123">그러나 약 2시간 동안 팀의 채팅 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="f5843-124">팀 구성원을 관리하는 모범 사례로 Teams 클라이언트에서 추가 및 제거하여 다른 그룹 연결된 워크로드에 대한 사용 권한이 빠르게 업데이트되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="f5843-125">Teams 클라이언트 외부에서 팀 구성원을 추가하거나 제거하는 경우(Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell을 사용하여) 변경 내용이 Teams에 반영되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="f5843-126">그룹 및 팀 삭제</span><span class="sxs-lookup"><span data-stu-id="f5843-126">Deleting groups and teams</span></span>

<span data-ttu-id="f5843-127">Microsoft 365 그룹을 삭제하면 영구 Outlook/OWA 대화 및 Teams 모임 초대에 대한 사서함 별칭이 제거되고 SharePoint 사이트를 삭제로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="f5843-128">팀을 제거하고 Outlook에 영향을 미치기까지 약 20분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="f5843-129">Teams 클라이언트에서 팀을 삭제하면 팀의 구성원인 모든 사용자 보기에서 즉시 팀이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="f5843-130">Teams 기능을 사용하도록 설정한 Microsoft 365 그룹의 구성원을 제거하는 경우 팀이 제거된 영향을 받는 사용자에 대한 Teams 클라이언트의 보기에서 팀이 제거되기 약 2시간이 지연될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5843-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="f5843-131">수명 주기 옵션의 그룹 및 팀 종료에 대한 자세한 내용은 Microsoft Teams에서 [그룹,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 팀 및 Yammer 수명 주기 종료 옵션 및 보관 또는 삭제를 [참조하세요.](./archive-or-delete-a-team.md)</span><span class="sxs-lookup"><span data-stu-id="f5843-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](./archive-or-delete-a-team.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f5843-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f5843-132">Related topics</span></span>

[<span data-ttu-id="f5843-133">Microsoft Teams의 기초(비디오)</span><span class="sxs-lookup"><span data-stu-id="f5843-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="f5843-134">삭제된 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="f5843-134">Restore a deleted Group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)