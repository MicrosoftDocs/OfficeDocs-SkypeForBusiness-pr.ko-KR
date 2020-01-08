---
title: 'Lync Server 2013: 스키마 클래스 및 설명'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39bd0b3ff3c99e7de731f94eda0d3775ac4bd7cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="be5d1-102">Lync Server 2013의 스키마 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="be5d1-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be5d1-103">_**마지막으로 수정한 주제:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="be5d1-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="be5d1-104">이 섹션에서는 Lync Server 2013에서 사용 되는 모든 스키마 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="be5d1-105">스키마 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="be5d1-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be5d1-106">클래스만</span><span class="sxs-lookup"><span data-stu-id="be5d1-106">Class</span></span></th>
<th><span data-ttu-id="be5d1-107">설명</span><span class="sxs-lookup"><span data-stu-id="be5d1-107">Description</span></span></th>
<th><span data-ttu-id="be5d1-108">메모</span><span class="sxs-lookup"><span data-stu-id="be5d1-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-109">메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="be5d1-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="be5d1-110">Exchange UM (통합 메시징) 전자 메일 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-111">이 보조 클래스는 Exchange UM과 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-112">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="be5d1-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="be5d1-113">이 클래스는 여러 응용 프로그램 대화 상대에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-114">Microsoft Office Communications Server 2007 R2의 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-115">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="be5d1-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="be5d1-116">이 클래스는 통합 커뮤니케이션 응용 프로그램 서비스 (c)의 인스턴스에 대 한 서비스 제어 지점의 항목을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="be5d1-117">Office Communications Server 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-118">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="be5d1-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="be5d1-119">이 클래스는 특정 풀과 해당 응용 프로그램 서비스의 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-120">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-121">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="be5d1-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="be5d1-122">이 보조 클래스에는 응용 프로그램 서비스의 인스턴스에 대 한 설정을 나타내는 특성이 msRTCSIP-ApplicationServer에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-123">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-124">msRTCSIP-보관 (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-125">이 보조 클래스를 msRTCSIP-GlobalContainer에는 보관에 관련 된 모든 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-126">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-127">msRTCSIP-ArchivingServer (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-128">이 클래스는 단일 인스턴트 메시징 보관 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-128">This class represents a single instant messaging Archiving Server.</span></span> <span data-ttu-id="be5d1-129">이 클래스의 인스턴스는 메신저 대화 서비스가 설치 된 컴퓨터와 같은 인스턴트 메시징 보관 서버로 컴퓨터가 활성화 될 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-129">An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-130">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-131">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="be5d1-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="be5d1-132">이 클래스는 회의 디렉터리의 여러 인스턴스에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-133">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-134">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="be5d1-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="be5d1-135">이 클래스는 특정 회의 디렉터리에 대 한 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-136">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-137">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="be5d1-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="be5d1-138">컴퓨터를 Lync Server를 실행 하는 서버로 지정 하는 SCP (일반 서비스 제어 지점)</span><span class="sxs-lookup"><span data-stu-id="be5d1-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-139">Lync 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-140">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="be5d1-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="be5d1-141">이 보조 클래스에는 Microsoft Lync Web App 은행에 대 한 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-142">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-143">msRTCSIP-도메인</span><span class="sxs-lookup"><span data-stu-id="be5d1-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="be5d1-144">이 클래스에는 SIP 등록자의 구성 된 도메인을 정의 하는 특성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-145">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="be5d1-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="be5d1-146">이 클래스 컨테이너는 단일 액세스에 지 서비스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="be5d1-147">경계 네트워크에 액세스에 지 서비스가 배포 되 고 일반적으로 경계 네트워크에서 Active Directory 도메인 서비스 액세스를 허용 하지 않기 때문에 액세스에 지 서비스 인스턴스가 인트라넷의 Active Directory 네트워크에 가입 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="be5d1-148">따라서 Access 프록시는 AD DS에 자동으로 등록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="be5d1-149">관리자는 AD DS에 각 액세스에 지 서비스 인스턴스의 존재를 수동으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-150">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="be5d1-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="be5d1-151">MsRTCSIP-MCU에 대 한이 보조 클래스는 회의 서버의 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-152">Microsoft Office 통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-153">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="be5d1-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="be5d1-154">MsRTCSIP-MediationServer에 대 한이 보조 클래스는 중재 서버의 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-155">Office Communications Server 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-156">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="be5d1-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="be5d1-157">MsRTCSIP에 대 한이 보조 클래스는 SIP 서버 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-158">msRTCSIP-페더레이션</span><span class="sxs-lookup"><span data-stu-id="be5d1-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="be5d1-159">MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 페더레이션과 관련 된 모든 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-160">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="be5d1-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="be5d1-161">이 클래스에는 Lync Server 배포 전체에 적용 되는 모든 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-162">msRTCSIP-GlobalUserPolicy (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-163">이 클래스는 단일 Office 커뮤니케이션 서버 모임 정책을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-164">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-165">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="be5d1-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="be5d1-166">로컬 전역 토폴로지 설정 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-167">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-168">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="be5d1-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="be5d1-169">전역 토폴로지 설정 개체를 보관할 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-170">Lync Server 2010의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-171">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="be5d1-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="be5d1-172">이 클래스는 위치 정규화 규칙의 인스턴스를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-173">msRTCSIP-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="be5d1-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="be5d1-174">이 클래스는 회의 수행자 응용 프로그램에서 생성 되며 전화 회의 전화 번호를 지역별로 분류 하는 데 사용 되는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-175">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-176">msRTCSIP-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="be5d1-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="be5d1-177">이 클래스는 위치 대화 매핑의 여러 인스턴스에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-178">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-179">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="be5d1-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="be5d1-180">이 클래스는 특정 위치 프로필을 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-181">msRTCSIP-LocationProfiles (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-182">이 클래스는 여러 위치 프로필에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-183">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-184">msRTCSIP-LocalNormalizations (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-185">이 클래스는 여러 로컬 정규화 규칙에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-186">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-187">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="be5d1-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="be5d1-188">이 클래스는 단일 회의 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-189">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-190">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="be5d1-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="be5d1-191">이 클래스는 여러 msRTCSIP MCUFactory 클래스를 보유 하 고 있으며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-192">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-193">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="be5d1-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="be5d1-194">이 클래스는 단일 미디어 형식에 대 한 회의 서버 팩토리를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-194">This class is a container representing a Conferencing Server Factory for a single medium type.</span></span> <span data-ttu-id="be5d1-195">이 클래스의 인스턴스는이 특정 유형 및 공급 업체에 대 한 첫 번째 회의 서버가 활성화 될 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-195">An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-196">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-197">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="be5d1-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="be5d1-198">이 클래스는 특정 풀과 해당 하는 회의 서버 팩터리에 대 한 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-199">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-200">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="be5d1-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="be5d1-201">이 클래스는 중재 서버에 대 한 서비스 제어 지점의 항목을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-202">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-203">msRTCSIP-모임 (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-204">MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 구성 가능한 모임 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-205">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-206">msRTCSIP-이동성</span><span class="sxs-lookup"><span data-stu-id="be5d1-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="be5d1-207">전역 이동성 설정을 저장 하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="be5d1-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="be5d1-209">이 클래스에는 단일 모니터링 서버의 설정을 나타내는 특성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-210">통신 서버 2007 R2의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="be5d1-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-211">msRTCSIP-PhoneRoute (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-212">이 클래스는 게이트웨이 또는 게이트웨이 집합에 대 한 최소 순위의 경로의 인스턴스를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-212">This class is a container representing an instance of a least cost route to a gateway or set of gateways.</span></span> <span data-ttu-id="be5d1-213">이 정보는 모든 엔터프라이즈 풀 또는 표준 버전을 실행 하는 서버에서 가장 비용 효율적인 방법으로 PSTN (공개 통신 네트워크)로 나가는 호출을 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-213">This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-214">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-215">msRTCSIP-PhoneRoutes (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-216">이 클래스는 최소 순위의 여러 경로에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-217">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-218">msRTCSIP-정책 (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-219">이 클래스는 여러 Lync Server 정책 클래스를 보유 하며 특성 자체는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-220">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-221">msRTCSIP-풀</span><span class="sxs-lookup"><span data-stu-id="be5d1-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="be5d1-222">이 클래스는 단일 Lync Server 풀을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-223">msRTCSIP-풀</span><span class="sxs-lookup"><span data-stu-id="be5d1-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="be5d1-224">이 클래스는 여러 Lync Server 풀을 보유 하며 특성 자체는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-225">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="be5d1-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="be5d1-226">이 클래스는 풀의 서비스 제어 포인트 서비스 제어점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-226">This class represents the service control pointservice control point of a pool.</span></span> <span data-ttu-id="be5d1-227">풀에 호스팅되는 사용자의 msRTCSIP-PrimaryHomeServer 특성 점이이 클래스의 인스턴스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-227">Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-228">msRTCSIP-현재 상태</span><span class="sxs-lookup"><span data-stu-id="be5d1-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="be5d1-229">전역 현재 상태 설정을 저장 하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-230">msRTCSIP-등록자</span><span class="sxs-lookup"><span data-stu-id="be5d1-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="be5d1-231">MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 SIP 등록자 서버에서 유지 관리 하는 사용자 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-232">msRTCSIP-RouteUsage (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-233">이 클래스는 전화 경로 사용의 인스턴스를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-233">This class is a container representing an instance of a phone route usage.</span></span> <span data-ttu-id="be5d1-234">전화 경로 사용 클래스는 특성 필드와 설명 필드로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-234">A phone route usage class consists of an attribute field and a description field.</span></span> <span data-ttu-id="be5d1-235">특성 필드는 사용 유형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-235">The attribute field defines a usage type.</span></span> <span data-ttu-id="be5d1-236">관리자는 설명 필드를 사용 하 여 전화 라우트에이 특성에 대 한 사용량을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-236">The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-237">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-238">msRTCSIP-RouteUsages (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-239">이 클래스는 msRTCSIP-RouteUsage 클래스의 여러 인스턴스를 포함 하며 특성 자체는 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-240">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-241">msRTCSIP-검색</span><span class="sxs-lookup"><span data-stu-id="be5d1-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="be5d1-242">MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 검색 결과 범위를 제한 하 고 제어 하는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-243">msRTCSIP-서버</span><span class="sxs-lookup"><span data-stu-id="be5d1-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="be5d1-244">이 클래스는 Lync Server를 실행 하는 단일 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-245">msRTCSIP-서비스</span><span class="sxs-lookup"><span data-stu-id="be5d1-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="be5d1-246">이 클래스에는 전역 설정 컨테이너 및 msRTCSIP 도메인 개체가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-247">msRTCSIP 된 Mcu</span><span class="sxs-lookup"><span data-stu-id="be5d1-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="be5d1-248">이 클래스에는 신뢰할 수 있는 회의 서버의 설정을 나타내는 특성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-249">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-250">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="be5d1-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="be5d1-251">이 클래스에는 msRTCSIP로 거는 Mcu 클래스의 여러 인스턴스가 저장 되며 특성 자체는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-252">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-253">msRTCSIP 프록시</span><span class="sxs-lookup"><span data-stu-id="be5d1-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="be5d1-254">이 클래스는 여러 msRTCSIP 프록시 클래스를 보유 하며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-255">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-256">msRTCSIP 프록시</span><span class="sxs-lookup"><span data-stu-id="be5d1-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="be5d1-257">이 클래스는 프록시 서버를 실행 하는 서버를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-257">This class is a container representing a server running Proxy Server.</span></span> <span data-ttu-id="be5d1-258">이 클래스의 인스턴스는 AD DS에 연결 된 컴퓨터에서 새 프록시 서버를 활성화할 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-258">An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-259">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-260">msRTCSIP 서버</span><span class="sxs-lookup"><span data-stu-id="be5d1-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="be5d1-261">이 클래스는 신뢰할 수 있는 서버에 대 한 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-262">msRTCSIP 서비스</span><span class="sxs-lookup"><span data-stu-id="be5d1-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="be5d1-263">이 클래스는 전역적으로 라우팅할 수 있는 GRUU (사용자 에이전트 URI) 주소를 사용 하 여 라우팅할 수 있는 서비스를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="be5d1-264">이 클래스의 인스턴스는 Lync Server에서 신뢰 하는 새 서버가 활성화 될 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="be5d1-265">이 신뢰할 수 있는 서버는 Active Directory 도메인에 가입 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-266">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-267">msRTCSIP 서비스</span><span class="sxs-lookup"><span data-stu-id="be5d1-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="be5d1-268">이 클래스는 여러 GRUU 서버에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-269">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-270">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="be5d1-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="be5d1-271">이 클래스에는 신뢰할 수 있는 웹 구성 요소에 대 한 설정을 나타내는 특성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-272">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-273">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="be5d1-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="be5d1-274">이 클래스는 msRTCSIP Webcomponentserver 클래스의 여러 인스턴스를 보유 하며 특성 자체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-275">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-276">msRTCSIP-UnifiedCommunications (구식)</span><span class="sxs-lookup"><span data-stu-id="be5d1-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="be5d1-277">MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 통합 커뮤니케이션 관련 특성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-278">Lync Server 2010에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-279">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="be5d1-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="be5d1-280">이 클래스는 IIS (Internet Information Server)에 대 한 서비스 제어 포인트 서비스 제어 지점을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-280">This class holds the service control pointservice control point for Internet Information Server (IIS).</span></span> <span data-ttu-id="be5d1-281">서버를 웹 구성 요소 서버로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-281">It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-282">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be5d1-283">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="be5d1-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="be5d1-284">이 클래스는 특정 풀과 풀에서 사용할 웹 구성 요소에 대 한 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-285">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be5d1-286">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="be5d1-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="be5d1-287">MsRTCSIP 구성 요소에 대 한이 보조 클래스는 웹 구성 요소 설정을 나타내는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5d1-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="be5d1-288">통신 서버 2007의 새로운 방법.</span><span class="sxs-lookup"><span data-stu-id="be5d1-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

