---
title: 비즈니스용 Skype 서버의 Schema 변경 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 비즈니스용 Skype 서버를 배포 및 운영하기 전에 해당 스마마를 확장하여 Active Directory 도메인 서비스를 준비해야 합니다. 이 확장은 비즈니스용 Skype 서버에 필요한 클래스 및 특성을 추가합니다.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813578"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="a514b-104">비즈니스용 Skype 서버의 Schema 변경 사항</span><span class="sxs-lookup"><span data-stu-id="a514b-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="a514b-105">비즈니스용 Skype 서버를 배포 및 운영하기 전에 해당 스마마를 확장하여 Active Directory 도메인 서비스를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="a514b-106">이 확장은 비즈니스용 Skype 서버에 필요한 클래스 및 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="a514b-107">Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드하는 경우 이러한 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="a514b-108">비즈니스용 Skype 서버에는 몇 가지 새로운 클래스 및 특성이 필요하며 일부 기존 클래스 및 특성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="a514b-109">또한 비즈니스용 Skype 서버에 대한 많은 구성 정보는 이전 버전과 같은 AD DS 대신 중앙 관리 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="a514b-110">다음 정보는 여전히 비즈니스용 Skype 서버의 AD DS에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="a514b-111">**스키마 확장**:</span><span class="sxs-lookup"><span data-stu-id="a514b-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="a514b-112">사용자 개체 확장</span><span class="sxs-lookup"><span data-stu-id="a514b-112">User object extensions</span></span>
    
  - <span data-ttu-id="a514b-113">지원되는 이전 버전 Lync Server와의 호환성을 유지하기 위한 클래스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="a514b-114">**데이터(비즈니스용** Skype 서버 확장된 스마마 및 기존 schema 클래스에 저장됨):</span><span class="sxs-lookup"><span data-stu-id="a514b-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="a514b-115">사용자 SIP URI(Uniform Resource Identifier) 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="a514b-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="a514b-116">응답 그룹 및 회의 길잡이 등과 같은 응용 프로그램에 대한 대화 상대 개체</span><span class="sxs-lookup"><span data-stu-id="a514b-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="a514b-117">중앙 관리 저장소에 대한 포인터</span><span class="sxs-lookup"><span data-stu-id="a514b-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="a514b-118">Kerberos 인증 계정(선택적 컴퓨터 개체)</span><span class="sxs-lookup"><span data-stu-id="a514b-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="a514b-119">이 항목에서는 비즈니스용 Skype 서버에서 요구하는 Active Directory의 변경 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="a514b-120">이전 버전의 Office Communications Server에서 도입된 계획 변경 내용은 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="a514b-121">클래스 및 해당 설명 목록은 비즈니스용 Skype 서버의 Schema 클래스 및 [설명을 참조하세요.](schema-classes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="a514b-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="a514b-122">특성 및 해당 설명 목록은 비즈니스용 Skype 서버의 Schema 특성 및 [설명을 참조하세요.](schema-attributes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="a514b-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="a514b-123">포함할 수 있는 특성이 있는 클래스 목록은 비즈니스용 Skype 서버의 클래스에 따라 [Schema 특성을 참조하세요.](schema-attributes-by-class.md)</span><span class="sxs-lookup"><span data-stu-id="a514b-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="a514b-124">msRTCSIP prefix는 비즈니스용 Skype 서버와 관련이 있는 클래스 및 특성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="a514b-125">새 Active Directory 특성</span><span class="sxs-lookup"><span data-stu-id="a514b-125">New Active Directory Attributes</span></span>

<span data-ttu-id="a514b-126">다음 표에서는 비즈니스용 Skype 서버에서 추가한 Active Directory 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="a514b-127">**비즈니스용 Skype 서버에서 추가된 특성**</span><span class="sxs-lookup"><span data-stu-id="a514b-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="a514b-128">**특성**</span><span class="sxs-lookup"><span data-stu-id="a514b-128">**Attribute**</span></span>|<span data-ttu-id="a514b-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="a514b-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a514b-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a514b-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="a514b-131">이 다중값 특성은 사용자에 적용되는 유지 정책의 ID를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="a514b-132">유지 정책은 유지 기간 동안 사용자의 사서함 항목을 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="a514b-133">이 특성은 Exchange 2013과 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="a514b-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a514b-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="a514b-p106">이는 SIP 라우팅 그룹 ID입니다. 동일한 그룹의 사용자는 동일한 프런트 엔드 서버에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-p106">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="a514b-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a514b-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="a514b-138">이 특성은 프런트 엔드 풀에서 SQL Server 미러된 백 엔드를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="a514b-139">수정된 Active Directory 클래스</span><span class="sxs-lookup"><span data-stu-id="a514b-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="a514b-140">다음 표에서는 비즈니스용 Skype 서버에서 수정한 Active Directory 클래스에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a514b-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="a514b-141">**비즈니스용 Skype 서버에서 수정된 클래스**</span><span class="sxs-lookup"><span data-stu-id="a514b-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="a514b-142">**클래스**</span><span class="sxs-lookup"><span data-stu-id="a514b-142">**Class**</span></span>|<span data-ttu-id="a514b-143">**변경 사항**</span><span class="sxs-lookup"><span data-stu-id="a514b-143">**Change**</span></span>|<span data-ttu-id="a514b-144">**클래스 또는 특성**</span><span class="sxs-lookup"><span data-stu-id="a514b-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a514b-145">사용자</span><span class="sxs-lookup"><span data-stu-id="a514b-145">User</span></span>  <br/> |<span data-ttu-id="a514b-146">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="a514b-146">add: mayContain</span></span>  <br/> <span data-ttu-id="a514b-147">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="a514b-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="a514b-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a514b-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="a514b-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a514b-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="a514b-150">담당자</span><span class="sxs-lookup"><span data-stu-id="a514b-150">Contact</span></span>  <br/> |<span data-ttu-id="a514b-151">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="a514b-151">add: mayContain</span></span>  <br/> <span data-ttu-id="a514b-152">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="a514b-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="a514b-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a514b-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="a514b-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a514b-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="a514b-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="a514b-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="a514b-156">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="a514b-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="a514b-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a514b-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="a514b-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="a514b-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="a514b-159">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="a514b-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="a514b-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a514b-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

