---
title: 'Lync Server 2013: 다이얼 플랜 및 정규화 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="fd9f4-102">Lync Server 2013의 다이얼 플랜 및 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="fd9f4-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd9f4-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="fd9f4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="fd9f4-104">다이얼 플랜은 전화 인증 및 통화 라우팅과 같은 목적으로 명명 된 위치, 개인 사용자 또는 연락처 개체의 전화 번호를 단일 표준 (E) 형식으로 변환 하는 정규화 규칙의 명명 된 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="fd9f4-105">정규화 규칙은 다양 한 형식으로 표시 되는 전화 번호가 지정 된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅되는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-105">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="fd9f4-106">전화 거는 위치와 전화를 걸고 있는 사람 또는 연락처 개체에 따라 같은 다이얼 문자열을 다르게 해석 하 고 번역할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-106">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="fd9f4-107">다이얼 플랜 범위</span><span class="sxs-lookup"><span data-stu-id="fd9f4-107">Dial Plan Scope</span></span>

<span data-ttu-id="fd9f4-108">다이얼 플랜의 *범위* 는 다이얼 플랜을 적용할 수 있는 계층 수준을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="fd9f4-109">Lync Server에서는 사용자에 게 특정 사용자 단위 다이얼 플랜을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="fd9f4-110">사용자 다이얼 플랜을 할당 하지 않으면 등록자 그룹 다이얼 플랜이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="fd9f4-111">등록자 풀 다이얼 플랜이 없으면 사이트 다이얼 플랜이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="fd9f4-112">마지막으로, 사용자에 게 적용 가능한 다른 다이얼 플랜이 없으면 전역 다이얼 플랜이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="fd9f4-113">클라이언트는 사용자가 Lync Server에 로그온 할 때 제공 되는 대역내 프로비저닝 설정을 통해 다이얼 플랜 범위 수준을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="fd9f4-114">관리자는 Lync Server 제어판을 사용 하 여 다이얼 플랜 범위 수준을 관리 하 고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd9f4-115">서비스 수준 PSTN (공개 교환 전화 네트워크) 게이트웨이 다이얼 플랜은 특정 게이트웨이에서 들어오는 전화에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="fd9f4-116">다이얼 플랜 범위 수준은 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="fd9f4-117">**사용자 다이얼 플랜:** 개인 사용자, 그룹 또는 연락처 개체에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="fd9f4-118">음성 응용 프로그램은 전화-컨텍스트를 사용자-기본으로 설정한 상태에서 통화를 받을 때 사용자 단위 다이얼 플랜을 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="fd9f4-119">다이얼 플랜을 지정 하기 위해 연락처 개체는 개별 사용자로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="fd9f4-120">**풀 다이얼 플랜:** 토폴로지에서 PSTN 게이트웨이 또는 등록자에 대 한 서비스 수준에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="fd9f4-121">풀 다이얼 플랜을 정의 하려면 다이얼 플랜을 적용할 특정 서비스 (PSTN 게이트웨이 또는 등록자 풀)를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="fd9f4-122">**사이트 다이얼 플랜:** 풀 다이얼 플랜 또는 사용자 다이얼 플랜에 할당 된 사용자, 그룹 또는 연락처 개체를 제외한 전체 사이트에 대해 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="fd9f4-123">사이트 다이얼 플랜을 정의 하려면 다이얼 플랜을 적용할 사이트를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="fd9f4-124">**글로벌 다이얼 플랜:** 제품과 함께 설치 된 기본 다이얼 플랜입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="fd9f4-125">전역 다이얼 플랜은 편집할 수 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="fd9f4-126">이 다이얼 플랜은 보다 구체적인 범위를 사용 하 여 다이얼 플랜을 구성 하 고 지정 하지 않는 한 배포의 모든 Enterprise Voice 사용자, 그룹 및 연락처 개체에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="fd9f4-127">다이얼 플랜 계획</span><span class="sxs-lookup"><span data-stu-id="fd9f4-127">Planning for Dial Plans</span></span>

<span data-ttu-id="fd9f4-128">다이얼 플랜을 계획 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="fd9f4-129">조직에 office가 있는 모든 로캘을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="fd9f4-130">목록은 최신 상태 여야 하며 완료 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-130">The list must be up-to-date and complete.</span></span> <span data-ttu-id="fd9f4-131">회사 조직이 변화 함에 따라 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-131">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="fd9f4-132">소규모 지사의 수가 많은 다국적 대기업에서는 시간이 오래 걸리는 작업이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-132">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="fd9f4-133">각 사이트의 유효한 번호 패턴을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="fd9f4-134">다이얼 플랜 계획 중 시간이 오래 걸리는 부분은 각 사이트의 유효한 번호 패턴을 식별 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-134">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site.</span></span> <span data-ttu-id="fd9f4-135">일부 경우에는 해당 사이트가 같은 국가/지역 또는 대륙 내에 있는 경우 특정 다이얼 플랜에 대해 작성 한 정규화 규칙을 다른 다이얼 플랜에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-135">In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent.</span></span> <span data-ttu-id="fd9f4-136">다른 경우에는 특정 다이얼 플랜에서 숫자를 약간만 변경 하면 다른 다이얼 플랜에서이를 사용 하는 것이 충분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-136">In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="fd9f4-137">다이얼 플랜의 이름을 지정 하기 위한 조직 차원의 스키마를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="fd9f4-138">표준 명명 스키마를 채택 하면 조직 전체의 일관성을 보장 하 고 유지 관리 및 업데이트를 쉽게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="fd9f4-139">단일 위치에 여러 다이얼 플랜이 필요한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="fd9f4-140">조직에서 여러 위치에 걸친 단일 다이얼 플랜을 유지 관리 하는 경우에도, PBX (개인 브랜치 교환)에서 마이그레이션하는 Enterprise Voice 사용자를 위한 별도의 다이얼 플랜을 만들어야 하며, 기존 확장을 보존 해야 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="fd9f4-141">사용자 단위 다이얼 플랜이 필요한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="fd9f4-142">예를 들어 중앙 사이트를 사용 하 여 등록 한 지점 사이트에 사용자가 있거나 Survivable Branch 기기에 등록 된 사용자가 있는 경우, 사용자에 대 한 다이얼 플랜 및 정규화 규칙을 사용 하 여 해당 사용자에 대 한 특별 한 전화 접속 시나리오를 고려할 수 있습니다. .</span><span class="sxs-lookup"><span data-stu-id="fd9f4-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="fd9f4-143">자세한 내용은 [Lync Server 2013에 대 한 지점 사이트 복원 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="fd9f4-144">다이얼 플랜 범위 결정 (이 항목의 이전 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="fd9f4-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="fd9f4-145">다이얼 플랜을 만들려면 필요에 따라 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 다음 필드에 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="fd9f4-146">이름 및 단순한 이름</span><span class="sxs-lookup"><span data-stu-id="fd9f4-146">Name and Simple Name</span></span>

<span data-ttu-id="fd9f4-147">사용자 다이얼 플랜의 경우 다이얼 플랜이 할당 되는 사용자, 그룹 또는 연락처 개체를 식별 하는 설명적인 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="fd9f4-148">사이트 다이얼 플랜의 경우 이름 필드는 사이트 이름으로 미리 채워져 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="fd9f4-149">풀 다이얼 플랜의 경우 이름 필드는 PSTN 게이트웨이 또는 프론트 엔드 풀 정규화 된 도메인 이름 (FQDN)으로 미리 채워 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="fd9f4-150">다이얼 플랜의 *단순한 이름* 에는 다이얼 플랜 이름에서 파생 된 문자열이 미리 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="fd9f4-151">간단한 이름 필드는 편집 가능 하며,이를 통해 다이얼 플랜에 대 한 보다 설명적인 명명 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="fd9f4-152">*간단한 이름* 값은 비워 둘 수 없으며 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="fd9f4-153">전체 조직의 명명 규칙을 개발한 다음 모든 사이트와 사용자에 게 일관 되 게이 규칙을 사용 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="fd9f4-154">설명</span><span class="sxs-lookup"><span data-stu-id="fd9f4-154">Description</span></span>

<span data-ttu-id="fd9f4-155">해당 다이얼 플랜이 적용 되는 지리적 위치에 대해 인식할 수 있는 일반적인 이름을 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-155">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies.</span></span> <span data-ttu-id="fd9f4-156">예를 들어 다이얼 플랜 이름이 London.Contoso.com 경우 권장 설명은 London입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-156">For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="fd9f4-157">전화 접속 회의 지역</span><span class="sxs-lookup"><span data-stu-id="fd9f4-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="fd9f4-158">전화 접속 회의를 배포 하는 경우 다이얼 인 회의 액세스 번호를 다이얼 플랜에 연결 하려면 전화 접속 회의 지역을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="fd9f4-159">외부 액세스 접두사</span><span class="sxs-lookup"><span data-stu-id="fd9f4-159">External Access Prefix</span></span>

<span data-ttu-id="fd9f4-160">외부 회선을 얻으려면 사용자가 하나 이상의 추가 선행 번호 (예\#: \*9)로 전화를 걸어야 하는 경우 최대 4 자 (,, 0-9)로 외부 액세스 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd9f4-161">외부 액세스 접두사를 지정 하는 경우 접두사를 수용할 수 있는 추가 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="fd9f4-162">정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="fd9f4-162">Normalization Rules</span></span>

<span data-ttu-id="fd9f4-163">정규화 규칙은 다양 한 형식으로 표시 되는 전화 번호가 명명 된 위치에 대해 라우팅되는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-163">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="fd9f4-164">같은 숫자 문자열은이를 거는 로케일에 따라 다르게 해석 하 고 번역할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-164">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="fd9f4-165">사용자는 연락처 목록에 전화 번호를 입력할 때 다양 한 형식을 사용할 수 있기 때문에 통화 라우팅에 정규화 규칙이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-165">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="fd9f4-166">사용자 제공 전화 번호 정규화는 다음 작업을 용이 하 게 하는 일관 된 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="fd9f4-167">전화를 받는 사람의 SIP URI와 번호를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="fd9f4-168">전화 건이에 대 한 권한 부여 규칙을 통화 파티에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="fd9f4-169">다음 번호 필드는 정규화 규칙에서 고려해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="fd9f4-170">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="fd9f4-170">Dial plan</span></span>

  - <span data-ttu-id="fd9f4-171">국가 코드</span><span class="sxs-lookup"><span data-stu-id="fd9f4-171">Country code</span></span>

  - <span data-ttu-id="fd9f4-172">지역 번호</span><span class="sxs-lookup"><span data-stu-id="fd9f4-172">Area code</span></span>

  - <span data-ttu-id="fd9f4-173">확장 길이</span><span class="sxs-lookup"><span data-stu-id="fd9f4-173">Length of extension</span></span>

  - <span data-ttu-id="fd9f4-174">사이트 접두사</span><span class="sxs-lookup"><span data-stu-id="fd9f4-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="fd9f4-175">정규화 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="fd9f4-175">Creating Normalization Rules</span></span>

<span data-ttu-id="fd9f4-176">정규화 규칙에서는 검색 문자열을 변환 하는 데 사용 되는 숫자 일치 패턴을 지정 하기 위해 서버에서 역방향 번호 조회를 수행 하기 위한 목적으로이 정규식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="fd9f4-177">수동으로 식을 입력 하거나, 일치 시킬 다이얼 문자열의 시작 숫자와 길이를 입력 하 여 Lync Server 제어판에서 정규화 규칙을 만들 수 있습니다. 사용자에 게 정규식을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="fd9f4-178">두 방법 중 하나를 마치면 테스트 번호를 입력 하 여 정규화 규칙이 예상 대로 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="fd9f4-179">.NET Framework 정규식을 사용 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net framework 정규식"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="fd9f4-180">예제 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="fd9f4-180">Sample Normalization Rules</span></span>

<span data-ttu-id="fd9f4-181">다음 표에는 .NET Framework 정규식으로 작성 된 예제 정규화 규칙이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-181">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="fd9f4-182">샘플은 예일 뿐 이며 고유한 정규화 규칙을 만들기 위한 규범적 참조 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-182">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="fd9f4-183">표 1. .NET Framework 정규식을 사용 하는 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="fd9f4-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd9f4-184">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="fd9f4-184">Rule name</span></span></th>
<th><span data-ttu-id="fd9f4-185">설명</span><span class="sxs-lookup"><span data-stu-id="fd9f4-185">Description</span></span></th>
<th><span data-ttu-id="fd9f4-186">번호 패턴</span><span class="sxs-lookup"><span data-stu-id="fd9f4-186">Number pattern</span></span></th>
<th><span data-ttu-id="fd9f4-187">변환용</span><span class="sxs-lookup"><span data-stu-id="fd9f4-187">Translation</span></span></th>
<th><span data-ttu-id="fd9f4-188">예</span><span class="sxs-lookup"><span data-stu-id="fd9f4-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="fd9f4-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-190">4 자리 확장을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-192">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-193">0100는 + 14255550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="fd9f4-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-195">다섯 자리 확장명 변환</span><span class="sxs-lookup"><span data-stu-id="fd9f4-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-197">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-198">50100는 + 14255550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="fd9f4-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-200">7 자리 숫자를 Redmond 지역 번호로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-202">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-203">5550100는 + 14255550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="fd9f4-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-205">7 자리 숫자를 달라스 지역 번호로 변환</span><span class="sxs-lookup"><span data-stu-id="fd9f4-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-207">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-208">5550100는 + 19725550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="fd9f4-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-210">미국에서 10 자리 숫자를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-212">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-213">2065550100는 + 12065550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="fd9f4-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-215">미국에서 시외 접두 번호를 사용 하 여 숫자를 번역 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-218">12145550100는 + 2145550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-219">소개</span><span class="sxs-lookup"><span data-stu-id="fd9f4-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-220">미국에서 국제 접두 번호로 번호를 번역 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-221">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-223">01191445550100는 + 91445550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="fd9f4-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-225">0에서 레드먼드 연산자로 변환</span><span class="sxs-lookup"><span data-stu-id="fd9f4-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-226">^ $0</span><span class="sxs-lookup"><span data-stu-id="fd9f4-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-227">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="fd9f4-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-228">0이 + 14255550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fd9f4-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-230">A-net 접두사 (6) 및 Redmond 사이트 코드 (222)를 사용 하 여 숫자를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-232">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-233">62220100는 + 14255550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fd9f4-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-235">순 접두 (6) 및 (333) 전화 번호를 사용 하 여 숫자를 번역 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-237">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-238">63330100는 + 12025550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fd9f4-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-240">A-net 접두사 (6) 및 달라스 사이트 코드 (444)를 사용 하 여 숫자를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fd9f4-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-242">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="fd9f4-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="fd9f4-243">64440100는 + 19725550100로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd9f4-244">다음 표에서는 이전 표에 표시 된 표준화 규칙에 따라 Redmond, 인천, 미국에 대 한 예제 다이얼 플랜을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="fd9f4-245">표 2.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-245">Table 2.</span></span> <span data-ttu-id="fd9f4-246">표 1에 표시 된 정규화 규칙을 기반으로 하는 Redmond 다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="fd9f4-246">Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd9f4-247">Redmond forestFQDN</span><span class="sxs-lookup"><span data-stu-id="fd9f4-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="fd9f4-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="fd9f4-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="fd9f4-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-251">소개</span><span class="sxs-lookup"><span data-stu-id="fd9f4-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fd9f4-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fd9f4-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd9f4-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fd9f4-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd9f4-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="fd9f4-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fd9f4-256">앞의 표에 나와 있는 정규화 규칙 이름에는 공백이 포함 되지 않지만, 선택 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-256">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="fd9f4-257">예를 들어 표의 이름에는 "5 자리 내선" 또는 "5 자리 내선 번호"가 기록 되 고 여전히 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9f4-257">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

