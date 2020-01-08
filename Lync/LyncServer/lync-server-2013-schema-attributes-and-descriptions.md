---
title: 'Lync Server 2013: 스키마 특성 및 설명'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="80ed0-102">Lync Server 2013의 스키마 특성 및 설명</span><span class="sxs-lookup"><span data-stu-id="80ed0-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80ed0-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="80ed0-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="80ed0-104">이 섹션에서는 Lync Server 2013에서 사용 되는 모든 스키마 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="80ed0-105">특성과 관련 된 클래스의 경우 [Lync Server 2013에서 클래스별 스키마 특성](lync-server-2013-schema-attributes-by-class.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80ed0-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="80ed0-106">Lync Server 2013의 새로운 클래스 및 특성 목록은 [Lync server 2013의 스키마 변경을](lync-server-2013-schema-changes-in-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80ed0-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="80ed0-107">연결 된 쌍의 특성은 전방 링크 또는 뒤로 링크로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="80ed0-108">다른 개체를 참조 하는 특성은 전방 링크입니다. 첫 번째 개체를 다시 참조 하는 다른 개체의 특성은 뒤로 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="80ed0-109">전방 링크는 업데이트할 수 있으며, 역방향 링크는 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="80ed0-110">일부 특성에는 비트 마스크 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="80ed0-111">이러한 특성의 경우 각 설정이 비트로 표시 되 고 표시 되는 10 진수 값이 비트 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="80ed0-112">비트 위치는 비트 0으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="80ed0-113">예를 들어 1 (이진수)는 비트 0으로 설정 되 고 1만 (이진수)는 비트 4로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="80ed0-114">각 비트는 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-114">Each bit represents a property.</span></span> <span data-ttu-id="80ed0-115">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-115">The following are some examples:</span></span>

  - <span data-ttu-id="80ed0-116">1만 (이진수)의 10 진수 값이 16 (즉, 비트 4가 설정 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="80ed0-117">1억 (이진수)에 256의 10 진수 값 (즉, 비트 8이 설정 됨)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="80ed0-118">1100 (이진수)의 10 진수 값이 12입니다 (즉, bits 2와 3이 설정 되 고, 두 비트로 표현 된 속성을 사용할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="80ed0-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="80ed0-119">1111000001 (이진수)의 10 진수 값 961 (즉, 비트 0, 6, 7, 8, 9가 설정 되 고 각 비트에 대 한 속성을 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="80ed0-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="80ed0-120">Lync Server 2013의 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="80ed0-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80ed0-121">특성</span><span class="sxs-lookup"><span data-stu-id="80ed0-121">Attribute</span></span></th>
<th><span data-ttu-id="80ed0-122">설명</span><span class="sxs-lookup"><span data-stu-id="80ed0-122">Description</span></span></th>
<th><span data-ttu-id="80ed0-123">메모</span><span class="sxs-lookup"><span data-stu-id="80ed0-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="80ed0-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="80ed0-125">이제 <strong>msRTCSIP</strong> 및 <strong>msRTCSIP</strong> 클래스와 연결 된 Active Directory 도메인 서비스의 기존 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="80ed0-126">이 특성은 풀 또는 모니터링 서버의 정규화 된 도메인 이름 (FQDN)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="80ed0-127">각 세그먼트에 대 한 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-128">Microsoft Office Live Communications Server 2005의 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="80ed0-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-130">이 특성은이 개체에 해당 하는 다른 포리스트의 개체에 대 한 DN (고유 이름)의 문자열 표현을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="80ed0-131">이 특성은 메일 그룹 확장과 자동으로 참석 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="80ed0-132">이 특성은 Windows Server 2003 R2의 기본 Active Directory 스키마에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="80ed0-133">AD DS를 Windows Server 2003 R2로 업그레이드 하지 않도록 하기 위해 Active Directory 스키마 준비에서이 특성 정의를 사용 하 여 Windows Server 2003 스키마를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-134">Microsoft Office 통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="80ed0-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="80ed0-136">이 다중 값 특성에는 음성 메일 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="80ed0-137">이 특성은 Exchange UM (통합 메시징)와 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="80ed0-138">Microsoft Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="80ed0-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="80ed0-140">이 다중 값 특성에는 사용자에 게 적용 되는 보류 정책에 대 한 식별자가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="80ed0-141">보존 정책은 보류 기간 동안 사용자의 사서함 항목을 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="80ed0-142">이 특성은 Exchange 2013와 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-143">Lync Server 2013의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="80ed0-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="80ed0-145">이 특성은 사용자에 대 한 오디오 회의 공급자 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-146">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="80ed0-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="80ed0-148">이 특성은 응용 프로그램 대화 상대에 대 한 신뢰할 수 있는 서비스 항목을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-149">Microsoft Office Communications Server 2007 R2의 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="80ed0-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="80ed0-151">이 특성에는 응용 프로그램 서버에서 호스팅되는 응용 프로그램의 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-152">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="80ed0-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="80ed0-154">이 특성은 응용 프로그램 연락처에 대 한 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-155">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="80ed0-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="80ed0-157">이 특성에는 응용 프로그램 연락처의 기본 언어가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-158">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="80ed0-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="80ed0-160">이 여러 값 특성에는 응용 프로그램 연락처의 보조 언어가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-161">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="80ed0-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="80ed0-163">이 특성에는이 풀에 속한 응용 프로그램 서버 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="80ed0-164">@ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ <strong>뒤로 링크</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-165">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="80ed0-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="80ed0-167">이 특성은이 응용 프로그램 서버가 속한 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="80ed0-168">전방 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-168">This is the forward link.</span></span> <span data-ttu-id="80ed0-169">해당 역방향 링크는 <strong>msRTCSIP-ApplicationServerBL</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-170">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-171">msRTCSIP-ArchiveDefault (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-172">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-173">Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-174">msRTCSIP-ArchiveDefaultFlags (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-175">이 특성은 모든 사용자 통신을 보관할 포리스트 경계 내의 전역 기본값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="80ed0-176">이는 보관 에이전트 계층에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="80ed0-177">이 특성에 대 한 값의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-178"><strong>TRUE</strong>: 모든 사용자 보관</span><span class="sxs-lookup"><span data-stu-id="80ed0-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="80ed0-179"><strong>FALSE</strong>: 모든 사용자 보관 안 함</span><span class="sxs-lookup"><span data-stu-id="80ed0-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="80ed0-180">이 특성은 포리스트 경계 내에서 내부 네트워크 내의 사용자 통신을 보관 하는 방법을 전역적으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="80ed0-181"><strong>Live Communications Server 2005 동작 (현재 사용 중지)</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="80ed0-182">이 특성에 대 한 값의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-183">0: 메시지 본문 보관 [비트 0]</span><span class="sxs-lookup"><span data-stu-id="80ed0-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="80ed0-184">1: 메시지 본문을 보관 하지 않음 [비트 0]</span><span class="sxs-lookup"><span data-stu-id="80ed0-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="80ed0-185"><strong>Office Communications Server 2007 동작</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="80ed0-186">이 특성에 대 한 값의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-187">0: ArchiveFederationDefaultWithoutBody (사용 중지)</span><span class="sxs-lookup"><span data-stu-id="80ed0-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="80ed0-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="80ed0-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="80ed0-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="80ed0-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="80ed0-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="80ed0-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="80ed0-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="80ed0-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="80ed0-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="80ed0-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="80ed0-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="80ed0-194">9: Record오디오 Ocalldetails</span><span class="sxs-lookup"><span data-stu-id="80ed0-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="80ed0-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="80ed0-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="80ed0-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="80ed0-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="80ed0-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="80ed0-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="80ed0-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="80ed0-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="80ed0-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="80ed0-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="80ed0-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="80ed0-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="80ed0-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="80ed0-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-202">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-203">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-204">msRTCSIP-ArchiveFederationDefault (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-205">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-206">Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-207">msRTCSIP-ArchiveFederationDefaultFlags (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-208">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-209">Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="80ed0-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="80ed0-211">이 특성은 단일 사용자의 통신을 보관할지 여부를 제어 하는 비트 필드로 사용 되는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="80ed0-212">이 컨트롤은 보관 에이전트 계층에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="80ed0-213">이는 글로벌 카탈로그 복제로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="80ed0-214">이 특성의 범위는 단일 사용자 또는 연락처와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="80ed0-215">Lync Server의 유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-216">0: 보관 안 함 (비트 집합 없음)</span><span class="sxs-lookup"><span data-stu-id="80ed0-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-217">1: 사용 중지 (비트 위치 0)</span><span class="sxs-lookup"><span data-stu-id="80ed0-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-218">2: 사용 중지 (비트 위치 1)</span><span class="sxs-lookup"><span data-stu-id="80ed0-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-219">4: 내부 통신 보관 (비트 위치 2)</span><span class="sxs-lookup"><span data-stu-id="80ed0-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-220">8: 페더레이션 통신 보관 (비트 위치 3)</span><span class="sxs-lookup"><span data-stu-id="80ed0-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="80ed0-221">Live Communications Server 2005의 이전 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-222">0: 우선 순위에 따라 <strong>msRTCSIP-ArchiveDefault</strong> 및 <strong>msRTCSIP-ArchiveFederation</strong> 에 의해 정의 된 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-223">1: 보관</span><span class="sxs-lookup"><span data-stu-id="80ed0-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="80ed0-224">2: 보관 안 함</span><span class="sxs-lookup"><span data-stu-id="80ed0-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="80ed0-225">3: 메시지 본문 없이 보관</span><span class="sxs-lookup"><span data-stu-id="80ed0-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-226">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-227">msRTCSIP-ArchivingServerData (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-228">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-229">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-230">msRTCSIP-ArchivingServerVersion (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-231">이 특성은 보관 서비스의 버전을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="80ed0-232">이 특성은 공식적인 각 제품 릴리스로 증가 하는 monotonously 증가 하는 정수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="80ed0-233">가능한 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-234">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="80ed0-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="80ed0-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="80ed0-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="80ed0-236">                 실시간 통신 서버 2005 (SP1)</span><span class="sxs-lookup"><span data-stu-id="80ed0-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="80ed0-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="80ed0-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="80ed0-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="80ed0-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-239">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-240">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="80ed0-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="80ed0-242">이 특성은 풀 백 엔드 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="80ed0-243">풀 당 하나의 백 엔드 서버만 사용할 수 있기 때문에 단일 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="80ed0-244">각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-245">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="80ed0-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="80ed0-247">이 특성에는 컨퍼런스 디렉터리를 호스팅하는 풀의 식별자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-248">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="80ed0-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="80ed0-250">이 특성에는 컨퍼런스 디렉터리의 식별자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-251">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="80ed0-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="80ed0-253">이 특성에는 회의 디렉터리가 이동 되는 풀의 식별자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-254">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-255">msRTCSIP-기본값</span><span class="sxs-lookup"><span data-stu-id="80ed0-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="80ed0-256">이 부울 특성은 전화 사용이 기본 사용 인지 여부를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="80ed0-257">이 특성을 <strong>TRUE</strong>로 설정 하면 전화 사용이 기본 사용 이므로 관리자가 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="80ed0-258">이 특성을 <strong>FALSE</strong>로 설정 하면 사용을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-259">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="80ed0-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="80ed0-261">이 특성은 조직 외부의 사용자에 대 한 Communicator Web Access URL을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-262">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="80ed0-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="80ed0-264">이 특성은 조직 내에 있는 사용자의 Communicator Web Access URL을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-265">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-266">msRTCSIP-DefaultLocationProfileLink (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-267">이 단일 값 특성에는 할당 된 위치 프로필 클래스 개체의 DN (고유 이름)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="80ed0-268">전달 링크: <strong>링크 ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="80ed0-269">해당 역방향 링크는 <strong>msRTCSIP-ServerReferenceBL</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-270">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-271">msRTCSIP-DefaultPolicy (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-272">이 부울 특성은 정책이 기본 정책 인지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="80ed0-273">정책이 <strong>TRUE</strong>로 설정 되 면 기본 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-274">Office Communications Server 2007의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="80ed0-275">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-276">msRTCSIP-DefaultRouteToEdgeProxy (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-277">이 특성은 액세스에 지 서비스를 실행 하는 Edge 서버의 FQDN을 지정 하 고, 직접 액세스할 수 있는 경우에는 액세스에 지 서비스를 실행 하는 서버 풀의 하드웨어 부하 분산 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="80ed0-278">액세스에 지 서비스를 실행 하는 서버에 하나 이상의 디렉터만 액세스할 수 있는 경우,이 특성은 FQDN을 지정 하 고, 선택적으로 디렉터의 포트 번호 또는 디렉터 풀을 처리 하는 하드웨어 부하 분산 장치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="80ed0-279">각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-280">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-281">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-282">msRTCSIP-DefaultRouteToEdgeProxyPort (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-283">이 특성은 액세스에 지 서비스를 실행 하는 서버에 연결 하는 데 사용 해야 하는 포트 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="80ed0-284">유효한 값은 사용할 포트를 지정 하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="80ed0-285">기본값은 5061입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-286">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-287">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-288">msRTCSIP-DefPresenceSubscriptionTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-289">이 특성은 기본 현재 상태 구독 시간 초과 기간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-290">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-291">msRTCSIP-DefRegistrationTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-292">이 특성은 기본 등록 시간 초과 창을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-293">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-295">이 특성은 기본 로밍 데이터 구독 시간 초과 창을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-296">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="80ed0-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="80ed0-298">이 특성은 분할 된 도메인 토폴로지에 사용 되며 FQDN (정규화 된 도메인 이름)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="80ed0-299">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-300">msRTCSIP-설명 (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-301">이 단일 값 유니코드 문자열 특성에는이 전화 경로 또는 정규화 규칙에 대 한 간단한 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-302">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-303">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-304">msRTCSIP-도메인 데이터</span><span class="sxs-lookup"><span data-stu-id="80ed0-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-305">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="80ed0-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="80ed0-307">이 특성은 등록 기관에 대해 구성 된 도메인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="80ed0-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-309">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-310">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="80ed0-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-312">이 특성은 액세스에 지 서비스를 실행 하는 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="80ed0-313">각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-314">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-315">msRTCSIP-EnableBestEffortNotify (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-316">이 특성은 서버에서 클라이언트의 구독 요청에 대 한 응답으로 알림 요청 대신 BENOTIFY (최고 작업량 알림) 요청을 생성할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="80ed0-317">BENOTIFY는 일반 알림 요청 대신 서버가 BENOTIFY 요청을 생성 하는 구독 알림 핸드셰이크에 대 한 성능 향상 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="80ed0-318">성능상의 이점은 BENOTIFY 요청에 알림 요청이 수행 하는 것 처럼 클라이언트의 200 OK 응답을 요구 하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="80ed0-319">유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="80ed0-320">Live Communications Server 2003는 BENOTIFY 요청을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="80ed0-321">Live communications Server 2005 및 타사 서버에서 실행 되는 Live Communications Server 2003 server API를 사용 하 여 작성 된 서버 응용 프로그램과 상호 운용 하려면 해당 값을 <STRONG>FALSE</STRONG>로 설정 하 여 BENOTIFY 요청을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="80ed0-322">BENOTIFY는 현재 IETF (인터넷 엔지니어링 작업 포스) SIP 표준화 프로세스에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="80ed0-323">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-324">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-325">msRTCSIP-EnableFederation (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-326">이 특성은 사용자가 다른 조직의 사용자와 통신할 수 있는지 여부를 구성 하는 데 사용 되는 전역 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="80ed0-327">관리자가 개별 사용자의 <strong>FederationEnabled</strong> 특성을 덮어쓸 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="80ed0-328">이 특성은 웜, 바이러스 또는 회사의 대상 공격으로 인해 발생할 수 있는 인터넷 공격 으로부터 내부 네트워크를 보호 하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="80ed0-329">유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-330">1: 공용 IM 연결에 사용 (비트 위치 0)</span><span class="sxs-lookup"><span data-stu-id="80ed0-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-331">2: 예약 됨 (비트 위치 1)</span><span class="sxs-lookup"><span data-stu-id="80ed0-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-332">4: 예약 됨 (비트 위치 2)</span><span class="sxs-lookup"><span data-stu-id="80ed0-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-333">8: 예약 됨 (비트 위치 3)</span><span class="sxs-lookup"><span data-stu-id="80ed0-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-334">16: 원격 통화 제어 사용 [전화 통신] (비트 위치 4)</span><span class="sxs-lookup"><span data-stu-id="80ed0-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-335">64: AllowOrganizeMeetingWithAnonymousParticipants (사용자가 모임에 익명 사용자를 초대 하도록 허용 (비트 위치 6)</span><span class="sxs-lookup"><span data-stu-id="80ed0-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-336">128: 작업 사용 (통합 커뮤니케이션에 대해 사용자 사용) (비트 위치 7)</span><span class="sxs-lookup"><span data-stu-id="80ed0-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-337">256: EnabledForEnhancedPresence (공용 IM 연결에 사용자 사용) (비트 위치 8)</span><span class="sxs-lookup"><span data-stu-id="80ed0-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-338">512: RemoteCallControlDualMode (비트 위치 9)</span><span class="sxs-lookup"><span data-stu-id="80ed0-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-339">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-340">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="80ed0-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="80ed0-342">이 특성은 엔터프라이즈 서비스가 지정 된 서버에 로드 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="80ed0-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-344">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="80ed0-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="80ed0-346">이 특성에는 외부 액세스를 위한 전화 번호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-347">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="80ed0-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="80ed0-349">이 특성은 단일 사용자가 페더레이션을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="80ed0-350">엔터프라이즈 서비스 계층에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="80ed0-351">이는 글로벌 카탈로그 복제로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="80ed0-352">유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-353">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="80ed0-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="80ed0-355">이 특성은 풀과 연결 된 모든 Enterprise Edition 서버의 도메인 이름에 대 한 다중값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="80ed0-356">뒤로 링크: <strong>링크 ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="80ed0-357">이 역방향 링크에 해당 하는 전방 링크는 <strong>msRTCSIP-PoolAddress</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-358">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-359">msRTCSIP-게이트웨이 (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-360">이 다중 값 문자열 특성에는 게이트웨이 별 게이트웨이 및 포트 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="80ed0-361">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-362">msRTCSIP-GlobalSettingsData (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-363">이 특성은 이름: 값 쌍을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="80ed0-364">이미 정의 된 이름: 값 쌍은 <strong>현재 상태 폴링 허용</strong> 설정에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-365">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="80ed0-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="80ed0-367">이 특성은 주소록 항목을 그룹화 하는 데 사용 되는 그룹의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-368">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-369">msRTCSIP-HomeServer (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-370">Live Communications Server 2003 (사용 되지 않음)의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="80ed0-371">Live Communications Server 2005에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-372">msRTCSIP-HomeServerString (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-373">실시간 통신 서버 2003의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="80ed0-374">Live Communications Server 2005에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-375">msRTCSIP-HomeUsers (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-376">Live Communications Server 2003 (사용 되지 않음)의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="80ed0-377">Live Communications Server 2005에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="80ed0-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="80ed0-379">이 특성은 외부 사용자 액세스에 대해 단일 사용자를 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="80ed0-380">엔터프라이즈 서비스 계층에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="80ed0-381">이는 글로벌 카탈로그 복제로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="80ed0-382">유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-383">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-384">msRTCSIP-IsMaster (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-385">실시간 통신 서버 2003의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="80ed0-386">Live Communications Server 2005에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-387">msRTCSIP 선</span><span class="sxs-lookup"><span data-stu-id="80ed0-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="80ed0-388">이 단일 값 특성에는 장치 ID (사용자 컨트롤을 사용 하는 SIP URI 또는 휴대폰의 TEL URI)가 전화 통신을 위해 Lync에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="80ed0-389">이 특성은 글로벌 카탈로그 복제용으로 표시 되며 인덱싱되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="80ed0-390">사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정 되어 있는 경우이 특성은 사용자의 전화 번호의 164 정규화 된 버전을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-391">Microsoft Office Live Communications Server 2005 SP1에서 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="80ed0-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="80ed0-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="80ed0-393">이 단일 값 특성에는 CSTA-SIP 게이트웨이 서버의 SIP URI가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="80ed0-394">이 특성은 글로벌 카탈로그 복제에 대해 표시 되지만 인덱싱되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-395">Microsoft Office Live Communications Server 2005 SP1에서 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="80ed0-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-396">msRTCSIP-LocalNormalizationData (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-397">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-398">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-399">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-400">msRTCSIP-LocalNormalizationLinks (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-401">이 다중 값 특성에는이 위치 프로필에 연결 된 DN (local 정규화 고유 이름) 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="80ed0-402">이 특성의 형식은 DN 이진입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="80ed0-403">위치 프로필과 로컬 정규화 규칙 사이에는 일대다 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="80ed0-404">로컬 정규화 DNs 목록의 순서는 관리자가 지정한 순서 대로 유지 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="80ed0-405">순서 보존은 주문 인덱스를 지정 하는 DN 이진의 이진 부분에 의해 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="80ed0-406">전달 링크: <strong>링크 ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="80ed0-407">이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-LocationProfileBL</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-408">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-409">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="80ed0-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="80ed0-411">이 특성에는 정규화 규칙에 대 한 옵션 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-412">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-413">msRTCSIP-LocationName (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-414">이 단일 값 특성에는이 프로필이 나타내는 위치를 나타내는 위치 프로필에 대 한 친근 한 이름이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="80ed0-415">여러 위치 프로필을 사용할 수 있기 때문에 관리자는 여러 프로필을 구분 하는 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-416">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-417">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-418">msRTCSIP-locationProfileBL (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-419">이 다중 값 특성에는 위치 프로필의 고유 이름 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="80ed0-420">이 특성은 하나 이상의 위치 프로필에 대 한 역방향 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="80ed0-421">뒤로 링크: <strong>링크 ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="80ed0-422">이 특성은 전방 링크 <strong>msRTCSIP-LocalNormalizationLinks</strong>에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-423">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-424">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-425">msRTCSIP-LocationProfileData (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-426">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-427">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-428">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="80ed0-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="80ed0-430">이 특성에는 위치 프로필에 대 한 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-431">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="80ed0-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="80ed0-433">이 다중 값 특성에는 응용 프로그램 연락처 목록이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-434">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="80ed0-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="80ed0-436">이 다중 값 특성에는 위치 프로필 목록이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-437">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-438">msRTCSIP-MaxNumOutstandingSearchPerServer (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-439">이 특성은 서버 당 해결 되지 않은 최대 검색 요청 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-440">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-441">msRTCSIP-MaxNumSubscriptionsPerUser (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-442">사용자 당 최대 구독 수를 나타내는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-443">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-444">msRTCSIP-MaxPresenceSubscriptionTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-445">이 특성은 최대 구독 시간 초과 기간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-446">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-447">msRTCSIP-MaxRegistrationsTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-448">이 특성은 최대 등록 시간 초과 기간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-449">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-451">이 특성은 최대 로밍 데이터 구독 시간 초과 기간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-452">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="80ed0-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-454">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-455">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="80ed0-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="80ed0-457">이 특성은 해당 링크가 속한 MCU (multipoint control unit) Factory에 대 한 링크를 다시 지정 하는 컴퓨터 클래스의 서비스 제어 지점 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="80ed0-458">이 서비스 제어 지점과 특성은 모든 Microsoft MCU에 대해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="80ed0-459">각 Microsoft MCU는 해당 그룹에서 풀 수준 설정을 검색 하기 위해 자신이 속해 있는 풀의 백 엔드 서버를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="80ed0-460">이 특성의 값은 MCU 팩터리의 DN (고유 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="80ed0-461">이것은 단일 값 특성이 며 글로벌 카탈로그 복제로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="80ed0-462">전달 링크: <strong>링크 ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="80ed0-463">이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-MCUServers</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-464">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="80ed0-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-466">다중 문자열 예약 된 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="80ed0-467">이 특성에 저장 된 설정은 이름/값 쌍으로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="80ed0-468">현재 정의 된 이름/값 쌍은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="80ed0-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-470">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="80ed0-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="80ed0-472">풀과 연결 된 단일 MCU 팩터리의 DN (고유 이름)을 포함 하는 단일 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="80ed0-473">전달 링크: <strong>링크 ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="80ed0-474">이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-PoolAddresses</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-475">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="80ed0-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="80ed0-477">이 특성은 MCU factory provider의 GUID를 지정 하는 단일 값 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="80ed0-478">GUID 값을 기준으로 MCU factory 프로세스는이 MCU 형식을 서비스 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="80ed0-479">GUID 값이 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>인 경우 MCU factory 프로세스 (Lync Server에서 기본적으로 사용 가능)가 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="80ed0-480">다른 GUID 값에 대해서는 MCU factory 프로세스가 MCU 형식을 서비스 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-481">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="80ed0-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="80ed0-483">이 특성은 DN (고유 이름)의 다중 값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="80ed0-484">이 특성에는이 MCU 팩터리에 연결 된 동일한 종류 및 공급 업체의 모든 MCU 서버 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="80ed0-485">각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="80ed0-486">뒤로 링크: 링크 ID 11027</span><span class="sxs-lookup"><span data-stu-id="80ed0-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="80ed0-487">이 후방에 해당 하는 전방 링크는 <strong>msRTCSIP-MCUFactoryAddress</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-488">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-489">msRTCSIP-M가공선</span><span class="sxs-lookup"><span data-stu-id="80ed0-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="80ed0-490">이 특성은 MCU가 처리할 수 있는 매체를 지정 하는 단일 값 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="80ed0-491">지원 되는 유효한 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-492">모임을</span><span class="sxs-lookup"><span data-stu-id="80ed0-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="80ed0-493">오디오-영상</span><span class="sxs-lookup"><span data-stu-id="80ed0-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="80ed0-494">채트</span><span class="sxs-lookup"><span data-stu-id="80ed0-494">chat</span></span></p></li>
<li><p><span data-ttu-id="80ed0-495">휴대폰-회의</span><span class="sxs-lookup"><span data-stu-id="80ed0-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-496">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-497">msRTCSIP-MCUVendor 공급 업체</span><span class="sxs-lookup"><span data-stu-id="80ed0-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="80ed0-498">이 특성은 MCU 공급 업체의 이름을 지정 하는 단일 값 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="80ed0-499">모든 Microsoft MCUs는이 특성을 <strong>Microsoft Corporation</strong>으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-500">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-501">msRTCSIP-MeetingFlags (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-502">이 특성은 모든 사용자 또는 연락처 개체에 전체적으로 사용할 수 있는 다른 모임 옵션을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="80ed0-503">이 특성은 정수 형식의 비트 마스크 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="80ed0-504">유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-505">0: AllowOrganizeMeetingWithAnonymousParticipants가 없음 (사용자가 익명 사용자를 모임에 초대 하지 않도록 허용 하지 않음) (비트가 설정 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="80ed0-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-506">4: AllowOrganizeMeetingWithAnonymousParticipants는 Everyone (모든 사용자가 익명 사용자를 모임에 초대할 수 있도록 허용) (비트 위치 2)</span><span class="sxs-lookup"><span data-stu-id="80ed0-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-507">8: AllowOrganizeMeetingWithAnonymousParticipants는 UsePerUserSetting (사용자가 사용자별 설정에 기반 하 여 모임에 익명 사용자를 초대 하도록 허용) (비트 위치 3)</span><span class="sxs-lookup"><span data-stu-id="80ed0-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-508">16: UserPerUserMeetingPolicy (모임 정책이 사용자 당 정의 됨) (비트 위치 4)</span><span class="sxs-lookup"><span data-stu-id="80ed0-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-509">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-510">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-511">msRTCSIP-MeetingPolicy (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-512">이 특성은 관리자가이 사용자에 게 할당 한 정책의 DN (고유 이름)을 단일 값 특성으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-513">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-514">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-515">msRTCSIP-MinPresenceSubscriptionTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-516">이 특성은 최소 현재 상태 구독 시간 초과 창을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-517">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-518">msRTCSIP-MinRegistrationTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-519">이 특성은 최소 등록 시간 초과 창을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-520">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-521">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-523">이 특성은 최소 로밍 데이터 구독 시간 초과 창을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-524">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-525">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="80ed0-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="80ed0-527">이 특성은 프런트 엔드 풀에 사용 되는 미러된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-528">Lync Server 2013의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="80ed0-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="80ed0-530">이 특성은 이동성 설정을 정의 하는 옵션과 플래그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-531">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="80ed0-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="80ed0-533">이 특성은 이동성 정책 개체의 DN을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-534">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-535">msRTCSIP-NumDevicesPerUser (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-536">이 특성은 사용자가 SIP 통신을 등록 하 고 현재 상태를 구독할 수 있는 허용 되는 장치 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-537">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-538">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-539">msRTCSIP 플래그</span><span class="sxs-lookup"><span data-stu-id="80ed0-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="80ed0-540">이 특성은 사용자 또는 연락처 개체에 대해 사용 하도록 설정 된 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="80ed0-541">이 특성은 integer 형식의 비트 마스크 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="80ed0-542">각 옵션은 비트로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-542">Each option is represented by a bit.</span></span> <span data-ttu-id="80ed0-543">이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="80ed0-544">유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-545">1: 공용 인스턴트 메시징 (IM) 연결에 사용 (비트 위치 0)</span><span class="sxs-lookup"><span data-stu-id="80ed0-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-546">2: 예약 됨 (비트 위치 1)</span><span class="sxs-lookup"><span data-stu-id="80ed0-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-547">4: 예약 됨 (비트 위치 2)</span><span class="sxs-lookup"><span data-stu-id="80ed0-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-548">8: 예약 됨 (비트 위치 3)</span><span class="sxs-lookup"><span data-stu-id="80ed0-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-549">16: 원격 통화 제어 사용 [전화 통신] (비트 위치 4)</span><span class="sxs-lookup"><span data-stu-id="80ed0-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-550">64: AllowOrganizeMeetingWithAnonymousParticipants (사용자가 모임에 익명 사용자를 초대 하도록 허용 (비트 위치 6)</span><span class="sxs-lookup"><span data-stu-id="80ed0-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-551">128: 작업 사용 (UC 사용자 사용) (비트 위치 7)</span><span class="sxs-lookup"><span data-stu-id="80ed0-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-552">256: EnabledForEnhancedPresence (공용 IM 연결에 사용자 사용) (비트 위치 8)</span><span class="sxs-lookup"><span data-stu-id="80ed0-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-553">512: RemoteCallControlDualMode (비트 위치 9)</span><span class="sxs-lookup"><span data-stu-id="80ed0-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-554">실시간 통신 서버 2005 (SP1)에서 새로 만들기.</span><span class="sxs-lookup"><span data-stu-id="80ed0-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="80ed0-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="80ed0-556">이 특성은 Windows NT Server principal 계정에서 사용자의 ObjectSID이 리소스 또는 중앙 포리스트의 해당 사용자 또는 연락처 개체의이 특성으로 복사 될 때 single sign-on을 사용 하도록 설정 하기 위해 리소스 및 중앙 포리스트 토폴로지에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="80ed0-557">Communicator Web Access는이 특성 또는 사용자의 ObjectSID를 사용 하 여 AD DS에 있는 사용자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="80ed0-558">이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-559">msRTCSIP-소유자 Urn</span><span class="sxs-lookup"><span data-stu-id="80ed0-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="80ed0-560">이 특성은 응용 프로그램 연락처에 대 한 소유자의 URN (Uniform Resource Name)입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-561">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-562">msRTCSIP-패턴 (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-563">이 단일 값 문자열 특성에는 다이얼 번호와 일치 하는 데 사용 되는 패턴이 전자 164 형식으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="80ed0-564">전화 번호가이 패턴과 일치 하는 경우에는 전화를 건 번호에 번역이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-565">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-566">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-567">msRTCSIP-PhoneRouteBL (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-568">이 다중 값 특성에는 DN (전화 경로 고유 이름) 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="80ed0-569">이 특성은 하나 이상의 휴대폰 경로에 대 한 역방향 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="80ed0-570">뒤로 링크: <strong>링크 ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="80ed0-571">이 특성은 전방 링크 <strong>msRTCSIP-RouteUsageLinks</strong>에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-572">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-573">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-574">msRTCSIP-PhoneRouteData (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-575">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-576">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-577">msRTCSIP-PhoneRouteName (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-578">이 단일 값으로 된 UNICODE 문자열 특성은 전화 경로의 친숙 한 이름을 지정 하므로 관리자가 쉽게 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-579">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-580">msRTCSIP-PhoneUsageData (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-581">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-582">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-583">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-584">msRTCSIP-PolicyContent (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-585">이 특성은 단일 값 유니코드 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="80ed0-586">이 문자열 특성은 XML 형식의 정책 정의를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="80ed0-587">XML 스키마 정의는 여러 정책 형식에서 공통 되며 각 정책 유형에 대 한 설정만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="80ed0-588">XSD (XML 스키마 정의)는 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="80ed0-589">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-590">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-591">msRTCSIP-PolicyData (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-592">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-593">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-594">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-595">msRTCSIP-PolicyType (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-596">이 단일 값 유니코드 문자열 특성에는 정책 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="80ed0-597">유효한 정책 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-598">모임을</span><span class="sxs-lookup"><span data-stu-id="80ed0-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="80ed0-599">통신</span><span class="sxs-lookup"><span data-stu-id="80ed0-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-600">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-601">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="80ed0-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="80ed0-603">이 특성은 컴퓨터가 속한 풀로 돌아가는 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="80ed0-604">이 특성은 컴퓨터에서 Lync Server의 Standard Edition 또는 Enterprise Edition을 실행 하 고 있는지 여부에 관계 없이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="80ed0-605">이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="80ed0-606">유효한 값은 풀의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="80ed0-607">전달 링크: <strong>링크 ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="80ed0-608">이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-FrontEndServers</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-609">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="80ed0-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="80ed0-611">이는 MCU 팩터리가 연결 된 풀의 DN (고유 이름) 목록이 포함 된 다중 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="80ed0-612">뒤로 링크: <strong>링크 ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="80ed0-613">이 후방에 해당 하는 전방 링크는 <strong>msRTCSIP-MCUFactoryPath</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-614">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="80ed0-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-616">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-617">실시간 통신 서버 2005 (SP1)에서 새로 만들기.</span><span class="sxs-lookup"><span data-stu-id="80ed0-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="80ed0-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="80ed0-619">이 특성은 관리 콘솔에 표시 되는 풀에 대 한 임의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="80ed0-620">이 이름은 관리자가 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="80ed0-621">유효한 값은 풀의 이름을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-622">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="80ed0-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-624">이 특성은 단일 값 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="80ed0-625">이 특성의 값이 있으면 관리자가 프런트 엔드 풀을 만든 Active Directory 도메인 구조에 맞지 않는 FQDN을 사용 하 여 프런트 엔드 풀을 만들려는 경우 풀의 도메인 FQDN을 나타냅니다 (예: SIP DNS (Domain Name System) 네임 스페이스에 대 한 네임 스페이스의 가입이 해제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="80ed0-626">프런트 엔드 풀 도메인 FQDN을 해당 풀이 있는 Active Directory 도메인으로 도메인 이름 부분에 매핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="80ed0-627">따라서이 특성에 값이 없는 경우에는 <strong>dnsHostName</strong> 특성이 표시 하는 것 처럼 프런트 엔드 풀 FQDN이 Active Directory 도메인 이름 구조를 기본값으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-628">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="80ed0-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="80ed0-630">풀과 연결 된 모든 Lync Server 엔터프라이즈 버전 서버의 도메인 이름에 대 한 다중 값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="80ed0-631">이 integer 형식의 특성은 풀이 인스턴트 메시지 (IM)와 현재 상태, 모임을 사용할 수 있는지 여부를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="80ed0-632">가능한 유효한 값 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-633">정의 되지 않음: IM 및 현재 상태 서비스 (Live Communications Server 2005 및 2003)</span><span class="sxs-lookup"><span data-stu-id="80ed0-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-634">1: IM 및 현재 상태 서비스 (Lync 서버)</span><span class="sxs-lookup"><span data-stu-id="80ed0-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-635">2: IM 및 현재 상태 및 모임 서비스 (Lync 서버)</span><span class="sxs-lookup"><span data-stu-id="80ed0-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-636">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="80ed0-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="80ed0-638">이 특성은 서버 풀이 Standard Edition server 또는 Enterprise Edition 서버를 실행 하 고 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="80ed0-639">이 특성은 integer 형식의 비트 마스크 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="80ed0-640">각 옵션은 비트로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="80ed0-641">유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-642">1: 스탠더드 버전 서버, 호스트 사용자 (비트 위치 0)</span><span class="sxs-lookup"><span data-stu-id="80ed0-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-643">2: Enterprise Edition server, 호스트 사용자 (비트 위치 1)</span><span class="sxs-lookup"><span data-stu-id="80ed0-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-644">4: 스탠더드 버전 서버, 호스트 응용 프로그램 (비트 위치 2)</span><span class="sxs-lookup"><span data-stu-id="80ed0-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-645">8: Enterprise Edition server, 호스트 응용 프로그램 (비트 위치 3)</span><span class="sxs-lookup"><span data-stu-id="80ed0-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="80ed0-646">Lync Server는 응용 프로그램을 호스트 하는 풀을 지원 하지 않으므로 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-647">5: Standard Edition 서버, 호스트 사용자 및 응용 프로그램 (비트 위치 0 및 2)</span><span class="sxs-lookup"><span data-stu-id="80ed0-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-648">10: Enterprise Edition server, 호스트 사용자 및 응용 프로그램 (비트 위치 1 및 3)</span><span class="sxs-lookup"><span data-stu-id="80ed0-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-649">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="80ed0-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="80ed0-651">이 특성은 풀 버전을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-651">This attribute defines the pool version.</span></span> <span data-ttu-id="80ed0-652">각 주요 제품 릴리스로 증가 하는 정수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="80ed0-653">가능한 유효한 값 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="80ed0-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="80ed0-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="80ed0-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="80ed0-656">2: 실시간 통신 서버 2005 (SP1)</span><span class="sxs-lookup"><span data-stu-id="80ed0-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="80ed0-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="80ed0-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="80ed0-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="80ed0-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="80ed0-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="80ed0-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-660">실시간 통신 서버 2005 (SP1 포함).</span><span class="sxs-lookup"><span data-stu-id="80ed0-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="80ed0-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="80ed0-662">이 특성은 현재 상태 설정을 정의 하는 옵션과 플래그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-663">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="80ed0-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="80ed0-665">이 특성에는 현재 상태 정책 개체의 DN이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-666">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="80ed0-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="80ed0-668">이 특성은 SIP 메시지에 대 한 사용자 또는 연락처를 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="80ed0-669">중앙 포리스트 토폴로지에서는 사용자 개체가 아닌 연락처 개체는 SIP를 사용할 수 있기 때문에 contact 클래스에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="80ed0-670">유효한 값은 사용자가 속한 Standard Edition server 또는 Enterprise Edition 프런트 엔드 풀의 DN입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-671">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="80ed0-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="80ed0-673">이 특성에는 특정 사용자의 SIP 주소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="80ed0-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="80ed0-675">이 특성에는 개인 회선 디바이스의 디바이스 ID가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-676">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-677">msRTCSIP-라우팅 가능</span><span class="sxs-lookup"><span data-stu-id="80ed0-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="80ed0-678">이 특성은 Lync Server에서 GRUU 주소를 사용 하 여이 서비스로 라우팅할 권한이 있는지 여부를 결정 하는 데 사용 되는 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="80ed0-679">이 값을 <strong>TRUE</strong>로 설정 하는 경우 Lync Server에이 서비스로 라우팅할 수 있는 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="80ed0-680">이 값을 <strong>FALSE</strong>로 설정 하는 경우 Lync Server에는이 서비스로 라우팅할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-681">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-682">msRTCSIP-RouteUsageAttribute (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-683">이 단일 값 유니코드 문자열 특성은 전화 경로의 사용을 정하는 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="80ed0-684">전화 경로의 선택은 두 가지 요소, 즉 전화 경로에 할당 된 사용 특성과 호출자가 허용 되는 정책 사용 특성을 기준으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="80ed0-685">호출자의 허용 사용이 일치 하는 사용 특성이 있는 첫 번째 전화 경로가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-686">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-687">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-688">msRTCSIP-RouteUsageLinks (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-689">이 다중 값 고유 이름 (DN) 특성에는 경로 사용 고유 이름 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="80ed0-690">전달 링크: <strong>링크 ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="80ed0-691">이 특성은 해당 하는 뒤로 링크 <strong>msRTCSIP-PhoneRouteBL</strong>에 대 한 전방 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-692">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="80ed0-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-694">이 특성에는이 MCU 또는 신뢰할 수 있는 서비스로 주소가 지정 된 모든 SIP 트래픽이 통과 해야 하는 풀을 가리키는 DN이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-695">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-696">msRTCSIP-RuleName (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-697">이 단일 값 유니코드 문자열 특성은 정규화 규칙의 이름을 지정 하 여 관리자가 쉽게 참조할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-698">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-699">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="80ed0-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="80ed0-701">이 특성은 현재 조직에 배포 된 스키마 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-702">msRTCSIP-SearchMaxRequests (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-703">이 특성은 사용자가 Communicator를 사용 하 여 연락처를 검색할 때 디렉터리 검색에서 반환 되는 검색 결과의 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="80ed0-704">이 특성은 클라이언트에서 제공 하는 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-705">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-706">msRTCSIP-SearchMaxResults (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-707">이 특성은 반환 되는 검색 요청 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-708">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="80ed0-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="80ed0-710">이 다중 값 특성은 DN (고유 이름) 목록을 포함 하는 역방향 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="80ed0-711">이러한 DNs는 풀이나 <strong>서비스</strong> 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="80ed0-712">이 특성은 전방 링크 <strong>msRTCSIP-TrustedServiceLinks</strong>에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-713">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="80ed0-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-715">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-716">msRTCSIP-ServerReferenceBL (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-717">이 다중값 특성에는 고유 이름 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="80ed0-718">이러한 고유 이름은 기본 위치 프로필을 할당할 수 있는 다른 서버 개체를 참조 하는 역방향 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="80ed0-719">뒤로 링크: <strong>링크 ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="80ed0-720">이 후방 링크에 해당 하는 전방 링크는 <strong>msRTCSIP-DefaultLocationProfileLink</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="80ed0-721">이 뒤로 링크 특성은 풀 및 중재 서버만 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-722">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-723">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="80ed0-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="80ed0-725">이 특성은 서버의 버전 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="80ed0-726">이 버전 번호는 모든 서버 역할에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-726">This version number applies to all server roles.</span></span> <span data-ttu-id="80ed0-727">이는 각 공식 제품 릴리스로 증가 하는 monotonously 증가 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="80ed0-728">가능한 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-729">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="80ed0-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="80ed0-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="80ed0-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="80ed0-731">                 실시간 통신 서버 2005 (SP1)</span><span class="sxs-lookup"><span data-stu-id="80ed0-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="80ed0-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="80ed0-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="80ed0-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="80ed0-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="80ed0-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="80ed0-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="80ed0-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80ed0-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-736">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="80ed0-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="80ed0-738">정수 형식의이 단일 값 특성은 다음과 같이 <strong>msDS-SourceObjectDN</strong> 가 가리키는 개체의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-739">null | 0x00000001: 다른 포리스트의 Windows NT Server principal 사용자 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="80ed0-740">다음 특성은 메일 그룹 확장에 대해 다른 포리스트의 그룹 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="80ed0-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="80ed0-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="80ed0-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="80ed0-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="80ed0-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="80ed0-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="80ed0-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="80ed0-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="80ed0-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="80ed0-746">0x90000000: 같은 포리스트나 다른 포리스트의 자동 전화 교환 또는 구독자 액세스 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-747">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-748">msRTCSIP-SubscriptionAuthRequired (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-749">실시간 통신 서버 2003의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="80ed0-750">Live Communications Server 2005에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="80ed0-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="80ed0-752">이 특성을 사용 하면 사용자 또는 연락처 개체를 Lync 서버 풀 간에 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="80ed0-753">중앙 포리스트 토폴로지에서는 사용자 개체가 아닌 contact 개체를 SIP로 설정 하기 때문에이 특성은 contact 클래스에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="80ed0-754">유효한 값은 사용자가 이동할 대상 Standard Edition server 또는 프런트 엔드 풀의 DN입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-755">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-756">msRTCSIP-TargetPhoneNumber (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-757">이 단일 값 문자열 특성에는 <strong>msRTCSIP</strong>에 정의 된 특정 게이트웨이로 라우팅하기 위한 전화 번호 패턴 또는 범위가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-758">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="80ed0-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="80ed0-760">이 특성은 Lync Server 사용자의 대상 정책에 대 한 이름-값 쌍을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-761">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="80ed0-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="80ed0-763">이 특성은 테 넌 트에 대 한 고유 식별자를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-764">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-765">msRTCSIP-번역 (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-766">이 특성은 Lync Server의 음성 기능에 사용 되며, 일치 하는 항목을 찾은 경우, 전화를 건 번호에 적용할 번역 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-767">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="80ed0-768">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-769">msRTCSIP-Trustedm데이터</span><span class="sxs-lookup"><span data-stu-id="80ed0-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-770">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-771">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-772">msRTCSIP-Trustedm의 Fqdn</span><span class="sxs-lookup"><span data-stu-id="80ed0-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-773">이 특성은 MCU의 FQDN을 포함 하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="80ed0-774">이것은 단일 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-774">This is a single-valued attribute.</span></span> <span data-ttu-id="80ed0-775">각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-776">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-777">msRTCSIP Proxydata</span><span class="sxs-lookup"><span data-stu-id="80ed0-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-778">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-779">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-780">msRTCSIP-을 (를)로 하는 Proxyfqdn</span><span class="sxs-lookup"><span data-stu-id="80ed0-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-781">이 특성은 프록시 서버를 실행 하는 서버의 FQDN을 포함 하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="80ed0-782">이 특성은 단일 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-782">This attribute is single-valued.</span></span> <span data-ttu-id="80ed0-783">각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-784">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-785">msRTCSIP Serverdata</span><span class="sxs-lookup"><span data-stu-id="80ed0-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-786">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-787">msRTCSIP-로 비트 하는 Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="80ed0-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-788">이 특성은 신뢰할 수 있는 서버의 FQDN을 나타내는 단일 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-789">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-790">msRTCSIP Serverversion</span><span class="sxs-lookup"><span data-stu-id="80ed0-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="80ed0-791">이 특성은 신뢰 된 서버 목록에 있는 서버의 버전 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="80ed0-792">가능한 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="80ed0-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="80ed0-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="80ed0-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="80ed0-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="80ed0-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="80ed0-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="80ed0-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="80ed0-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="80ed0-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="80ed0-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80ed0-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-799">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-800">msRTCSIP-(비트)로가는 플래그</span><span class="sxs-lookup"><span data-stu-id="80ed0-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="80ed0-801">이 특성은 신뢰 된 서비스에 대해 사용 하도록 설정 된 옵션을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-802">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="80ed0-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="80ed0-804">이 다중 값 특성에는 미디어 릴레이 인증 서비스와 같이 신뢰할 수 있는 서비스 개체를 참조 하는 DN (고유 이름) 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="80ed0-805">미디어 릴레이 인증 서비스 (A/V 회의 서비스를 실행 하는 Edge 서버를 물리적으로 collocated)는 원격 사용자를 위한 오디오 시나리오를 지원 하기 위해 풀에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="80ed0-806">이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-ServerBL</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-807">UC</span><span class="sxs-lookup"><span data-stu-id="80ed0-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-808">msRTCSIP-(와)로 이루어진 Serviceport</span><span class="sxs-lookup"><span data-stu-id="80ed0-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="80ed0-809">이 특성은이 GRUU 서비스에 연결 하는 데 사용 되는 포트 번호를 정의 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-810">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-811">msRTCSIP의로이는 Servicetype</span><span class="sxs-lookup"><span data-stu-id="80ed0-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="80ed0-812">이 특성은 해당 속성이 나타내는 GRUU 서비스의 형식을 정의 하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="80ed0-813">유효한 GRUU 서비스 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="80ed0-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="80ed0-815">게이트웨이와</span><span class="sxs-lookup"><span data-stu-id="80ed0-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="80ed0-816">MRAS (미디어 릴레이 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="80ed0-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="80ed0-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="80ed0-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="80ed0-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="80ed0-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-819">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="80ed0-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-821">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-822">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="80ed0-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="80ed0-824">이 특성은 Lync Server Web Services를 실행 하는 IIS의 FQDN을 포함 하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="80ed0-825">이것은 단일 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-825">This is a single-valued attribute.</span></span> <span data-ttu-id="80ed0-826">각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-827">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-828">msRTCSIP 플래그 (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-829">이 특성은 모든 사용자 또는 연락처 개체에 전역적으로 사용할 수 있는 다른 UC 옵션을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="80ed0-830">이 특성은 정수 형식의 비트 마스크 값입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="80ed0-831">각 옵션은 비트의 현재 상태에 따라 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="80ed0-832">가능한 유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-833">4: Useperuser작업 정책 (비트 위치 2)</span><span class="sxs-lookup"><span data-stu-id="80ed0-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="80ed0-834">이 비트가 설정 되 면 사용자 당 UC 정책이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-835">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-836">msRTCSIP 정책 (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-837">이 단일 값 특성은 관리자가이 사용자에 대해 할당 한 UC 정책의 DN (고유 이름)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-838">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-839">msRTCSIP Domainlist (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="80ed0-840">이 특성은 SIP 사용 가능 사용자를 호스팅하는 포리스트의 모든 도메인 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="80ed0-841">기본값은 포리스트의 모든 도메인이 SIP를 사용할 수 있음을 나타내는 빈 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="80ed0-842">유효한 값은 개별 도메인의 도메인 이름을 나타내는 여러 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-843">실시간 통신 서버 2005의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="80ed0-844">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="80ed0-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="80ed0-846">이 특성은 사용자가 현재 Lync Server를 사용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-847">UserExtension msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="80ed0-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="80ed0-848">이 다중 값 특성에는 &quot;name = value 형식의 이름-값 쌍 목록이 포함 됩니다. &quot; 이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-849">실시간 통신 서버 2005 (SP1)에서 새로 만들기.</span><span class="sxs-lookup"><span data-stu-id="80ed0-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="80ed0-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="80ed0-851">이 특성은 위치 프로필 개체를 가리키는 DN (고유 이름)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-852">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="80ed0-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="80ed0-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="80ed0-854">이 특성은 사용자 정책에 대 한 이름-값 쌍을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-855">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="80ed0-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="80ed0-857">이는 서로 다른 유형의 전역 사용자 정책을 가리키는 binary (DN_WITH_BINARY)를 사용 하 여 고유 이름 목록을 포함 하는 다중 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="80ed0-858">이진 부분은 DN 부분이 가리키는 정책의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="80ed0-859">유효한 이진 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-860">0x00000001: 모임 정책</span><span class="sxs-lookup"><span data-stu-id="80ed0-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="80ed0-861">0x00000002: UC 정책</span><span class="sxs-lookup"><span data-stu-id="80ed0-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="80ed0-862">0x00000005: 현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="80ed0-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-863">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="80ed0-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="80ed0-865">SIP 라우팅 그룹 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="80ed0-866">같은 그룹의 사용자가 동일한 프런트 엔드 서버에 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-867">Lync Server 2013의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="80ed0-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="80ed0-869">다중값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="80ed0-870">이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-871">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="80ed0-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="80ed0-873">이 단일 값 특성은 웹 구성 요소가 속해 있는 풀 또는 Standard Edition 서버를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="80ed0-874">전달 링크: <strong>링크 ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="80ed0-875">이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-WebComponentsServers</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-876">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="80ed0-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="80ed0-878">이 특성은 고유 이름에 대 한 다중값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="80ed0-879">이 특성에는이 풀과 연결 된 모든 웹 서버의 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="80ed0-880">뒤로 링크: <strong>링크 ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="80ed0-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="80ed0-881">이 후방에 해당 하는 전방 링크는 <strong>msRTCSIP-WebComponentsPoolAddress</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-882">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-883">msRTCSIP-WMIInstanceId (구식)</span><span class="sxs-lookup"><span data-stu-id="80ed0-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="80ed0-884">실시간 통신 서버 2003의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="80ed0-885">Live Communications Server 2005에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="80ed0-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="80ed0-887">전화 통신에서이 기존 Active Directory 특성을 사용 하 여 전화기에 대 한 대체 TCP/IP 주소 목록을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-888">Windows Server 2008 운영 체제의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="80ed0-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="80ed0-890">이 기존 Active Directory 특성은 연락처 개체만을 위해 Lync Server의 음성 구성 요소에 사용 되며, 통합 메시징 자동 전화 교환 및 구독자 액세스 번호로의 라우팅에는 해당 용도로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="80ed0-891">무조건 통화 전달 주소는이 다중값 특성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="80ed0-892">이 계정은 자동 전화 교환 및 구독자 액세스의 특정 목적을 위해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="80ed0-893">관리자가이 계정의 특성을 수정 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-894">Windows 2000 운영 체제의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80ed0-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="80ed0-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="80ed0-896">이 기존 Active Directory 다중 값 특성은 Windows 2000에서 도입 된 기본 Active Directory 스키마의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="80ed0-897">이 특성에는 사용자의 전자 메일에 대 한 다양 한 X400, X500 및 SMTP 주소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="80ed0-898">Live Communications Server 2003 이상에서는 &quot;sip:&quot; 태그를 사용 하 여 사용자의 sip URI가이 목록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="80ed0-899">다음 응용 프로그램은 사용자의 SIP URI를이 특성에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="80ed0-900">Microsoft Office Outlook 2003 메시징 및 공동 작업 클라이언트</span><span class="sxs-lookup"><span data-stu-id="80ed0-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="80ed0-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="80ed0-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80ed0-902">Windows 2000 운영 체제의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80ed0-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="80ed0-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="80ed0-904">이 기존 Active Directory 특성은 사용자의 전화 번호를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ed0-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="80ed0-905">Windows 2000 운영 체제의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="80ed0-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

