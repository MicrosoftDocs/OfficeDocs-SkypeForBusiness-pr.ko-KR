---
title: 팀에 게스트 추가
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: 관리자는 Microsoft Teams 데스크톱 및 웹 클라이언트와 Azure Active Directory B2B 공동 작업 포털의 조직에 새 게스트 사용자를 추가하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea1670078a61366e1ab0207368a58f9ad2b900ab
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44609836"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="e511d-103">팀에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="e511d-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="e511d-104">비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 Teams에서 게스트로 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="e511d-105">관리자는 다음과 같은 두 가지 방법으로 조직에 새 게스트 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="e511d-106">전역 관리자 또는 Teams 관리자와 팀 소유자가 Teams 클라이언트나 Teams 관리 센터에서 팀에 게스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="e511d-107">자세한 내용을 보려면 [팀에 게스트 추가](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)를 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="e511d-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="e511d-108">아직 게스트 액세스를 설정하지 않은 경우 [게스트 액세스 검사 목록](guest-access-checklist.md)의 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="e511d-109">**관리자 및 게스트 초대자 역할의 사용자가 초대할 수 있음**을 사용하도록 설정한 경우에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="e511d-110">게스트 초대자 역할은 Teams에서 지원되지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="e511d-111">Azure AD(Azure Active Directory) B2B 공동 작업을 통해 조직에 게스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="e511d-112">Azure AD B2B 공동 작업에서는 전역 관리자가 쉼표로 구분된 값(CSV) 파일(라인 2,000개 이하)을 B2B 공동 작업 포털에 업로드하여 외부 사용자 집단을 초대하고 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="e511d-113">자세한 내용은 [Azure Active Directory B2B 공동 작업](https://go.microsoft.com/fwlink/p/?linkid=826383)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e511d-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="e511d-114">Azure AD B2B 공동 작업을 통해 조직에서는 B2B 사용자에 대한 조건부 액세스 및 MFA(Multi-Factor Authentication) 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="e511d-115">조직의 전일제 직원과 구성원에 대해 이러한 정책을 사용하는 것과 같은 방법으로 이러한 정책을 테넌트, 앱 또는 개별 사용자 수준에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="e511d-116">이러한 정책은 리소스 조직에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="e511d-117">자세한 내용은 [B2B 공동 작업 사용자에 대한 조건부 액세스](https://go.microsoft.com/fwlink/?linkid=857454)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e511d-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="e511d-118">개별 게스트 사용자는 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="e511d-119">Azure AD B2B, Microsoft 365 그룹 또는 SharePoint Online을 통해 이미 추가한 게스트 사용자는 준비가 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-119">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="e511d-120">Microsoft 365 또는 Office 365의 관리자 또는 팀 소유자는 해당 게스트를 각자의 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-120">The Microsoft 365 or Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="e511d-121">팀이 이미 Microsoft 365 그룹을 사용하는데 그룹에 게스트가 추가되는 경우, 해당 게스트는 팀에 대한 액세스 권한을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-121">If a team is already with a Microsoft 365 group and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="e511d-122">게스트가 Microsoft 365 그룹을 통해 게스트를 추가하는 경우에는 게스트에 대한 초대 전자 메일이 생성되지 않습니다. 그러므로 팀의 구성원이 게스트에게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-122">Adding a guest via the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="e511d-123">게스트는 [Microsoft 365 또는 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 서비스 제한에 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-123">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="e511d-124">Azure AD 또는 Microsoft 365 보안 센터에서 게스트 추가를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-124">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="e511d-125">Microsoft Teams에서 게스트 추가가 감사되고 Azure AD 그룹 관리 작업 “그룹에 구성원이 추가됨”으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e511d-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="e511d-126">자세한 내용은 [B2B 공동 작업 사용자 감사 및 보고](https://go.microsoft.com/fwlink/p/?linkid=858884)와 [Microsoft 365 보안 센터에서 감사 로그 검색](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e511d-126">For more details, see [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Microsoft 365 security center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="e511d-127">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e511d-127">More information</span></span>

[<span data-ttu-id="e511d-128">Microsoft Teams에서 게스트 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="e511d-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="e511d-129">Microsoft Teams에서 게스트 액세스 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="e511d-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="e511d-130">PowerShell을 사용하여 팀에 대한 액세스 권한 제어</span><span class="sxs-lookup"><span data-stu-id="e511d-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
