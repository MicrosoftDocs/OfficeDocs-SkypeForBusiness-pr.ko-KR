---
title: Microsoft 팀의 정보 장벽
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft 팀의 정보 장벽에 대해 설명 하 고 팀에 어떤 영향을 주는지 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12bd0102904ff933b5a2ffd6f12d8a8d3b76aaaa
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868695"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="86063-103">Microsoft 팀의 정보 장벽</span><span class="sxs-lookup"><span data-stu-id="86063-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="86063-104">IB (정보 장벽)은 관리자가 개인 또는 그룹이 서로 통신 하는 것을 방지 하기 위해 구성할 수 있는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="86063-104">Information barriers (IB) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="86063-105">예를 들어 한 부서가 다른 부서와 공유 하지 않아야 하는 정보를 처리 하거나 그룹 외부의 모든 사람과 통신 하는 것을 금지 또는 격리 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-105">This is useful if, for example, one department is handling information that shouldn't be shared with other departments or a group needs to be prevented, or isolated, from communicating with anyone outside of that group.</span></span>

> [!NOTE]
> - <span data-ttu-id="86063-106">테 넌 트 간에 정보 장벽 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="86063-107">봇을 사용 하 여 사용자를 추가 하는 것은 버전 1에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-107">Using bots to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="86063-108">개인 채널은 사용자가 구성한 정보 장벽 정책에 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="86063-108">Private channels are compliant to information barrier policies that you configure.</span></span>
> - <span data-ttu-id="86063-109">신규: 팀에 연결 된 SharePoint 사이트에 대 한 정보 장벽 지원은 이제 비공개 미리 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="86063-109">New: Information barrier support for SharePoint site connected to Teams is now in Private Preview.</span></span> <span data-ttu-id="86063-110">비공개 미리 보기에 참여 하려면 [여기](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) 를 클릭 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-110">Click [here](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) to participate in the private preview.</span></span>

<span data-ttu-id="86063-111">정보 장벽 정책은 또한 조회 및 검색을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-111">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="86063-112">따라서 통신 하지 않아야 하는 사람과 통신을 시도 하는 경우에는 사용자 선택에서 해당 사용자를 찾지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-112">This means that if you attempt to communicate with someone you should not be communicating with, you will not find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="86063-113">배경</span><span class="sxs-lookup"><span data-stu-id="86063-113">Background</span></span>

<span data-ttu-id="86063-114">정보 장벽에 대 한 기본 드라이버는 금융 서비스 업계에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-114">The primary driver for information barriers comes from the financial services industry.</span></span> <span data-ttu-id="86063-115">이 (가) 금융 업계 규정 기관 ([finra]( http://www.finra.org))은 회원 기업 내에 대 한 정보 장벽 및 충돌을 검토 하 고 그러한 충돌 (finra 2241, [부채 리서치 규정 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)을 관리 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-115">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

<span data-ttu-id="86063-116">그러나 정보 장벽 때문에 다른 많은 영역에서 유용 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-116">However, since introducing information barriers, many other areas have found them to be useful.</span></span> <span data-ttu-id="86063-117">다른 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-117">Other common scenarios include:</span></span>

- <span data-ttu-id="86063-118">교육: 한 학교에 있는 학생 들은 다른 학교 학생의 연락처 세부 정보를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>
- <span data-ttu-id="86063-119">법률: 한 클라이언트의 변호사에서 얻은 데이터의 기밀성을 다른 클라이언트를 나타내는 동일한 회사의 변호사에서 액세스 하지 못하도록 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-119">Legal: Maintaining confidentiality of data obtained by the lawyer of one client from being accessed by a lawyer for the same firm representing a different client.</span></span>
- <span data-ttu-id="86063-120">정부: 부서와 그룹 간에 정보 액세스 및 제어가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-120">Government: Information access and control is limited across departments and groups.</span></span>
- <span data-ttu-id="86063-121">전문 서비스: 회사의 사용자 그룹은 고객 참여 중에 페더레이션 또는 게스트 액세스를 통해 클라이언트나 특정 고객에 게 채팅할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-121">Professional services: A group of people in a company is only able to chat with a client or specific customer via federation or guest access during a customer engagement.</span></span>

<span data-ttu-id="86063-122">예를 들어 Enrico는 은행 부문 세그먼트에 속하고 재무 관리자 세그먼트에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="86063-123">조직의 IB 정책은 이러한 두 세그먼트 간의 통신과 공동 작업을 차단 하기 때문에, Pradeep는 서로 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="86063-124">그러나 Pradeep는 HR에 정영일와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![세그먼트 간 통신을 방지 하는 정보 장애물을 보여 주는 예](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="86063-126">정보 장애물을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="86063-126">When to use information barriers</span></span>

<span data-ttu-id="86063-127">다음과 같은 경우에 정보 장벽을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-127">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="86063-128">팀에서 특정 다른 팀과 데이터를 교환 하거나 공유 하는 것을 방지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="86063-129">팀은 팀 외부의 모든 사람과 데이터를 교환 하거나 공유 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="86063-130">정보 장벽 정책 평가 서비스는 통신이 정보 장벽 정책에 부합 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="86063-131">정보 장벽 정책 관리</span><span class="sxs-lookup"><span data-stu-id="86063-131">Managing information barrier policies</span></span>

<span data-ttu-id="86063-132">정보 장벽 정책은 PowerShell cmdlet을 사용 하 여 SCC (Microsoft 365 준수 센터)에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-132">Information barrier policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="86063-133">자세한 내용은 [정보 장벽에 대 한 정책 정의](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-133">For more information, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86063-134">정책을 설정 하거나 정의 하기 전에 **Microsoft 팀에서 범위 디렉터리 검색을 사용 하도록 설정 해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="86063-134">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="86063-135">범위 디렉터리 검색을 사용 하도록 설정한 후에는 정보 장벽에 대 한 정책을 설정 하거나 정의 하 고 나 서 몇 시간 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="86063-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="86063-136">[정보 장벽에 대 한 필수 구성 요소에 대해 자세히 알아보세요](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="86063-136">[Learn more about prerequisites for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="86063-137">정보 장벽 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="86063-137">Information barriers administrator role</span></span>

<span data-ttu-id="86063-138">IB 준수 관리 역할은 정보 장벽 정책 관리를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-138">The IB Compliance Management role is responsible for managing information barrier policies.</span></span> <span data-ttu-id="86063-139">이 역할에 대 한 자세한 내용은 [Microsoft 365 준수 센터의 사용 권한을](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="86063-140">정보 장벽 트리거</span><span class="sxs-lookup"><span data-stu-id="86063-140">Information barrier triggers</span></span>

<span data-ttu-id="86063-141">정보 장벽 정책은 다음 팀 이벤트가 발생 했을 때 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-141">Information barrier policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="86063-142">**구성원은 팀에 추가 되며** , 팀에 사용자를 추가할 때마다 다른 팀 구성원의 정보 장벽 정책에 대해 사용자의 정책을 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="86063-143">사용자가 성공적으로 추가 된 후에는 사용자가 추가 검사 없이 팀의 모든 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="86063-144">사용자의 정책이 팀에 추가 되는 것을 차단 하는 경우 사용자는 검색에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-144">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>

    ![그룹 채팅을 보여 주는 스크린샷](media/information-barriers-add-members.png)

- <span data-ttu-id="86063-146">**새로운 채팅 요청** -두 명 이상의 사용자 간에 새로운 채팅을 요청할 때마다 채팅은 정보 장벽 정책에 위반 되지 않도록 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-146">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn't violating any information barrier policies.</span></span> <span data-ttu-id="86063-147">대화가 정보 장벽 정책에 위배 되는 경우 대화가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-147">If the conversation violates an information barrier policy, then the conversation isn't initiated.</span></span>

    <span data-ttu-id="86063-148">다음은 1:1 채팅의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="86063-148">Here's an example of a 1:1 chat.</span></span>

     ![1:1 채팅에서 차단 된 통신을 보여 주는 스크린샷](media/information-barriers-one-one-chat.png)

    <span data-ttu-id="86063-150">다음은 그룹 채팅의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="86063-150">Here's an example of a group chat.</span></span>

    ![그룹 채팅을 보여 주는 스크린샷](media/information-barriers-group-chat.png)

- <span data-ttu-id="86063-152">**사용자가 모임에 참가 하도록 초대 됨** -사용자가 모임에 참가 하도록 초대 하면 다른 팀 구성원의 정책에 대해 사용자의 정책이 평가 되 고 위반이 있는 경우 사용자가 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there's a violation, the user will not be allowed to join the meeting.</span></span>

    ![모임에서 차단 된 사용자를 보여 주는 스크린샷](media/information-barriers-meeting.png)

- <span data-ttu-id="86063-154">두 명 이상의 사용자가 화면을 **공유** 하는 경우, 두 명 이상의 사용자가 화면을 공유할 때마다 화면 공유를 평가 하 여 다른 사용자의 정보 장벽 정책에 위배 되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-154">**A screen is shared between two or more users** - Any time a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn't violate the information barrier policies of other users.</span></span> <span data-ttu-id="86063-155">정보 장벽 정책이 위반 되는 경우 화면 공유는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-155">If an information barrier policy is violated, the screen share won't be allowed.</span></span>
- <span data-ttu-id="86063-156">**사용자가 팀에 VOIP (voice call)를 배치** 합니다-사용자가 다른 사용자 또는 사용자 그룹에 게 음성 통화를 시작할 때마다 해당 통화가 다른 팀 구성원의 정보 장벽 정책을 위반 하지 않도록 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-156">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn't violate the information barrier policies of other team members.</span></span> <span data-ttu-id="86063-157">위반 사항이 있는 경우 음성 통화가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-157">If there is any violation, the voice call is blocked.</span></span>
- <span data-ttu-id="86063-158">**팀의 게스트 사용자** -정보 장벽 정책은 팀의 게스트 사용자 에게도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-158">**Guest users in Teams** - Information barrier policies apply to guest users in Teams too.</span></span> <span data-ttu-id="86063-159">조직의 전체 주소 목록에서 게스트 사용자를 검색할 수 있어야 하는 경우 [Microsoft 365 그룹에서 게스트 액세스 관리](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-159">If guest users need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="86063-160">게스트 사용자가 검색 가능 하면 [정보 장벽 정책을 정의할](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-160">Once guest users are discoverable, you can [define information barrier policies](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="86063-161">정책 변경으로 기존 채팅에 영향을 주는 방법</span><span class="sxs-lookup"><span data-stu-id="86063-161">How policy changes impact existing chats</span></span>

<span data-ttu-id="86063-162">정보 장벽 정책 관리자가 정책을 변경 하거나 사용자 프로필 (예: 작업 변경 또는 유사한 이유)의 변경으로 인해 정책 변경이 적용 되는 경우 정보 장벽 정책 평가 서비스는 구성원을 자동으로 검색 하 여 팀 구성원이 정책을 위반 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-162">When the information barrier policy administrator makes changes to a policy, or a policy change kicks into effect because of a change to a user's profile (such as for a job change or a similar reason), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span>

<span data-ttu-id="86063-163">사용자 간에 기존 채팅 또는 다른 통신이 있는 경우 새 정책이 설정 되거나 기존 정책이 변경 되는 경우 서비스는 기존 통신을 평가 하 여 통신이 계속 발생할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-163">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span>

- <span data-ttu-id="86063-164">**1:1 채팅** -두 사용자 간의 통신이 더 이상 허용 되지 않음 (한 명 또는 두 명의 사용자에 게 정책 차단 통신이 적용 되는 경우), 추가 통신은 차단 되 고 채팅 대화는 읽기 전용 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-164">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span>

- <span data-ttu-id="86063-165">**그룹 채팅** -한 사용자에서 그룹으로의 통신을 더 이상 사용할 수 없는 경우 (예: 사용자가 작업을 변경 하는 경우) 해당 정책을 위반 하는 다른 사용자와 함께 그룹 채팅에서 제거 되 고 그룹과의 추가 통신은 허용 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-165">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="86063-166">사용자는 여전히 이전 대화 (읽기 전용)를 볼 수 있지만 그룹과 새로운 대화를 보거나 참여할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-166">The user can still see old conversations (which will be read-only), but will not be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="86063-167">통신을 차단 하는 새 정책이 여러 사용자에 게 적용 되는 경우 해당 정책의 영향을 받는 사용자가 그룹 채팅에서 제거 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-167">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="86063-168">이전 대화를 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-168">They can still see old conversations.</span></span>

<span data-ttu-id="86063-169">이 예제에서는 조직 내의 다른 부서로 이동 하 고 그룹 채팅에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-169">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![그룹 채팅을 보여 주는 스크린샷](media/information-barriers-user-changes-job.png)

<span data-ttu-id="86063-171">더 이상 그룹 채팅에 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-171">Enrico can no longer send messages to the group chat.</span></span>

  ![그룹 채팅을 보여 주는 스크린샷](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="86063-173">**팀** -그룹에서 제거 된 모든 사용자가 팀에서 제거 되 고 기존 또는 새 대화를 보거나 참여할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-173">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="86063-174">시나리오: 기존 채팅의 사용자가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-174">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="86063-175">현재는 정보 장벽 정책이 다른 사용자를 차단 하는 경우 사용자에 게 다음과 같은 경험을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-175">Currently, users experience the following if an information barrier policy blocks another user:</span></span>

- <span data-ttu-id="86063-176">**인물 정보 탭** -사용자가 대화 **상대** 탭에서 차단 된 사용자를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-176">**People tab** - A user cannot see blocked users on the **People** tab.</span></span>
- <span data-ttu-id="86063-177">**사용자 선택** -차단 된 사용자는 사용자 선택에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-177">**People Picker** - Blocked users will not be visible in the people picker.</span></span>

    ![그룹 채팅을 보여 주는 스크린샷](media/information-barriers-people-picker.png)
    
- <span data-ttu-id="86063-179">**활동 탭** -사용자가 차단 된 사용자의 **활동** 탭을 방문 하면 게시물이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-179">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="86063-180">( **활동** 탭에는 채널 게시물만 표시 되며, 두 사용자 사이에는 공통 채널이 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="86063-180">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>
- <span data-ttu-id="86063-181">**조직도** -사용자가 차단 된 사용자가 표시 되는 조직도에 액세스 하는 경우 차단 된 사용자가 조직도에 나타나지 않고 대신 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-181">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user will not appear on the org chart and an error message will appear instead.</span></span>
- <span data-ttu-id="86063-182">**인물 정보** -사용자가 대화에 참여 하 고 있고 그 사용자가 차단 되는 경우 사용자 카드에 차단 된 사용자의 이름을 가리키면 다른 사용자에 게 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-182">**People card** - If a user participates in a conversation and the user is subsequently blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="86063-183">카드 (통화 및 채팅 등)에 나열 된 동작을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-183">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>
- <span data-ttu-id="86063-184">**추천 연락처** -차단 된 사용자는 추천 연락처 목록 (새 사용자에 대해 표시 되는 초기 연락처 목록)에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-184">**Suggested contacts** - Blocked users do not appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>
- <span data-ttu-id="86063-185">**채팅 연락처** -사용자가 채팅 대화 상대 목록에서 차단 된 사용자를 볼 수 있지만 차단 되는 사용자를 식별 하 고 사용자가 수행할 수 있는 유일한 동작은 삭제 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86063-185">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span> <span data-ttu-id="86063-186">사용자는이를 클릭 하 여 이전 대화를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-186">The user can also click on them to view their past conversation.</span></span>
- <span data-ttu-id="86063-187">**대화 상대** 에 게 전화-사용자가 차단 된 사용자를 볼 수 있으 나 차단 되는 사용자를 식별 하 고 사용자가 수행할 수 있는 유일한 동작은 삭제 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86063-187">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span>
- <span data-ttu-id="86063-188">**Skype To 팀 마이그레이션** -비즈니스용 skype 마이그레이션 중-모든 사용자는 정보 장벽 정책에 의해 차단 된 경우에도 팀으로 마이그레이션되고, 위에서 설명한 대로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-188">**Skype to Teams migration** - During a Skype for Business to Teams migration, all users, even those blocked by information barrier policies, will be migrated to Teams and then will be handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="86063-189">팀 정책 및 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="86063-189">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="86063-190">팀을 만들 때 SharePoint 사이트를 프로 비전 하 고 파일 환경을 위해 팀과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-190">When a team is created, a SharePoint site is provisioned and associated with the Team for the files experience.</span></span> <span data-ttu-id="86063-191">이 SharePoint 사이트 및 파일에 대 한 액세스는 조직의 IB를 허용 하 고, 예를 들어 IB에 대 한 IB 세그먼트와 일치 하는 사용자만 액세스를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-191">Access to this SharePoint site and files honors the organization's IB, i.e., only the users whose IB segment matches per IB policy are allowed access.</span></span> <span data-ttu-id="86063-192">파일 공유 시에도 IB 정책이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86063-192">Even at the time of file sharing, the IB policy is honored.</span></span>

<span data-ttu-id="86063-193">예: Contoso Bank corporation에서 사용자 ' Sesha@contosobank.onmicrosoft.com '은 투자 은행 부문에 속하고 ' Nikita@contosobank.onmicrosoft.com ' 사용자는 세그먼트 권고에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-193">For example: In Contoso Bank corporation, user 'Sesha@contosobank.onmicrosoft.com' belongs to Investment Banking segment and user 'Nikita@contosobank.onmicrosoft.com' belongs to segment Advisory.</span></span> <span data-ttu-id="86063-194">조직의 IB 정책은 이러한 두 세그먼트 간의 통신과 공동 작업을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="86063-194">The organization's IB policy blocks communication and collaboration between these two segments.</span></span>
<span data-ttu-id="86063-195">사용자가 투자 은행 부문에 대 한 팀을 만드는 경우 팀과이를 지 원하는 SharePoint 사이트는 투자 은행 부문 사용자만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-195">When user Sesha creates a team for Investment Banking segment, the team and the SharePoint site that backs it will be accessible only to Investment Banking segment users.</span></span> <span data-ttu-id="86063-196">사이트 링크를가지고 있는 경우에도 사용자 Nikita 해당 사이트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86063-196">User Nikita can't access that site even if she has the site link.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="86063-197">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="86063-197">Required licenses and permissions</span></span>

<span data-ttu-id="86063-198">계획 및 가격을 비롯 한 자세한 내용은 [라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-198">For more details, including plans and pricing, see [Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="more-information"></a><span data-ttu-id="86063-199">추가 정보</span><span class="sxs-lookup"><span data-stu-id="86063-199">More information</span></span>

- <span data-ttu-id="86063-200">정보 장벽에 대해 자세히 알아보려면 [정보 장벽](https://docs.microsoft.com/office365/securitycompliance/information-barriers)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-200">To learn more about information barriers, see [Information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="86063-201">정보 장벽 정책을 설정 하려면 [정보 장벽에 대 한 정책 정의](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-201">To set up information barrier policies, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="86063-202">정보 장벽 정책을 편집 하거나 제거 하려면 [정보 장벽 정책 편집 (또는 제거)](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86063-202">To edit or remove information barrier policies, see [Edit (or remove) information barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>
