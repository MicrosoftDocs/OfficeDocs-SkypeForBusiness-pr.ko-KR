---
title: Microsoft Teams의 정보 장벽
description: 이 문서에서는 Microsoft Teams의 정보 장벽이 무엇일지, Teams에 어떤 영향을 줄 수 있는가를 설명합니다.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: vikramju
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2bae63b2a37b5c5739a988cfe69f23b7609e63b
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697823"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="693af-103">Microsoft Teams의 정보 장벽</span><span class="sxs-lookup"><span data-stu-id="693af-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="693af-104">IB(정보 장벽)는 관리자가 개인 또는 그룹이 서로 통신하지 못하도록 구성할 수 있는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-104">Information barriers (IBs) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="693af-105">예를 들어 한 부서에서 다른 부서와 공유하지 말아야 하는 정보를 처리하는 경우 IB가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-105">IBs are useful if, for example, one department is handling information that shouldn't be shared with other departments.</span></span> <span data-ttu-id="693af-106">또한 그룹이 격리되거나 그룹 외부의 모든 사용자와 통신하지 못하게 하는 경우 IB가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-106">IBs are also useful when a group needs to be isolated or prevented from communicating with anyone outside of that group.</span></span>

>[!NOTE]
>- <span data-ttu-id="693af-107">테넌트에서 IB(정보 장벽) 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-107">Information barrier (IB) groups cannot be created across tenants.</span></span>
>- <span data-ttu-id="693af-108">봇, Azure AD(Azure Active Directory) 앱 및 일부 API를 사용하여 사용자를 추가하는 것은 버전 1에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-108">Using bots, Azure Active Directory (Azure AD) apps, and some APIs to add users is not supported in version 1.</span></span>
>- <span data-ttu-id="693af-109">개인 채널은 구성하는 IB 정책을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-109">Private channels are compliant to IB policies that you configure.</span></span>
>- <span data-ttu-id="693af-110">새: Teams에 연결된 SharePoint 사이트에 대한 장벽에 대한 지원에 대한 자세한 내용은 Microsoft Teams 사이트와 연결된 [세그먼트를 참조하세요.](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)</span><span class="sxs-lookup"><span data-stu-id="693af-110">New: For information about support for barriers for SharePoint sites that are connected to Teams, see [Segments associated with Microsoft Teams sites](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

<span data-ttu-id="693af-111">IB 정책은 또한 검색 및 검색을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-111">IB policies also prevent lookups and discovery.</span></span> <span data-ttu-id="693af-112">다른 사용자와 통신하지 말아야 하는 경우 사용자 선택기에서 해당 사용자를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-112">If you attempt to communicate with someone you shouldn't be communicating with, you won't find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="693af-113">배경</span><span class="sxs-lookup"><span data-stu-id="693af-113">Background</span></span>

<span data-ttu-id="693af-114">B의 기본 드라이버는 금융 서비스 업계에서 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-114">The primary driver for IBs comes from the financial services industry.</span></span> <span data-ttu-id="693af-115">금융 산업 규제[기관(FINRA)은]( https://www.finra.org)구성원 회사 내에서 B 및 이해 상충을 검토하고 이러한 충돌 관리에 대한 지침을 제공합니다(FINRA 2241, 부채 조사 규제 [고지 15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)</span><span class="sxs-lookup"><span data-stu-id="693af-115">The Financial Industry Regulatory Authority ([FINRA]( https://www.finra.org)) reviews IBs and conflicts of interest within member firms and provides guidance about managing such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>

<span data-ttu-id="693af-116">그러나 B를 도입한 이후 다른 많은 영역에서 유용하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-116">However, since introducing IBs, many other areas have found them to be useful.</span></span> <span data-ttu-id="693af-117">다른 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-117">Other common scenarios include:</span></span>

- <span data-ttu-id="693af-118">교육: 한 학교의 학생은 다른 학교의 학생에 대한 연락처 세부 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>

- <span data-ttu-id="693af-119">법적: 한 클라이언트의 변호사가 획득한 데이터의 기밀성을 유지하고 다른 클라이언트를 나타내는 동일한 회사에 대한 변호사가 액세스하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-119">Legal: Maintaining the confidentiality of data that is obtained by the lawyer of one client and preventing it from being accessed by a lawyer for the same firm who represents a different client.</span></span>

- <span data-ttu-id="693af-120">정부: 부서 및 그룹 전체에서 정보 액세스 및 제어가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-120">Government: Information access and control are limited across departments and groups.</span></span>

- <span data-ttu-id="693af-121">전문 서비스: 회사의 사용자 그룹은 고객 참여 중에 게스트 액세스를 통해 클라이언트 또는 특정 고객과만 채팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-121">Professional services: A group of people in a company is only able to chat with a client or a specific customer via guest access during a customer engagement.</span></span>

<span data-ttu-id="693af-122">예를 들어 Enrico는 금융 부문에 속하고 Pradeep은 재무 고문 세그먼트에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="693af-123">Enrico와 Pradeep은 조직의 IB 정책이 이러한 두 세그먼트 간의 통신 및 공동 작업을 차단하기 때문에 서로 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="693af-124">그러나 Enrico 및 Pradeep는 HR에서 Lee와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![세그먼트 간 통신을 방지하는 정보 장벽을 보여주는 예제](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="693af-126">정보 장벽을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="693af-126">When to use information barriers</span></span>

<span data-ttu-id="693af-127">다음과 같은 상황에서 B를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-127">You might want to use IBs in situations like these:</span></span>

- <span data-ttu-id="693af-128">팀은 특정 다른 팀과 데이터를 통신하거나 공유하지 못하도록 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="693af-129">팀은 팀 외부의 다른 사용자와 데이터를 통신하거나 공유하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="693af-130">정보 장벽 정책 평가 서비스는 통신이 IB 정책을 준수하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with IB policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="693af-131">정보 장벽 정책 관리</span><span class="sxs-lookup"><span data-stu-id="693af-131">Managing information barrier policies</span></span>

<span data-ttu-id="693af-132">IB 정책은 PowerShell cmdlet을 사용하여 Microsoft 365 준수 센터(SCC)에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-132">IB policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="693af-133">자세한 내용은 정보 [장벽에 대한 정책 정의를 참조하세요.](/office365/securitycompliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="693af-133">For more information, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="693af-134">정책을 설정하거나 정의하기 전에 Microsoft Teams에서 범위가 지정된 디렉터리 검색을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-134">Before you set up or define policies, you must enable scoped directory search in Microsoft Teams.</span></span> <span data-ttu-id="693af-135">정보 장벽에 대한 정책을 설정하거나 정의하기 전에 범위가 지정된 디렉터리 검색을 사용하도록 설정한 후 적어도 몇 시간 정도 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="693af-136">자세한 내용은 정보 장벽 [정책 정의를 참조하세요.](/office365/securitycompliance/information-barriers-policies#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="693af-136">For more information, see [Define information barrier policies](/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="693af-137">정보 장벽 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="693af-137">Information barriers administrator role</span></span>

<span data-ttu-id="693af-138">IB 준수 관리 역할은 IB 정책을 관리할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-138">The IB Compliance Management role is responsible for managing IB policies.</span></span> <span data-ttu-id="693af-139">이 역할에 대한 자세한 내용은 [Microsoft 365 준수 센터의 권한을 참조하세요.](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="693af-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="693af-140">정보 장벽 트리거</span><span class="sxs-lookup"><span data-stu-id="693af-140">Information barrier triggers</span></span>

<span data-ttu-id="693af-141">IB 정책은 다음 Teams 이벤트가 진행될 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-141">IB policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="693af-142">**구성원이 팀에** 추가됩니다. 팀에 사용자를 추가할 때마다 사용자의 정책이 다른 팀 구성원의 IB 정책에 대해 평가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the IB policies of other team members.</span></span> <span data-ttu-id="693af-143">사용자가 성공적으로 추가된 후 사용자는 추가 확인 없이 팀의 모든 함수를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="693af-144">사용자의 정책이 팀에 추가되지 못하도록 차단하는 경우 사용자가 검색에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-144">If the user's policy blocks them from being added to the team, the user won't show up in search.</span></span>

    ![팀에 추가할 새 멤버를 검색하고 일치를 찾을 수 없는 스크린샷](media/information-barriers-add-members.png)

- <span data-ttu-id="693af-146">**새 채팅이 요청됩니다.** 사용자가 하나 이상의 다른 사용자와 새 채팅을 요청할 때마다 채팅은 IB 정책을 위반하지 않는지 확인하도록 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-146">**A new chat is requested** - Each time that a user requests a new chat with one or more other users, the chat is evaluated to make sure that it isn't violating any IB policies.</span></span> <span data-ttu-id="693af-147">대화가 IB 정책을 위반하는 경우 대화가 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-147">If the conversation violates an IB policy, then the conversation isn't started.</span></span>

    <span data-ttu-id="693af-148">다음은 1:1 채팅의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-148">Here's an example of a 1:1 chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-149">![1:1 채팅에서 차단된 통신을 보여주는 스크린샷](media/information-barriers-one-one-chat.png)</span><span class="sxs-lookup"><span data-stu-id="693af-149">![Screenshot showing blocked communication in 1:1 chat](media/information-barriers-one-one-chat.png)</span></span>

    <span data-ttu-id="693af-150">다음은 그룹 채팅의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-150">Here's an example of a group chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-151">![그룹 채팅을 보여주는 스크린샷](media/information-barriers-group-chat.png)</span><span class="sxs-lookup"><span data-stu-id="693af-151">![Screenshot showing group chat](media/information-barriers-group-chat.png)</span></span>

- <span data-ttu-id="693af-152">**사용자가 모임에** 참가하도록 초대됩니다. 사용자가 모임에 참가하도록 초대하면 사용자에게 적용되는 IB 정책이 다른 팀 구성원에게 적용되는 IB 정책에 대해 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the IB policy that applies to the user is evaluated against the IB policies that apply to the other team members.</span></span> <span data-ttu-id="693af-153">위반이 있는 경우 사용자는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-153">If there's a violation, the user won't be allowed to join the meeting.</span></span>

    ![모임에서 차단된 사용자를 보여주는 스크린샷](media/information-barriers-meeting.png)

- <span data-ttu-id="693af-155">**화면은** 두 개 이상의 사용자 간에 공유됩니다. 사용자가 다른 사용자와 화면을 공유하는 경우 공유가 다른 사용자의 IB 정책을 위반하지 않는지 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-155">**A screen is shared between two or more users** - When a user shares a screen with other users, the sharing must be evaluated to make sure that it doesn't violate the IB policies of other users.</span></span> <span data-ttu-id="693af-156">IB 정책을 위반하는 경우 화면 공유는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-156">If an IB policy is violated, the screen share won't be allowed.</span></span>

    <span data-ttu-id="693af-157">정책이 적용되기 전에 화면 공유의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-157">Here's an example of screen share before the policy is applied.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-158">![사용자 채팅을 보여주는 스크린샷](media/ib-before-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="693af-158">![Screenshot showing a user chat](media/ib-before-screen-share-policy.png)</span></span>

    <span data-ttu-id="693af-159">정책이 적용된 후 화면 공유의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-159">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="693af-160">화면 공유 및 통화 아이콘은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-160">The screen share and call icons aren't visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-161">![차단된 설정이 있는 사용자 char을 보여주는 스크린샷](media/ib-after-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="693af-161">![Screenshot showing user char with blocked settings](media/ib-after-screen-share-policy.png)</span></span>

- <span data-ttu-id="693af-162">**사용자가 Teams에** 전화 걸기 - 사용자가 VOIP를 통해 다른 사용자 또는 사용자 그룹에 음성 통화를 시작할 때마다 호출이 다른 팀 구성원의 IB 정책을 위반하지 않는지 확인하도록 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-162">**A user places a phone call in Teams** - Whenever a user initiates a voice call (via VOIP) to another user or group of users, the call is evaluated to make sure that it doesn't violate the IB policies of other team members.</span></span> <span data-ttu-id="693af-163">위반이 있는 경우 음성 통화가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-163">If there's any violation, the voice call is blocked.</span></span>

- <span data-ttu-id="693af-164">**Teams의 게스트** - Teams의 게스트에게도 IB 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-164">**Guests in Teams** - IB policies apply to guests in Teams, too.</span></span> <span data-ttu-id="693af-165">조직의 전역 주소 목록에서 게스트를 검색해야 하는 경우 [Microsoft 365 그룹에서](/microsoft-365/admin/create-groups/manage-guest-access-in-groups)게스트 액세스 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="693af-165">If guests need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="693af-166">게스트를 검색할 수 있는 경우 [IB 정책을 정의할 수 있습니다.](/office365/securitycompliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="693af-166">Once guests are discoverable, you can [define IB policies](/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="693af-167">정책 변경이 기존 채팅에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="693af-167">How policy changes impact existing chats</span></span>

<span data-ttu-id="693af-168">IB 정책 관리자가 정책을 변경하거나 사용자의 프로필 변경(예: 작업 변경)으로 인해 정책 변경이 활성화된 경우 정보 장벽 정책 평가 서비스는 자동으로 구성원을 검색하여 팀의 구성원 자격이 정책을 위반하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-168">When the IB policy administrator makes changes to a policy, or when a policy change is activated because of a change to a user's profile (such as for a job change), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that their membership in the team doesn't violate any policies.</span></span>

<span data-ttu-id="693af-169">사용자 간에 기존 채팅 또는 다른 통신이 있으며 새 정책이 설정되거나 기존 정책이 변경된 경우 서비스는 기존 통신을 평가하여 통신이 계속 발생할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-169">If there's an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="693af-170">**1:1 채팅** - 두 사용자 간의 통신이 더 이상 허용되지 않습니다(통신을 차단하는 정책의 한 사용자 또는 둘 다에게 애플리케이션으로 인하여) 추가 통신이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-170">**1:1 chat** - If communication between two users is no longer allowed (because of application to one or both users of a policy that blocks communication), further communication is blocked.</span></span> <span data-ttu-id="693af-171">기존 채팅 대화는 읽기 전용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-171">Their existing chat conversations become read-only.</span></span>

    <span data-ttu-id="693af-172">다음은 채팅이 표시되는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-172">Here's an example that shows the chat is visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-173">![사용자 채팅을 보여주는 스크린샷을 사용할 수 있습니다.](media/ib-before-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="693af-173">![Screenshot showing user chat is available](media/ib-before-1-1chat-policy.png)</span></span>

    <span data-ttu-id="693af-174">채팅이 비활성화되어 있는 경우를 보여주는 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-174">Here's an example that shows the chat is disabled.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-175">![사용자 채팅을 표시하는 스크린샷이 비활성화되어 있습니다.](media/ib-after-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="693af-175">![Screenshot showing user chat is disabled](media/ib-after-1-1chat-policy.png)</span></span>

- <span data-ttu-id="693af-176">**그룹 채팅** - 한 사용자와 그룹 간 통신이 더 이상 허용되지 않는 경우(예: 사용자가 작업을 변경하기 때문에) 참여가 정책을 위반하는 다른 사용자와 함께 그룹 채팅에서 제거될 수 있으며 그룹과의 추가 통신은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-176">**Group chat** - If communication from one user to a group is no longer allowed (for example, because a user changed jobs), the user—along with the other users whose participation violates the policy—may be removed from group chat, and further communication with the group won't be allowed.</span></span> <span data-ttu-id="693af-177">사용자는 여전히 이전 대화를 볼 수 있지만 그룹과의 새 대화를 보거나 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-177">The user can still see old conversations, but won't be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="693af-178">통신을 방지하는 새 정책 또는 변경된 정책이 두 개 이상의 사용자에게 적용되는 경우 정책의 영향을 받는 사용자는 그룹 채팅에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-178">If the new or changed policy that prevents communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="693af-179">이전 대화를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-179">They can still see old conversations.</span></span>

  <span data-ttu-id="693af-180">이 예제에서는 Enrico가 조직 내의 다른 부서로 이동하여 그룹 채팅에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-180">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![사용자가 제거된 그룹 채팅 스크린샷](media/information-barriers-user-changes-job.png)

  <span data-ttu-id="693af-182">Enrico는 더 이상 그룹 채팅에 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-182">Enrico can no longer send messages to the group chat.</span></span>

  ![사용자가 그룹에서 제거되어 그룹 채팅에 메시지를 보낼 수 없는 경우의 스크린샷](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="693af-184">**팀** - 그룹에서 제거된 모든 사용자가 팀에서 제거되고 기존 또는 새 대화를 보거나 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-184">**Team** - Any users who have been removed from the group are removed from the team and won't be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="693af-185">시나리오: 기존 채팅의 사용자가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-185">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="693af-186">현재 사용자는 IB 정책이 다른 사용자를 차단하는 경우 다음 시나리오를 경험합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-186">Currently, users experience the following scenarios if an IB policy blocks another user:</span></span>

- <span data-ttu-id="693af-187">**사람 탭** - 사용자가 사람 탭에서 차단된 사용자를 볼 **수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-187">**People tab** - A user can't see blocked users on the **People** tab.</span></span>

- <span data-ttu-id="693af-188">**사람 선택기** - 차단된 사용자는 사람 선택기에서 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-188">**People Picker** - Blocked users won't be visible in the people picker.</span></span>

    ![정책이 다른 사용자의 정보를 표시하지 못하도록 사용자에게 경고하는 Teams 스크린샷](media/information-barriers-people-picker.png)

- <span data-ttu-id="693af-190">**활동 탭** - 사용자가 차단된 사용자의 활동 탭을 방문하는 경우 게시물이 나타나지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="693af-190">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="693af-191">(활동 **탭은** 채널 게시물만 표시하며 두 사용자 간에 공통 채널이 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="693af-191">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="693af-192">다음은 차단된 활동 탭 보기의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-192">Here's an example of the activity tab view that is blocked.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-193">![차단된 활동 탭을 보여주는 스크린샷](media/ib-after-activity-tab-policy.png)</span><span class="sxs-lookup"><span data-stu-id="693af-193">![Screenshot showing the activity tab that is blocked](media/ib-after-activity-tab-policy.png)</span></span>

- <span data-ttu-id="693af-194">**오그** 차트 - 사용자가 차단된 사용자가 나타나는 오그 차트에 액세스하는 경우 차단된 사용자가 오그 차트에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-194">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user won't appear on the org chart.</span></span> <span data-ttu-id="693af-195">대신 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-195">Instead, an error message will appear.</span></span>

- <span data-ttu-id="693af-196">**사람 카드** - 사용자가 대화에 참여하고 사용자가 나중에 차단된 경우 차단된 사용자의 이름을 마우스로 를 때 다른 사용자가 사람 카드 대신 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-196">**People card** - If a user participates in a conversation and the user is later blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="693af-197">카드에 나열된 작업(예: 통화 및 채팅)은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-197">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>

- <span data-ttu-id="693af-198">**추천 연락처** - 차단된 사용자가 제안된 연락처 목록에 나타나지 않습니다(새 사용자에게 나타나는 초기 연락처 목록).</span><span class="sxs-lookup"><span data-stu-id="693af-198">**Suggested contacts** - Blocked users don't appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>

- <span data-ttu-id="693af-199">**채팅 연락처** - 사용자가 채팅 대화 목록에서 차단된 사용자를 볼 수 있지만 차단된 사용자가 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-199">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="693af-200">사용자가 차단된 사용자에서 수행할 수 있는 유일한 작업은 삭제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-200">The only action that the user can perform on the blocked users is to delete them.</span></span> <span data-ttu-id="693af-201">사용자는 해당 대화를 클릭하여 과거 대화를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-201">The user can also click on them to view their past conversation.</span></span>

- <span data-ttu-id="693af-202">**통화 연락처** - 사용자가 통화 연락처 목록에서 차단된 사용자를 볼 수 있지만 차단된 사용자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-202">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="693af-203">사용자가 블록에서 수행할 수 있는 유일한 작업은 해당 사용자를 삭제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-203">The only action that the user can perform on the block users is to delete them.</span></span>

    <span data-ttu-id="693af-204">다음은 통화 연락처 목록에서 차단된 사용자의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-204">Here's an example of a blocked user in the calls contact list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-205">![사용자 채팅을 보여주는 스크린샷](media/ib-before-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="693af-205">![Screenshot showing user user chat](media/ib-before-chat-contacts-policy.png)</span></span>

    <span data-ttu-id="693af-206">다음은 통화 콘텐츠 목록의 사용자에 대해 사용하지 않도록 설정되는 채팅의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-206">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="693af-207">![채팅에서 차단된 사용자를 보여주는 스크린샷](media/ib-after-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="693af-207">![Screenshot showing user blocked from chat](media/ib-after-chat-contacts-policy.png)</span></span>

- <span data-ttu-id="693af-208">**Skype에서 Teams로** 마이그레이션 - 비즈니스용 Skype에서 Teams로 마이그레이션하는 동안 IB 정책에 의해 차단된 모든 사용자도 Teams로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-208">**Skype to Teams migration** - During a migration from Skype for Business to Teams, all users—even those users who are blocked by IB policies—will be migrated to Teams.</span></span> <span data-ttu-id="693af-209">그런 다음 위에서 설명한 대로 해당 사용자를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-209">Those users are then handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="693af-210">Teams 정책 및 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="693af-210">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="693af-211">팀이 만들어지면 SharePoint 사이트가 프로비전 및 파일 환경을 위해 Microsoft Teams와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-211">When a team is created, a SharePoint site is provisioned and associated with Microsoft Teams for the files experience.</span></span> <span data-ttu-id="693af-212">이 SharePoint 사이트 및 파일에는 기본적으로 정보 장벽 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-212">Information barrier policies aren't honored on this SharePoint site and files by default.</span></span> <span data-ttu-id="693af-213">SharePoint 및 OneDrive에서 정보 장벽을 사용하도록 설정하려면 [SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) 항목과 함께 정보 장벽 사용의 지침 및 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="693af-213">To enable information barriers in SharePoint and OneDrive, follow the guidance and steps in the [Use information barriers with SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) topic.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="693af-214">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="693af-214">Required licenses and permissions</span></span>

<span data-ttu-id="693af-215">계획 및 가격 책정을 비롯한 라이선스 및 사용 권한에 대한 자세한 내용은 보안 규정 준수에 대한 [Microsoft 365 & 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="693af-215">For more information on licenses and permissions, including plans and pricing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="known-issues"></a><span data-ttu-id="693af-216">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="693af-216">Known Issues</span></span>

- <span data-ttu-id="693af-217">**사용자가 모임에** 참가할 수 없습니다. IB 정책이 설정된 경우 모임 참석 제한보다 큰 경우 사용자가 모임에 참가할 [수](limits-specifications-teams.md)없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-217">**Users can't join ad-hoc meetings**: If IB policies are enabled, users aren't allowed to join meetings if the size of the meeting roster is greater than the [meeting attendance limits](limits-specifications-teams.md).</span></span> <span data-ttu-id="693af-218">근본 원인은 IB가 사용자가 모임 채팅 로스터에 추가할 수 있는지 여부에 따라 확인하며, 해당 사용자를 모임에 추가할 수 있는 경우만 모임에 참가할 수 있도록 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-218">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="693af-219">모임에 참가하는 사용자는 해당 사용자를 목록에 추가합니다. 따라서 모임을 다시 진행하기 위해 로스터를 빠르게 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-219">A user joining a meeting once adds that user to the roster; hence for recurring meetings, the roster can fill up fast.</span></span> <span data-ttu-id="693af-220">채팅 로스터가 모임 참석 제한에 도달하면 [모임에](limits-specifications-teams.md)추가 사용자를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-220">Once the chat roster reaches the [meeting attendance limits](limits-specifications-teams.md), no additional users are allowed to be added to the meeting.</span></span> <span data-ttu-id="693af-221">테넌트에 대해 IB를 사용하도록 설정하고 채팅 로스터가 모임에 대해 가득 차면 새 사용자(아직 참가명단에 없는 사용자)는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-221">If IB is enabled for the tenant and the chat roster is full for a meeting, new users (those users who aren't already on the roster) aren't allowed to join the meeting.</span></span> <span data-ttu-id="693af-222">하지만 테넌트에 대해 IB를 사용하도록 설정하지 못하고 모임 채팅 로스터가 가득 차면 새 사용자(아직 참가명단에 없는 사용자)는 모임에 참가할 수 있지만 모임에 채팅 옵션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-222">But if IB isn't enabled for the tenant and the meeting chat roster is full, new users (those users who aren't already on the roster) are allowed to join the meeting, though they won't see the chat option in the meeting.</span></span> <span data-ttu-id="693af-223">단기 솔루션은 모임 채팅 목록에서 비활성 구성원을 제거하여 새 사용자를 위한 공간을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="693af-223">A short-term solution is to remove inactive members from the meeting chat roster to make space for new users.</span></span> <span data-ttu-id="693af-224">그러나 나중에 모임 채팅 로스터의 크기를 늘려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-224">We will, however, be increasing the size of meeting chat rosters at a later date.</span></span>
- <span data-ttu-id="693af-225">**사용자가 채널** 모임에 참가할 수 없습니다. IB 정책이 설정된 경우 사용자가 팀의 구성원이 아닌 경우 채널 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-225">**Users can't join channel meetings**: If IB policies are enabled, users aren't allowed to join channel meetings if they're not a member of the team.</span></span> <span data-ttu-id="693af-226">근본 원인은 IB가 사용자가 모임 채팅 로스터에 추가할 수 있는지 여부에 따라 확인하며, 해당 사용자를 모임에 추가할 수 있는 경우만 모임에 참가할 수 있도록 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-226">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="693af-227">채널 모임의 채팅 스레드는 Team/Channel 구성원만 사용할 수 있으며, 비회원은 채팅 스레드를 보거나 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-227">The chat thread in a channel meeting is available to Team/Channel members only, and non-members can't see or access the chat thread.</span></span> <span data-ttu-id="693af-228">테넌트에 대해 IB를 사용하도록 설정하고 팀이 아닌 구성원이 채널 모임에 참가하려고 하면 해당 사용자가 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-228">If IB is enabled for the tenant and a non-team member attempts to join a channel meeting, that user isn't allowed to join the meeting.</span></span> <span data-ttu-id="693af-229">그러나 테넌트에  대해 IB를 사용하도록 설정하지 못하고 팀 구성원이 아닌 구성원이 채널 모임에 참가하려고 하면 사용자가 모임에 참가할 수 있지만 모임에 채팅 옵션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-229">However, if IB is *not* enabled for the tenant and a non-team member attempts to join a channel meeting, the user is allowed to join the meeting—but they won't see the chat option in the meeting.</span></span>
- <span data-ttu-id="693af-230">**팀 소유자가** 제거되지 않습니다. Teams 채널에 두 개 이상의 충돌 세그먼트가 있는 새 IB 정책이 적용되면 팀 소유자가 있는 세그먼트가 더 높은 기본 설정이 제공되고 다른 세그먼트 사용자가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="693af-230">**Team owners are not removed**: If a new IB policy is applied that results in two or more conflicting segments present in a Teams channel, the segments with team owners are given higher preference and other segment users are removed.</span></span> <span data-ttu-id="693af-231">또한 현재 팀 소유자는 다른 소유자/사용자와 충돌하는 경우에도 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-231">Also, at this time, team owners are not getting removed, even if they are in conflict with other owners/users.</span></span> <span data-ttu-id="693af-232">테넌트 관리자 및 다른 채널 소유자는 충돌하는 소유자를 수동으로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="693af-232">Tenant admins and other channel owners will have to remove conflicting owners manually.</span></span>
- <span data-ttu-id="693af-233">**테넌트에서** 허용되는 최대 세그먼트 수: 각 테넌트는 IB 정책을 구성할 때 최대 100개 세그먼트를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-233">**Maximum number of segments allowed in a tenant**: Each tenant can set up to 100 segments when configuring IB policies.</span></span> <span data-ttu-id="693af-234">구성할 수 있는 정책 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-234">There is no limit on the number of policies that can be configured.</span></span>

- <span data-ttu-id="693af-235">**IB** 정책이 페더리된 사용자에 대해 작동하지 않습니다. 외부 테넌트와 페더연맹을 허용하는 경우 해당 테넌트의 사용자는 IB 정책에 의해 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-235">**IB policies don't work for federated users**: If you allow federation with external tenants, the users of those tenants won't be restricted by IB policies.</span></span> <span data-ttu-id="693af-236">조직의 사용자가 외부 페더러드 사용자가 구성한 채팅 또는 모임에 참가하는 경우 IB 정책도 조직의 사용자 간의 통신을 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-236">If users of your organization join a chat or meeting organized by external federated users, then IB policies also won't restrict communication between users of your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="693af-237">추가 정보</span><span class="sxs-lookup"><span data-stu-id="693af-237">More information</span></span>

- <span data-ttu-id="693af-238">IB에 대한 자세한 내용은 정보 장벽 [을 참조하세요.](/office365/securitycompliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="693af-238">To learn more about IBs, see [Information barriers](/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="693af-239">IB 정책을 설정하는 경우 정보 [장벽에 대한 정책 정의를 참조하세요.](/office365/securitycompliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="693af-239">To set up IB policies, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="693af-240">IB 정책을 편집하거나 제거하려면 정보 장벽 정책 [편집(또는 제거)을 참조하세요.](/microsoft-365/compliance/information-barriers-edit-segments-policies)</span><span class="sxs-lookup"><span data-stu-id="693af-240">To edit or remove IB policies, see [Edit (or remove) information barrier policies](/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>

## <a name="availability"></a><span data-ttu-id="693af-241">가용성</span><span class="sxs-lookup"><span data-stu-id="693af-241">Availability</span></span>

- <span data-ttu-id="693af-242">이 기능은 공용 클라우드에서 사용할 수 있습니다. 2021년 1월에는 GCC 클라우드에서 정보 장벽을 롤아웃했습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-242">The feature is available in our public cloud; in January 2021, we rolled out Information Barriers in the GCC cloud.</span></span>
- <span data-ttu-id="693af-243">이 기능은 GCCH 및 DOD 클라우드에서 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="693af-243">The feature is not yet available in the GCCH and DOD clouds.</span></span>