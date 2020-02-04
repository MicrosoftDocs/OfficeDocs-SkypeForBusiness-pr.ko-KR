---
title: 'Lync Server 2013: Lync Server 2013에서 스키마 변경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a3fd5f18785a649803cc6f9a0a56d7b98a2ee6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="ed09f-102">Lync Server 2013의 스키마 변경 사항</span><span class="sxs-lookup"><span data-stu-id="ed09f-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed09f-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ed09f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ed09f-104">Lync Server 2013를 배포 하 고 작동 하기 전에 스키마를 확장 하 여 Active Directory 도메인 서비스를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="ed09f-105">스키마 확장에서는 Lync Server 2013에서 요구 하는 클래스 및 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="ed09f-106">Lync Server 2013에는 몇 가지 새로운 클래스 및 특성이 필요 하며 일부 기존 클래스 및 특성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="ed09f-107">또한 Lync Server 2013에 대 한 많은 구성 정보는 이전 버전 에서처럼 AD DS 대신 중앙 관리 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="ed09f-108">다음 정보는 여전히 Lync Server 2013의 AD DS에 저장 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="ed09f-109">**스키마 확장**:</span><span class="sxs-lookup"><span data-stu-id="ed09f-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="ed09f-110">사용자 개체 확장</span><span class="sxs-lookup"><span data-stu-id="ed09f-110">User object extensions</span></span>
    
      - <span data-ttu-id="ed09f-111">지원 되는 이전 버전과의 호환성을 유지 하기 위해 Office Communications Server 2007 및 Office Communications Server 2007 R2 클래스의 확장</span><span class="sxs-lookup"><span data-stu-id="ed09f-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="ed09f-112">**데이터** (Lync Server 확장 스키마 및 기존 스키마 클래스에 저장 됨):</span><span class="sxs-lookup"><span data-stu-id="ed09f-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="ed09f-113">사용자 SIP URI (Uniform Resource Identifier) 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="ed09f-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="ed09f-114">응답 그룹 및 회의 수행자와 같은 응용 프로그램에 대 한 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="ed09f-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="ed09f-115">중앙 관리 저장소에 대 한 포인터</span><span class="sxs-lookup"><span data-stu-id="ed09f-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="ed09f-116">Kerberos 인증 계정 (선택적 컴퓨터 개체)</span><span class="sxs-lookup"><span data-stu-id="ed09f-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="ed09f-117">이 항목에서는 Lync Server 2013에 필요한 Active Directory 스키마 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="ed09f-118">이전 버전의 Office Communications Server에서 도입 된 스키마 변경은 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="ed09f-119">수업 목록과 해당 설명은 [Lync Server 2013의 스키마 클래스 및 설명을](lync-server-2013-schema-classes-and-descriptions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed09f-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="ed09f-120">특성 및 설명 목록은 [Lync Server 2013의 스키마 특성 및 설명을](lync-server-2013-schema-attributes-and-descriptions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed09f-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="ed09f-121">포함 될 수 있는 특성을 가진 클래스 목록은 [Lync Server 2013에서 클래스별 스키마 특성](lync-server-2013-schema-attributes-by-class.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed09f-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="ed09f-122">MsRTCSIP 접두사는 Lync Server와 관련 된 클래스 및 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="ed09f-123">새 Active Directory 특성</span><span class="sxs-lookup"><span data-stu-id="ed09f-123">New Active Directory Attributes</span></span>

<span data-ttu-id="ed09f-124">다음 표에서는 Lync Server 2013에서 추가 된 Active Directory 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="ed09f-125">Lync Server 2013에서 추가한 특성</span><span class="sxs-lookup"><span data-stu-id="ed09f-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed09f-126">특성</span><span class="sxs-lookup"><span data-stu-id="ed09f-126">Attribute</span></span></th>
<th><span data-ttu-id="ed09f-127">설명</span><span class="sxs-lookup"><span data-stu-id="ed09f-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed09f-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ed09f-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="ed09f-129">이 다중 값 특성에는 사용자에 게 적용 되는 보류 정책에 대 한 식별자가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="ed09f-130">보존 정책은 보류 기간 동안 사용자의 사서함 항목을 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="ed09f-131">이 특성은 Exchange 2013와 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed09f-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ed09f-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="ed09f-133">SIP 라우팅 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="ed09f-134">같은 그룹의 사용자가 동일한 프런트 엔드 서버에 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed09f-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="ed09f-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="ed09f-136">이 특성은 프런트 엔드 풀에 사용 되는 미러된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="ed09f-137">수정 된 Active Directory 클래스</span><span class="sxs-lookup"><span data-stu-id="ed09f-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="ed09f-138">다음 표에서는 Lync Server 2013에서 수정 된 Active Directory 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed09f-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="ed09f-139">Lync Server 2013에서 수정한 클래스</span><span class="sxs-lookup"><span data-stu-id="ed09f-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed09f-140">클래스만</span><span class="sxs-lookup"><span data-stu-id="ed09f-140">Class</span></span></th>
<th><span data-ttu-id="ed09f-141">바뀌지</span><span class="sxs-lookup"><span data-stu-id="ed09f-141">Change</span></span></th>
<th><span data-ttu-id="ed09f-142">클래스 또는 특성</span><span class="sxs-lookup"><span data-stu-id="ed09f-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed09f-143">사용자</span><span class="sxs-lookup"><span data-stu-id="ed09f-143">User</span></span></p></td>
<td><p><span data-ttu-id="ed09f-144">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="ed09f-144">add: mayContain</span></span></p>
<p><span data-ttu-id="ed09f-145">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="ed09f-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="ed09f-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ed09f-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="ed09f-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ed09f-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed09f-148">Contact</span><span class="sxs-lookup"><span data-stu-id="ed09f-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="ed09f-149">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="ed09f-149">add: mayContain</span></span></p>
<p><span data-ttu-id="ed09f-150">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="ed09f-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="ed09f-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ed09f-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="ed09f-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ed09f-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed09f-153">메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="ed09f-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="ed09f-154">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="ed09f-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="ed09f-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ed09f-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed09f-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="ed09f-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="ed09f-157">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="ed09f-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="ed09f-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="ed09f-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

