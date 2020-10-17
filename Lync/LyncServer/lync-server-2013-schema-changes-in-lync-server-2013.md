---
title: 'Lync Server 2013: Lync Server 2013의 스키마 변경 사항'
description: 'Lync Server 2013: Lync Server 2013에서 스키마가 변경 되었습니다.'
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
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557154"
---
# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="9217f-103">Lync Server 2013의 스키마 변경 내용</span><span class="sxs-lookup"><span data-stu-id="9217f-103">Schema changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9217f-104">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9217f-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9217f-105">Lync Server 2013를 배포 하 고 작동 하기 전에 스키마를 확장 하 여 Active Directory 도메인 서비스를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-105">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="9217f-106">스키마 확장은 Lync Server 2013에 필요한 클래스 및 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-106">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="9217f-107">Lync Server 2013에는 몇 가지 새 클래스와 특성이 필요 하며 일부 기존 클래스 및 특성을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-107">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="9217f-108">또한 Lync Server 2013에 대 한 많은 구성 정보는 이전 버전과 같이 AD DS가 아닌 중앙 관리 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-108">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="9217f-109">다음 정보는 여전히 Lync Server 2013의 AD DS에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-109">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="9217f-110">**스키마 확장**:</span><span class="sxs-lookup"><span data-stu-id="9217f-110">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="9217f-111">사용자 개체 확장</span><span class="sxs-lookup"><span data-stu-id="9217f-111">User object extensions</span></span>
    
      - <span data-ttu-id="9217f-112">지원 되는 이전 버전과의 이전 버전과의 호환성을 유지 하기 위해 Office Communications Server 2007 및 Office Communications Server 2007 R2 클래스에 대 한 확장</span><span class="sxs-lookup"><span data-stu-id="9217f-112">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="9217f-113">**데이터** (Lync Server 확장 스키마 및 기존 스키마 클래스에 저장):</span><span class="sxs-lookup"><span data-stu-id="9217f-113">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="9217f-114">사용자 SIP URI(Uniform Resource Identifier) 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="9217f-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="9217f-115">응답 그룹 및 회의 길잡이 등과 같은 응용 프로그램에 대한 대화 상대 개체</span><span class="sxs-lookup"><span data-stu-id="9217f-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="9217f-116">중앙 관리 저장소에 대한 포인터</span><span class="sxs-lookup"><span data-stu-id="9217f-116">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="9217f-117">Kerberos 인증 계정(선택적 컴퓨터 개체)</span><span class="sxs-lookup"><span data-stu-id="9217f-117">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="9217f-118">이 항목에서는 Lync Server 2013에서 요구 하는 Active Directory 스키마 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-118">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="9217f-119">이전 버전의 Office Communications Server에서 도입 되었던 스키마 변경 내용은 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="9217f-120">클래스 목록과 해당 설명에 대 한 자세한 내용은 [Lync Server 2013의 스키마 클래스 및 설명을](lync-server-2013-schema-classes-and-descriptions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9217f-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="9217f-121">특성 목록과 해당 설명에 대 한 자세한 내용은 [Lync Server 2013의 스키마 특성 및 설명을](lync-server-2013-schema-attributes-and-descriptions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9217f-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="9217f-122">여기에 포함 될 수 있는 특성을 가진 클래스 목록은 [Lync Server 2013에서 클래스별 스키마 특성](lync-server-2013-schema-attributes-by-class.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9217f-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="9217f-123">Msrtcsip-gateways 접두사는 Lync Server와 관련 된 클래스 및 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-123">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="9217f-124">새 Active Directory 특성</span><span class="sxs-lookup"><span data-stu-id="9217f-124">New Active Directory Attributes</span></span>

<span data-ttu-id="9217f-125">다음 표에서는 Lync Server 2013에서 추가 하는 Active Directory 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-125">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="9217f-126">Lync Server 2013에서 추가 된 특성</span><span class="sxs-lookup"><span data-stu-id="9217f-126">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9217f-127">특성</span><span class="sxs-lookup"><span data-stu-id="9217f-127">Attribute</span></span></th>
<th><span data-ttu-id="9217f-128">설명</span><span class="sxs-lookup"><span data-stu-id="9217f-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9217f-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="9217f-129">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="9217f-130">이 다중값 특성은 사용자에 적용되는 유지 정책의 ID를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="9217f-131">유지 정책은 유지 기간 동안 사용자의 사서함 항목을 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="9217f-132">이 특성은 Exchange 2013와 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-132">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9217f-133">Msrtcsip-gateways-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="9217f-133">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="9217f-p105">이는 SIP 라우팅 그룹 ID입니다. 동일한 그룹의 사용자는 동일한 프런트 엔드 서버에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9217f-136">Msrtcsip-gateways-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="9217f-136">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="9217f-137">이 특성은 프런트 엔드 풀에서 사용 하는 미러링된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="9217f-138">수정된 Active Directory 클래스</span><span class="sxs-lookup"><span data-stu-id="9217f-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="9217f-139">다음 표에서는 Lync Server 2013에서 수정 된 Active Directory 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9217f-139">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="9217f-140">Lync Server 2013에서 수정 된 클래스</span><span class="sxs-lookup"><span data-stu-id="9217f-140">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9217f-141">클래스</span><span class="sxs-lookup"><span data-stu-id="9217f-141">Class</span></span></th>
<th><span data-ttu-id="9217f-142">변경 사항</span><span class="sxs-lookup"><span data-stu-id="9217f-142">Change</span></span></th>
<th><span data-ttu-id="9217f-143">클래스 또는 특성</span><span class="sxs-lookup"><span data-stu-id="9217f-143">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9217f-144">사용자</span><span class="sxs-lookup"><span data-stu-id="9217f-144">User</span></span></p></td>
<td><p><span data-ttu-id="9217f-145">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="9217f-145">add: mayContain</span></span></p>
<p><span data-ttu-id="9217f-146">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="9217f-146">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="9217f-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9217f-147">ProxyAddresses</span></span></p>
<p><span data-ttu-id="9217f-148">Msrtcsip-gateways-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="9217f-148">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9217f-149">담당자</span><span class="sxs-lookup"><span data-stu-id="9217f-149">Contact</span></span></p></td>
<td><p><span data-ttu-id="9217f-150">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="9217f-150">add: mayContain</span></span></p>
<p><span data-ttu-id="9217f-151">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="9217f-151">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="9217f-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9217f-152">ProxyAddresses</span></span></p>
<p><span data-ttu-id="9217f-153">Msrtcsip-gateways-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="9217f-153">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9217f-154">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="9217f-154">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="9217f-155">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="9217f-155">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="9217f-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="9217f-156">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9217f-157">Msrtcsip-gateways-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="9217f-157">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="9217f-158">추가: mayContain</span><span class="sxs-lookup"><span data-stu-id="9217f-158">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="9217f-159">Msrtcsip-gateways-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="9217f-159">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

