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
description: 관리자는 데스크톱 및 웹 클라이언트 및 B2B 공동 작업 포털에서 조직에 Microsoft Teams 방법을 Azure Active Directory 수 있습니다.
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109084"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="20872-103">팀에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="20872-103">Add a guest to a team</span></span>

<span data-ttu-id="20872-104">비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 Teams에서 게스트로 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="20872-105">관리자는 몇 가지 방법으로 조직에 새 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="20872-106">전역 관리자 또는 Teams 관리자와 팀 소유자가 Teams 클라이언트나 Teams 관리 센터에서 팀에 게스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20872-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="20872-107">자세한 내용을 보려면 [팀에 게스트 추가](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)를 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="20872-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="20872-108">아직 게스트 액세스를 설정하지 않은 경우 [팀 내 게스트와의 공동 작업](/microsoft-365/solutions/collaborate-as-team) 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="20872-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="20872-109">Azure AD(Azure Active Directory) B2B 공동 작업을 통해 조직에 게스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20872-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="20872-110">자세한 내용은 빠른 [시작: Azure Portal의 디렉터리에 게스트 추가를 참조하세요.](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)</span><span class="sxs-lookup"><span data-stu-id="20872-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="20872-111">관리자는 게스트 초대자 역할을 할당하여 조직의 다른 사용자에게 게스트를 추가할 수 있는 권한을 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="20872-112">자세한 내용은 [B2B 외부 공동 작업 사용 및 게스트를 초대할 수 있는 사용자 관리하기](/azure/active-directory/external-identities/delegate-invitations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20872-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="20872-113">Azure AD B2B 공동 작업을 통해 조직에서는 B2B 사용자에 대한 조건부 액세스 및 MFA(Multi-Factor Authentication) 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="20872-114">조직의 전일제 직원과 구성원에 대해 이러한 정책을 사용하는 것과 같은 방법으로 이러한 정책을 테넌트, 앱 또는 개별 사용자 수준에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="20872-115">이러한 정책은 리소스 조직에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="20872-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="20872-116">자세한 내용은 [B2B 공동 작업 사용자에 대한 조건부 액세스](/azure/active-directory/external-identities/conditional-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20872-116">For more information, see  [Conditional access for B2B collaboration users](/azure/active-directory/external-identities/conditional-access).</span></span> <span data-ttu-id="20872-117">개별 게스트를 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="20872-118">Azure AD B2B, Microsoft 365 그룹 또는 SharePoint 추가한 게스트는 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="20872-119">관리자 Microsoft 365 팀 소유자는 해당 게스트를 해당 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="20872-120">게스트를 팀과 Microsoft 365 그룹에 직접 추가하면 게스트가 팀에 액세스할 수 있지만 Microsoft 365 그룹에 초대 전자 메일을 생성하지 않습니다. 따라서 팀의 다른 사용자가 게스트에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="20872-121">게스트는 [Microsoft 365 또는 Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) 및 [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) 서비스 제한에 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-121">Guests are subject to  [Microsoft 365 or Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) and [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) service limits.</span></span>

<span data-ttu-id="20872-122">Azure AD 또는 Microsoft 365 보안 센터에서 게스트 추가를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20872-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="20872-123">Microsoft Teams에서 게스트 추가가 감사되고 Azure AD 그룹 관리 작업 “그룹에 구성원이 추가됨”으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="20872-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="20872-124">자세한 내용은 [B2B](/azure/active-directory/external-identities/auditing-and-reporting) 공동 작업 사용자 감사 및 보고를 참조하고 준수 센터에서 감사 [로그 검색을 참조합니다.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="20872-124">For more details, see [Auditing and reporting a B2B collaboration user](/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="20872-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="20872-125">Related topics</span></span>

[<span data-ttu-id="20872-126">Microsoft Teams에서 게스트 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="20872-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="20872-127">Microsoft Teams에서 게스트 액세스 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="20872-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)