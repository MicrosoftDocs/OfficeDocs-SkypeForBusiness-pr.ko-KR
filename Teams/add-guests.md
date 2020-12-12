---
title: 팀에 게스트 추가
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 관리자는 Microsoft Teams 데스크톱 및 웹 클라이언트 및 Azure Active Directory B2B 공동 작업 포털에서 조직에 새 게스트를 추가하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662443"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="a2208-103">팀에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="a2208-103">Add a guest to a team</span></span>

<span data-ttu-id="a2208-104">비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 Teams에서 게스트로 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="a2208-105">관리자는 몇 가지 방법으로 조직에 새 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="a2208-106">전역 관리자 또는 Teams 관리자와 팀 소유자가 Teams 클라이언트나 Teams 관리 센터에서 팀에 게스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="a2208-107">자세한 내용을 보려면 [팀에 게스트 추가](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)를 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="a2208-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="a2208-108">아직 게스트 액세스를 설정하지 않은 경우 [팀 내 게스트와의 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="a2208-109">Azure AD(Azure Active Directory) B2B 공동 작업을 통해 조직에 게스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="a2208-110">자세한 내용은 빠른 시작: Azure Portal에서 디렉터리에 게스트 [추가를 확인합니다.](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)</span><span class="sxs-lookup"><span data-stu-id="a2208-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="a2208-111">관리자는 게스트 초대자 역할을 할당하여 조직의 다른 사용자에게 게스트를 추가할 수 있는 권한을 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="a2208-112">자세한 내용은 [B2B 외부 공동 작업 사용 및 게스트를 초대할 수 있는 사용자 관리하기](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2208-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="a2208-113">Azure AD B2B 공동 작업을 통해 조직에서는 B2B 사용자에 대한 조건부 액세스 및 MFA(Multi-Factor Authentication) 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="a2208-114">조직의 전일제 직원과 구성원에 대해 이러한 정책을 사용하는 것과 같은 방법으로 이러한 정책을 테넌트, 앱 또는 개별 사용자 수준에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="a2208-115">이러한 정책은 리소스 조직에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="a2208-116">자세한 내용은 [B2B 공동 작업 사용자에 대한 조건부 액세스](https://go.microsoft.com/fwlink/?linkid=857454)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2208-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="a2208-117">개별 게스트는 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="a2208-118">Azure AD B2B, Microsoft 365 그룹 또는 SharePoint를 통해 이미 추가한 게스트를 사용할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="a2208-119">Microsoft 365 관리자 또는 팀 소유자는 해당 게스트를 해당 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="a2208-120">팀과 연결된 Microsoft 365 그룹에 게스트를 직접 추가하면 게스트가 팀에 액세스할 수 있지만 Microsoft 365 그룹은 게스트에게 초대 전자 메일을 생성하지 않습니다. 따라서 팀의 누군가가 게스트에게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="a2208-121">게스트는 [Microsoft 365 또는 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 서비스 제한에 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-121">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="a2208-122">Azure AD 또는 Microsoft 365 보안 센터에서 게스트 추가를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="a2208-123">Microsoft Teams에서 게스트 추가가 감사되고 Azure AD 그룹 관리 작업 “그룹에 구성원이 추가됨”으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2208-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="a2208-124">자세한 내용은 [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) 공동 작업 사용자 감사 및 보고를 참조하고 준수 센터에서 감사 [로그를 검색합니다.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="a2208-124">For more details, see [Auditing and reporting a B2B collaboration user](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a2208-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a2208-125">Related topics</span></span>

[<span data-ttu-id="a2208-126">Microsoft Teams에서 게스트 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a2208-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="a2208-127">Microsoft Teams에서 게스트 액세스 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="a2208-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)
