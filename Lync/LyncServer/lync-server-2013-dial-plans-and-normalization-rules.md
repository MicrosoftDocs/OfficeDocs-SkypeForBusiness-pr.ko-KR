---
title: 'Lync Server 2013: 다이얼 플랜 및 정규화 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adcd2cd6bebfb0797427d15819399c9b2b9f86d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="07f1f-102">Lync Server 2013의 다이얼 플랜 및 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="07f1f-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07f1f-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="07f1f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="07f1f-104">다이얼 플랜은 전화 인증 및 통화 라우팅을 위해 명명된 위치, 개별 사용자 또는 연락처 개체의 전화 번호를 하나의 표준(E.164) 형식으로 변환하는 명명된 정규화 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="07f1f-105">정규화 규칙은 다양한 형식으로 표현된 전화 번호를 지정된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-105">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="07f1f-106">전화를 거는 위치와 통화를 수행 하는 사람 또는 대화 상대 개체에 따라 같은 다이얼 문자열이 다르게 해석 되 고 변환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-106">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="07f1f-107">다이얼 플랜 범위</span><span class="sxs-lookup"><span data-stu-id="07f1f-107">Dial Plan Scope</span></span>

<span data-ttu-id="07f1f-108">다이얼 플랜의 *범위*는 다이얼 플랜을 적용할 수 있는 계층 수준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="07f1f-109">Lync Server에서는 사용자에 게 특정 사용자별 다이얼 플랜을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="07f1f-110">사용자 다이얼 플랜이 할당되지 않으면 등록자 풀 다이얼 플랜이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="07f1f-111">등록자 풀 다이얼 플랜이 없는 경우 사이트 다이얼 플랜이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="07f1f-112">마지막으로 사용자에게 적용되는 다른 다이얼 플랜이 없는 경우 전역 다이얼 플랜이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="07f1f-113">클라이언트는 사용자가 Lync Server에 로그온 할 때 제공 되는 대역내 프로 비전 설정을 통해 다이얼 플랜 범위 수준을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="07f1f-114">관리자는 Lync Server 제어판을 사용 하 여 다이얼 플랜 범위 수준을 관리 하 고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07f1f-115">서비스 수준 PSTN (공중 전화망) 게이트웨이 다이얼 플랜은 특정 게이트웨이에서 들어오는 호출에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="07f1f-116">다이얼 플랜 범위 수준은 다음과 같이 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="07f1f-117">**사용자 다이얼 플랜:** 개별 사용자, 그룹 또는 연락처 개체에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="07f1f-118">음성 응용 프로그램은 전화 컨텍스트를 사용자 기본값으로 설정 하 여 통화가 수신 되는 경우 사용자별 다이얼 플랜을 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="07f1f-119">다이얼 플랜을 지정 하기 위해 연락처 개체가 개별 사용자로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="07f1f-120">**풀 다이얼 플랜:** 토폴로지의 모든 PSTN 게이트웨이 또는 등록자에 대 한 서비스 수준에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="07f1f-121">풀 다이얼 플랜을 정의하려면 다이얼 플랜을 적용할 특정 서비스(PSTN 게이트웨이 또는 등록자 풀)를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="07f1f-122">**사이트 다이얼 플랜:** 풀 다이얼 플랜 또는 사용자 다이얼 플랜이 할당 된 모든 사용자, 그룹 또는 연락처 개체를 제외 하 고 전체 사이트에 대해 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="07f1f-123">사이트 다이얼 플랜을 정의하려면 다이얼 플랜을 적용할 사이트를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="07f1f-124">**전역 다이얼 플랜:** 제품과 함께 설치 되는 기본 다이얼 플랜입니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="07f1f-125">전역 다이얼 플랜을 편집할 수 있지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="07f1f-126">이 다이얼 플랜은 더 구체적인 범위를 사용 하 여 다이얼 플랜을 구성 및 할당 하지 않는 한 배포의 모든 Enterprise Voice 사용자, 그룹 및 연락처 개체에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="07f1f-127">다이얼 플랜 계획</span><span class="sxs-lookup"><span data-stu-id="07f1f-127">Planning for Dial Plans</span></span>

<span data-ttu-id="07f1f-128">다이얼 플랜을 계획 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="07f1f-129">조직에 office가 있는 모든 로캘을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="07f1f-130">목록이 최신 상태이 고 완료 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-130">The list must be up-to-date and complete.</span></span> <span data-ttu-id="07f1f-131">또한 회사 조직이 발전함에 따라 목록도 수정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-131">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="07f1f-132">규모가 작은 다국적 대기업에서는 시간이 많이 소요 되는 작업이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-132">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="07f1f-133">각 사이트의 유효한 번호 패턴을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="07f1f-p109">다이얼 플랜 계획 중 가장 시간이 오래 걸리는 부분은 각 사이트에 유효한 숫자 패턴을 식별하는 것입니다. 경우에 따라, 특히 해당 사이트가 같은 국가/지역 또는 대륙 내에 있는 경우 한 다이얼 플랜에 대해 작성한 정규화 규칙을 다른 다이얼 플랜에 복사할 수 있습니다. 한 다이얼 플랜에서 번호를 조금만 변경해서 다른 다이얼 플랜에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="07f1f-137">다이얼 플랜을 명명 하기 위한 조직 차원의 구성표를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="07f1f-138">표준 명명 체계를 도입하면 조직 전체에서 일관성을 보장하고 유지 관리 및 업데이트를 더 수월하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="07f1f-139">단일 위치에 여러 다이얼 플랜이 필요한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="07f1f-140">조직에서 여러 위치에 대해 단일 다이얼 플랜을 유지 관리 하는 경우에도 PBX (private branch exchange)에서 마이그레이션하는 Enterprise Voice 사용자에 대해 별도의 다이얼 플랜을 만들고 기존 내선 번호를 보존 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="07f1f-141">사용자 단위 다이얼 플랜이 필요한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="07f1f-142">예를 들어 중앙 사이트에 등록 된 분기 사이트에 사용자가 있거나 Sba (survivable Branch 기기에 등록 된 사용자가 있는 경우 이러한 사용자에 대 한 특수 전화 걸기 시나리오를 사용 하 여 사용자별 다이얼 플랜 및 정규화 규칙을 고려할 수 있습니다. .</span><span class="sxs-lookup"><span data-stu-id="07f1f-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="07f1f-143">자세한 내용은 [Lync Server 2013에 대 한 분기 사이트 복구 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07f1f-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="07f1f-144">다이얼 플랜 범위 결정 (이 항목의 앞 부분에 설명 된 대로)</span><span class="sxs-lookup"><span data-stu-id="07f1f-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="07f1f-145">다이얼 플랜을 만들려면 필요에 따라 Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 다음 필드에 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="07f1f-146">이름 및 단순한 이름</span><span class="sxs-lookup"><span data-stu-id="07f1f-146">Name and Simple Name</span></span>

<span data-ttu-id="07f1f-147">사용자 다이얼 플랜의 경우 다이얼 플랜이 할당 되는 사용자, 그룹 또는 연락처 개체를 식별 하는 설명이 포함 된 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="07f1f-148">사이트 다이얼 플랜의 경우 이름 필드에 사이트 이름이 미리 채워지며 이는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="07f1f-149">풀 다이얼 플랜의 경우 이름 필드에 PSTN 게이트웨이 또는 프런트 엔드 풀 FQDN (정규화 된 도메인 이름)이 미리 채워져 있어 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="07f1f-150">다이얼 플랜 *단순한 이름*에는 다이얼 플랜 이름에서 파생된 문자열이 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="07f1f-151">간단한 이름 필드는 편집 가능 하며,이를 통해 다이얼 플랜에 대 한 보다 설명적인 명명 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="07f1f-152">*단순한 이름* 값은 비워 둘 수 없으며 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="07f1f-153">전체 조직에 대 한 명명 규칙을 개발한 다음 모든 사이트 및 사용자에 대해 일관 되 게이 규칙을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="07f1f-154">설명</span><span class="sxs-lookup"><span data-stu-id="07f1f-154">Description</span></span>

<span data-ttu-id="07f1f-p113">해당 다이얼 플랜이 적용되는 지역 위치에 대한 일반적이고 쉽게 알아볼 수 있는 이름을 입력하는 것이 좋습니다. 예를 들어 다이얼 플랜 이름이 London.Contoso.com이면 권장되는 설명은 런던입니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="07f1f-157">전화 접속 회의 지역</span><span class="sxs-lookup"><span data-stu-id="07f1f-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="07f1f-158">전화 접속 회의를 배포하는 경우 다이얼 플랜과 전화 접속 회의 액세스 번호를 연결할 전화 접속 회의 지역을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="07f1f-159">외부 액세스 접두사</span><span class="sxs-lookup"><span data-stu-id="07f1f-159">External Access Prefix</span></span>

<span data-ttu-id="07f1f-160">사용자가 하나 이상의 추가 선행 번호 (예: 9)를\#사용 \*하 여 외부 회선을 사용 해야 하는 경우 최대 4 자 (,, 0-9)의 외부 액세스 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07f1f-161">외부 액세스 접두사를 지정하면 접두사를 수용하기 위해 추가 정규화 규칙을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="07f1f-162">정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="07f1f-162">Normalization Rules</span></span>

<span data-ttu-id="07f1f-163">정규화 규칙은 다양한 형식으로 표현된 전화 번호를 명명된 위치에 대해 라우팅하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-163">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="07f1f-164">같은 숫자 문자열은 전화를 거는 로캘에 따라 다르게 해석 되 고 변환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-164">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="07f1f-165">사용자가 대화 상대 목록에 전화 번호를 입력할 때 여러 형식을 사용할 수 있고 또 사용하기 때문에 정규화 규칙은 통화 라우팅에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-165">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="07f1f-166">사용자가 제공한 전화 번호 정규화는 다음과 같은 작업을 용이 하 게 하는 일관 된 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="07f1f-167">전화 건 번호를 의도 한 받는 사람의 SIP URI와 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="07f1f-168">통화 당사자에 게 전화 걸기 권한 부여 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="07f1f-169">정규화 규칙에서 고려해야 하는 숫자 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="07f1f-170">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="07f1f-170">Dial plan</span></span>

  - <span data-ttu-id="07f1f-171">국가 번호</span><span class="sxs-lookup"><span data-stu-id="07f1f-171">Country code</span></span>

  - <span data-ttu-id="07f1f-172">지역 번호</span><span class="sxs-lookup"><span data-stu-id="07f1f-172">Area code</span></span>

  - <span data-ttu-id="07f1f-173">내선 번호 길이</span><span class="sxs-lookup"><span data-stu-id="07f1f-173">Length of extension</span></span>

  - <span data-ttu-id="07f1f-174">사이트 접두사</span><span class="sxs-lookup"><span data-stu-id="07f1f-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="07f1f-175">정규화 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="07f1f-175">Creating Normalization Rules</span></span>

<span data-ttu-id="07f1f-176">정규화 규칙은 .NET Framework 정규식을 사용하여 서버가 역방향 번호 조회를 수행하기 위해 전화 걸기 문자열을 E.164 형식으로 변환하는 데 사용하는 숫자 일치 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="07f1f-177">수동으로 식을 입력 하거나, 일치 시킬 전화 걸기 문자열의 길이를 입력 하 여 Lync Server 제어판에서 정규화 규칙을 만들거나, Lync Server 제어판에서 해당 사용자를 위한 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="07f1f-178">두 경우 모두 완료되면 테스트 번호를 입력하여 정규화 규칙이 예상대로 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="07f1f-179">.NET Framework 정규식 사용에 대 한 자세한 내용은의 ".NET Framework 정규식"을 참조 [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)하십시오.</span><span class="sxs-lookup"><span data-stu-id="07f1f-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="07f1f-180">샘플 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="07f1f-180">Sample Normalization Rules</span></span>

<span data-ttu-id="07f1f-p116">다음 표는 .NET Framework 정규식으로 작성된 샘플 정규화 규칙을 보여 줍니다. 샘플은 예로만 제공되며 정규화 규칙을 만드는 방법에 대한 규정은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="07f1f-183">표 1. .NET Framework 정규식을 사용한 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="07f1f-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="07f1f-184">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="07f1f-184">Rule name</span></span></th>
<th><span data-ttu-id="07f1f-185">설명</span><span class="sxs-lookup"><span data-stu-id="07f1f-185">Description</span></span></th>
<th><span data-ttu-id="07f1f-186">발신 제한</span><span class="sxs-lookup"><span data-stu-id="07f1f-186">Number pattern</span></span></th>
<th><span data-ttu-id="07f1f-187">Translation</span><span class="sxs-lookup"><span data-stu-id="07f1f-187">Translation</span></span></th>
<th><span data-ttu-id="07f1f-188">예제</span><span class="sxs-lookup"><span data-stu-id="07f1f-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="07f1f-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="07f1f-190">4자리 내선 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="07f1f-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-192">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-193">0100이 +14255550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-194">: 5Digitextension</span><span class="sxs-lookup"><span data-stu-id="07f1f-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="07f1f-195">5자리 내선 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="07f1f-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-197">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-198">50100이 +14255550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="07f1f-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="07f1f-200">7자리 번호를 레드몬드 지역 번호로 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="07f1f-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-202">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-203">5550100이 +14255550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="07f1f-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="07f1f-205">7자리 번호를 달라스 지역 번호로 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="07f1f-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-207">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-208">5550100이 +19725550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="07f1f-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="07f1f-210">미국 10자리 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="07f1f-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-212">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-213">2065550100이 +12065550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="07f1f-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="07f1f-215">미국 시외 접두사 포함 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="07f1f-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-218">12145550100이 +2145550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="07f1f-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="07f1f-220">미국 국가별 접두사 포함 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="07f1f-221">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-223">01191445550100이 +91445550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="07f1f-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="07f1f-225">0을 레드몬드 교환으로 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="07f1f-226">^ $0</span><span class="sxs-lookup"><span data-stu-id="07f1f-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-227">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="07f1f-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="07f1f-228">0이 +14255550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="07f1f-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="07f1f-230">온넷 접두사(6) 및 레드몬드 사이트 코드(222) 포함 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="07f1f-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-232">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-233">62220100이 +14255550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="07f1f-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="07f1f-235">온넷 접두사(6) 및 뉴욕 사이트 코드(333) 포함 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="07f1f-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-237">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-238">63330100이 +12025550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="07f1f-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="07f1f-240">온넷 접두사(6) 및 달라스 사이트 코드(444) 포함 번호 변환</span><span class="sxs-lookup"><span data-stu-id="07f1f-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="07f1f-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="07f1f-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="07f1f-242">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="07f1f-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="07f1f-243">64440100이 +19725550100으로 변환됨</span><span class="sxs-lookup"><span data-stu-id="07f1f-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07f1f-244">다음 표는 앞의 표에 나열된 정규화 규칙을 기반으로 미국 워싱턴주 레드몬드에 대한 샘플 다이얼 플랜을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="07f1f-p117">표 2. 표 1에 표시된 정규화 규칙에 기초한 레드몬드 다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="07f1f-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f1f-247">ForestFQDN</span><span class="sxs-lookup"><span data-stu-id="07f1f-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-248">: 5Digitextension</span><span class="sxs-lookup"><span data-stu-id="07f1f-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="07f1f-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="07f1f-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="07f1f-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="07f1f-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="07f1f-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f1f-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="07f1f-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f1f-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="07f1f-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="07f1f-p118">앞의 표에 나열된 정규화 규칙에는 공백이 포함되어 있지 않지만 이는 선택의 문제입니다. 예를 들어 표의 첫 번째 이름을 "5 digit extension" 또는 "5-digit Extension"으로 작성해도 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="07f1f-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

