---
title: EDU 관리자용 Microsoft Teams 정책 패키지
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 정책 패키지를 사용 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d4a11952ea65a5380abb3ba284e13bab6d5d4e90
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155050"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a><span data-ttu-id="be4ff-103">EDU 관리자용 Microsoft Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="be4ff-103">Microsoft Teams policy packages for EDU admins</span></span>

<span data-ttu-id="be4ff-104">Microsoft 팀의 정책 패키지는 기관에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-104">A policy package in Microsoft Teams collects predefined policies and policy settings that you can assign to users with similar roles in your institution.</span></span> <span data-ttu-id="be4ff-105">정책 패키지는 정책을 관리할 때 일관성을 단순화 하 고 효율적으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-105">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="be4ff-106">일반적인 연습에서는 각 사용자에 게 정책 패키지를 할당 하 고 필요에 따라 각 패키지의 정책을 다시 정의 하 여 해당 사용자 그룹의 요구에 맞게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-106">In normal practice, you assign each of your users a policy package, and as necessary redefine the policies in each package to suit the needs of that user group.</span></span> <span data-ttu-id="be4ff-107">패키지의 설정을 업데이트 하면 해당 패키지에 할당 된 모든 사용자가 대량 업데이트로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-107">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="be4ff-108">일반적으로 교육 기관에는 학생의 연령 및 성숙도에 따라 고유한 요구 사항으로 많은 사용자 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-108">Educational institutions in general have many user types with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="be4ff-109">예를 들어 강사와 직원에 게 Microsoft 팀에 대 한 전체 액세스 권한을 부여할 수 있지만, 학생을 위해 Microsoft 팀의 기능을 제한 하 여 안전 하 고 중요 한 학습 환경을 장려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-109">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="be4ff-110">정책 패키지를 사용 하 여 학교 커뮤니티에서 다른 cohorts의 요구 사항에 따라 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-110">You can use policy packages to tailor settings based on the needs of different cohorts in your school community.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="be4ff-111">정책 패키지 란?</span><span class="sxs-lookup"><span data-stu-id="be4ff-111">What is a policy package?</span></span>

<span data-ttu-id="be4ff-112">정책 패키지를 통해 Microsoft 팀이 조직의 특정 사용자 집합에 대해 사용 하도록 허용 하거나 제한할 수 있는 Microsoft 팀 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-112">Policy packages let you control Microsoft Teams features that allow or restrict Microsoft Teams use for  specific sets of people in your organization.</span></span> <span data-ttu-id="be4ff-113">각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 대 한 일반적인 활동을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-113">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span>

<span data-ttu-id="be4ff-114">정책 패키지 미리 정의할 정책:</span><span class="sxs-lookup"><span data-stu-id="be4ff-114">Policy packages predefine policies for:</span></span>
- <span data-ttu-id="be4ff-115">메시징</span><span class="sxs-lookup"><span data-stu-id="be4ff-115">Messaging</span></span>
- <span data-ttu-id="be4ff-116">모임</span><span class="sxs-lookup"><span data-stu-id="be4ff-116">Meetings</span></span>
- <span data-ttu-id="be4ff-117">앱 설정</span><span class="sxs-lookup"><span data-stu-id="be4ff-117">App Setup</span></span>
- <span data-ttu-id="be4ff-118">전화</span><span class="sxs-lookup"><span data-stu-id="be4ff-118">Calling</span></span>
- <span data-ttu-id="be4ff-119">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="be4ff-119">Live events</span></span>

<span data-ttu-id="be4ff-120">Microsoft 팀에는 현재 다음 정책 패키지가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-120">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="be4ff-121">Microsoft 팀 관리 센터에 나열 된 패키지 이름</span><span class="sxs-lookup"><span data-stu-id="be4ff-121">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="be4ff-122">사용 용도</span><span class="sxs-lookup"><span data-stu-id="be4ff-122">Best used for</span></span>  |<span data-ttu-id="be4ff-123">설명</span><span class="sxs-lookup"><span data-stu-id="be4ff-123">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="be4ff-124">Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="be4ff-124">Education_Teacher</span></span>| <span data-ttu-id="be4ff-125">교사 및 스태프</span><span class="sxs-lookup"><span data-stu-id="be4ff-125">Educators and staff</span></span>| <span data-ttu-id="be4ff-126">이 정책 및 정책 설정 집합을 사용 하 여 조직 내 강사와 직원에 게 Microsoft 팀을 통해 채팅, 통화, 모임에 대 한 모든 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-126">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="be4ff-127">Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="be4ff-127">Education_PrimaryStudent</span></span> | <span data-ttu-id="be4ff-128">기본 학교 오래 된 학생</span><span class="sxs-lookup"><span data-stu-id="be4ff-128">Primary school aged students</span></span>  | <span data-ttu-id="be4ff-129">귀하의 기관 내에 있는 기본 학교 오래 된 학생이 Microsoft 팀 내에서 더 많은 제한을 필요로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-129">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="be4ff-130">이 정책 및 정책 설정 집합을 사용 하 여 모임 만들기 및 관리, 채팅 관리, 비공개 통화와 같은 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-130">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="be4ff-131">Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="be4ff-131">Education_SecondaryStudent</span></span>| <span data-ttu-id="be4ff-132">보조 학교 오래 된 학생</span><span class="sxs-lookup"><span data-stu-id="be4ff-132">Secondary school aged students</span></span> | <span data-ttu-id="be4ff-133">귀하의 기관 내에 있는 2 차 학교 오래 된 학생이 Microsoft 팀 내에서 더 많은 제한을 필요로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-133">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="be4ff-134">이 정책 및 정책 설정 집합을 사용 하 여 모임 만들기 및 관리, 채팅 관리, 비공개 통화와 같은 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-134">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="be4ff-135">Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="be4ff-135">Education_HigherEducationStudent</span></span> | <span data-ttu-id="be4ff-136">높은 교육 학생</span><span class="sxs-lookup"><span data-stu-id="be4ff-136">Higher education students</span></span> | <span data-ttu-id="be4ff-137">Intuition 내에서 교육 학생 수가 높을수록 더 적은 수의 학생이 필요 하지 않지만 몇 가지 제한 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-137">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="be4ff-138">이 정책 및 정책 설정 집합을 사용 하 여 조직 내에서 채팅, 통화, 모임에 대 한 액세스 권한을 부여할 수 있지만 학생 들이 외부 참가자와 Microsoft 팀을 사용 하는 방법은 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-138">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|||

<span data-ttu-id="be4ff-139">정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-139">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="be4ff-140">예를 들어 학교에 Education_Teacher 정책 패키지를 할당 하면 패키지의 각 정책에 대해 Education_Teacher 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-140">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="be4ff-142">교사와 관리 지원 담당자에 게 다른 정책이 필요 하다 고 판단 되는 경우 기존 패키지를 사용할 수 있습니다. 현재 사용 하지 않는 패키지를 식별 하 고 해당 그룹에 맞게 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-142">If you decide that teachers and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="be4ff-143">어떤 그룹에 어떤 패키지가 있는지 자신에 게 기록해 야 할 수 있지만,이는 패키지를 재활용 하는 유일한 장애입니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-143">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="why-use-policy-packages"></a><span data-ttu-id="be4ff-144">정책 패키지를 사용 하는 이유</span><span class="sxs-lookup"><span data-stu-id="be4ff-144">Why use policy packages</span></span>

<span data-ttu-id="be4ff-145">기관에 수백 개 또는 수천 명의 사용자가 있는 경우 "특정 패키지를 할당 하는 이유는 무엇 인가요? 그리고 모든 사용자에 게 다른 권한이 있는 경우" 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-145">If your institution has hundreds, or even thousands of users, you may be asking yourself: "Why take the time to assign one package or another to all those users?"</span></span>

<span data-ttu-id="be4ff-146">수백 명의 사용자에 게 패키지를 할당 하는 것은 관리 시간에 아무런 문제 없이 투자 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-146">Assigning packages to hundreds of users is an investment in administrative time, without question.</span></span> <span data-ttu-id="be4ff-147">투자에 대 한 중요 한 점은 시간이 지남에 따라 즉각적이 지는 것이 아니라 시간을 지불 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-147">An important thing about investments is that they pay off over time, rather than immediately.</span></span>

<span data-ttu-id="be4ff-148">교육 환경에는 같은 역할이 나 비슷한 역할을 갖는 사용자가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-148">In an educational environment, there are many users with the same or similar roles.</span></span> <span data-ttu-id="be4ff-149">사용자 환경을 관리 하는 것과 동일한 방식으로 시간에 따른 노력을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-149">You spend less effort over time when you manage their user experience the same way.</span></span> <span data-ttu-id="be4ff-150">패키지 그룹은 기관에 있는 다양 한 역할과 관련 된 정책 집합을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-150">Packages group a set of policies specific to the various roles in the institution.</span></span> <span data-ttu-id="be4ff-151">동일한 라이선스가 있지만 역할이 서로 다른 사용자는 해당 역할을 기준으로 하는 관련 정책을 할당할 수 있으며,이는 개별 사용자의 조정 정책 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-151">Users with the same license, but different roles, can have relevant policies assigned based on their role, which is more efficient than tweaking policies for individual users.</span></span>

<span data-ttu-id="be4ff-152">기관에 있는 모든 사용자를 그룹으로 정렬 하 고 패키지를 적용 한 후에는 패키지에 할당 된 모든 사용자에 대해 패키지 설정을 한 번만 변경 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-152">Once you have all users in the institution sorted into groups and have packages applied, managing them from then on is a matter of changing the package settings once for all users assigned to the package.</span></span> <span data-ttu-id="be4ff-153">패키지에 사용자를 할당 하기 전이나 후에 패키지 내에서 정책을 미세 조정 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4ff-153">You can choose to fine-tune the policies within a package before or after assigning users to the package.</span></span>

<span data-ttu-id="be4ff-154">단일 사용자 지정 패키지, 최대 20 명의 사용자에 게 패키지 할당, 각 패키지에 연결 된 정책 관리 및 업데이트에 대 한 단계별 지침은 [Microsoft 팀에서 정책 패키지 관리](manage-policy-packages.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be4ff-154">See [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 20 users, and managing and updating the policies linked to each package.</span></span>
