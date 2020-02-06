---
title: 비즈니스용 Skype 서버의 스키마 변경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 비즈니스용 Skype 서버를 배포 하 고 작동 하기 전에 스키마를 확장 하 여 Active Directory 도메인 서비스를 준비 해야 합니다. 스키마 확장에서는 비즈니스용 Skype 서버에서 요구 하는 클래스 및 특성을 추가 합니다.
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815486"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="7ca31-104">비즈니스용 Skype 서버의 스키마 변경</span><span class="sxs-lookup"><span data-stu-id="7ca31-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="7ca31-105">비즈니스용 Skype 서버를 배포 하 고 작동 하기 전에 스키마를 확장 하 여 Active Directory 도메인 서비스를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="7ca31-106">스키마 확장에서는 비즈니스용 Skype 서버에서 요구 하는 클래스 및 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="7ca31-107">Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하는 경우 스키마가 변경 되지 않으므로이 문서는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="7ca31-108">비즈니스용 Skype 서버에는 몇 가지 새로운 클래스 및 특성이 필요 하며 일부 기존 클래스 및 특성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="7ca31-109">또한 비즈니스용 Skype Server에 대 한 많은 구성 정보는 이전 버전 에서처럼 AD DS 대신 중앙 관리 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="7ca31-110">다음 정보는 여전히 비즈니스용 Skype 서버의 AD DS에 저장 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="7ca31-111">**스키마 확장**:</span><span class="sxs-lookup"><span data-stu-id="7ca31-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="7ca31-112">사용자 개체 확장</span><span class="sxs-lookup"><span data-stu-id="7ca31-112">User object extensions</span></span>
    
  - <span data-ttu-id="7ca31-113">지원 되는 이전 버전의 Lync Server와의 호환성을 유지 하는 클래스에 대 한 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="7ca31-114">**데이터** (비즈니스용 Skype Server 확장 스키마 및 기존 스키마 클래스에 저장 됨):</span><span class="sxs-lookup"><span data-stu-id="7ca31-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="7ca31-115">사용자 SIP URI (Uniform Resource Identifier) 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="7ca31-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="7ca31-116">응답 그룹 및 회의 수행자와 같은 응용 프로그램에 대 한 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="7ca31-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="7ca31-117">중앙 관리 저장소에 대 한 포인터</span><span class="sxs-lookup"><span data-stu-id="7ca31-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="7ca31-118">Kerberos 인증 계정 (선택적 컴퓨터 개체)</span><span class="sxs-lookup"><span data-stu-id="7ca31-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="7ca31-119">이 항목에서는 비즈니스용 Skype Server에 필요한 Active Directory 스키마 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="7ca31-120">이전 버전의 Office Communications Server에서 도입 된 스키마 변경은 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="7ca31-121">수업 목록과 해당 설명은 [비즈니스용 Skype 서버의 스키마 클래스 및 설명을](schema-classes-and-descriptions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca31-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="7ca31-122">특성 및 설명 목록은 [비즈니스용 Skype 서버의 스키마 특성 및 설명을](schema-attributes-and-descriptions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca31-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="7ca31-123">포함 될 수 있는 특성을 가진 클래스 목록은 [비즈니스용 Skype 서버에서 클래스별 스키마 특성](schema-attributes-by-class.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ca31-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="7ca31-124">MsRTCSIP 접두사는 비즈니스용 Skype 서버와 관련 된 클래스 및 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="7ca31-125">새 Active Directory 특성</span><span class="sxs-lookup"><span data-stu-id="7ca31-125">New Active Directory Attributes</span></span>

<span data-ttu-id="7ca31-126">다음 표에서는 비즈니스용 Skype 서버에 추가 된 Active Directory 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="7ca31-127">**비즈니스용 Skype 서버에 의해 추가 된 특성**</span><span class="sxs-lookup"><span data-stu-id="7ca31-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="7ca31-128">**특성**</span><span class="sxs-lookup"><span data-stu-id="7ca31-128">**Attribute**</span></span>|<span data-ttu-id="7ca31-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="7ca31-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7ca31-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="7ca31-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="7ca31-131">이 다중 값 특성에는 사용자에 게 적용 되는 보류 정책에 대 한 식별자가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="7ca31-132">보존 정책은 보류 기간 동안 사용자의 사서함 항목을 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="7ca31-133">이 특성은 Exchange 2013와 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="7ca31-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="7ca31-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="7ca31-135">SIP 라우팅 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="7ca31-136">같은 그룹의 사용자가 동일한 프런트 엔드 서버에 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="7ca31-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="7ca31-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="7ca31-138">이 특성은 프런트 엔드 풀에 사용 되는 미러된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="7ca31-139">수정 된 Active Directory 클래스</span><span class="sxs-lookup"><span data-stu-id="7ca31-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="7ca31-140">다음 표에서는 비즈니스용 Skype 서버에서 수정 된 Active Directory 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca31-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="7ca31-141">**비즈니스용 Skype 서버에서 수정한 클래스**</span><span class="sxs-lookup"><span data-stu-id="7ca31-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="7ca31-142">**클래스만**</span><span class="sxs-lookup"><span data-stu-id="7ca31-142">**Class**</span></span>|<span data-ttu-id="7ca31-143">**바뀌지**</span><span class="sxs-lookup"><span data-stu-id="7ca31-143">**Change**</span></span>|<span data-ttu-id="7ca31-144">**클래스 또는 특성**</span><span class="sxs-lookup"><span data-stu-id="7ca31-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ca31-145">사용자</span><span class="sxs-lookup"><span data-stu-id="7ca31-145">User</span></span>  <br/> |<span data-ttu-id="7ca31-146">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="7ca31-146">add: mayContain</span></span>  <br/> <span data-ttu-id="7ca31-147">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="7ca31-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="7ca31-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7ca31-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="7ca31-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="7ca31-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="7ca31-150">Contact</span><span class="sxs-lookup"><span data-stu-id="7ca31-150">Contact</span></span>  <br/> |<span data-ttu-id="7ca31-151">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="7ca31-151">add: mayContain</span></span>  <br/> <span data-ttu-id="7ca31-152">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="7ca31-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="7ca31-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7ca31-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="7ca31-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="7ca31-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="7ca31-155">메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="7ca31-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="7ca31-156">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="7ca31-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="7ca31-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="7ca31-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="7ca31-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="7ca31-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="7ca31-159">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="7ca31-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="7ca31-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="7ca31-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

