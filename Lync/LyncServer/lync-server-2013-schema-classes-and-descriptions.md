---
title: 'Lync Server 2013: 스키마 클래스 및 설명'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a7da8bf5781de56f89e19359168530597ef977
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="7399d-102">Lync Server 2013의 스키마 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="7399d-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7399d-103">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="7399d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="7399d-104">이 섹션에서는 Lync Server 2013에서 사용 되는 모든 스키마 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="7399d-105">스키마 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="7399d-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7399d-106">클래스</span><span class="sxs-lookup"><span data-stu-id="7399d-106">Class</span></span></th>
<th><span data-ttu-id="7399d-107">설명</span><span class="sxs-lookup"><span data-stu-id="7399d-107">Description</span></span></th>
<th><span data-ttu-id="7399d-108">설명</span><span class="sxs-lookup"><span data-stu-id="7399d-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7399d-109">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="7399d-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="7399d-110">Exchange UM (통합 메시징) 전자 메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="7399d-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="7399d-111">이 보조 클래스는 Exchange UM과 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-112">Msrtcsip-gateways-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="7399d-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="7399d-113">이 클래스는 여러 응용 프로그램 대화 상대에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-114">Microsoft Office Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-115">Msrtcsip-gateways-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="7399d-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="7399d-116">이 클래스는 UCAS(통합 통신 응용 프로그램 서비스) 인스턴스의 서비스 제어 지점에 대한 항목을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="7399d-117">Office Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-118">Msrtcsip-gateways-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="7399d-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="7399d-119">이 클래스는 특정 풀에서 해당 응용 프로그램 서비스로의 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="7399d-120">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-121">Msrtcsip-gateways-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="7399d-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="7399d-122">이 보조 클래스는 응용 프로그램 서비스의 인스턴스에 대 한 설정을 나타내는 특성을 보유 합니다 (Msrtcsip-gateways).</span><span class="sxs-lookup"><span data-stu-id="7399d-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="7399d-123">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-124">msRTCSIP-Archive(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-125">msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 보관과 관련된 모든 설정을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="7399d-126">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-127">msRTCSIP-ArchivingServer(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-p101">이 클래스는 단일 인스턴트 메시징 보관 서버를 나타냅니다. 이 클래스의 인스턴스는 컴퓨터(예: 인스턴트 메시징 보관 서비스가 설치된 컴퓨터)가 인스턴트 메시징 보관 서버로 활성화될 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="7399d-130">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-131">Msrtcsip-gateways-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="7399d-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="7399d-132">이 클래스는 전화 회의 디렉터리의 여러 인스턴스에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-133">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-134">Msrtcsip-gateways-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="7399d-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="7399d-135">이 클래스는 특정 전화 회의 디렉터리에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="7399d-136">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-137">Msrtcsip-gateways-Msrtcsip-connectionpoint</span><span class="sxs-lookup"><span data-stu-id="7399d-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="7399d-138">컴퓨터를 Lync Server를 실행 하는 서버로 지정 하는 SCP (일반 서비스 제어 지점)</span><span class="sxs-lookup"><span data-stu-id="7399d-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="7399d-139">Lync 2010의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="7399d-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-140">Msrtcsip-gateways-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="7399d-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="7399d-141">이 보조 클래스에는 Microsoft Lync Web App 은행의 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="7399d-142">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-143">Msrtcsip-gateways-도메인</span><span class="sxs-lookup"><span data-stu-id="7399d-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="7399d-144">이 클래스는 SIP 등록자의 구성된 도메인을 정의하는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-145">Msrtcsip-gateways-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="7399d-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="7399d-146">이 클래스 컨테이너는 단일 액세스에 지 서비스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="7399d-147">액세스에 지 서비스는 경계 네트워크에 배포 되 고, 고객은 일반적으로 경계 네트워크에서 Active Directory 도메인 서비스 액세스를 허용 하지 않으므로 액세스에 지 서비스의 인스턴스가 인트라넷의 Active Directory 네트워크에 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="7399d-148">따라서 액세스 프록시는 자동으로 AD DS에 등록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="7399d-149">관리자는 AD DS에 각 액세스에 지 서비스 인스턴스가 있는지 여부를 수동으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-150">Msrtcsip-gateways-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="7399d-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="7399d-151">msRTCSIP-MCU에 대한 이 보조 클래스는 회의 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="7399d-152">Microsoft Office Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-153">Msrtcsip-gateways-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="7399d-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="7399d-154">msRTCSIP-MediationServer에 대한 이 보조 클래스는 중재 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="7399d-155">Office Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-156">Msrtcsip-gateways-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="7399d-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="7399d-157">msRTCSIP-Server에 대한 이 보조 클래스는 SIP 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-158">Msrtcsip-gateways-페더레이션</span><span class="sxs-lookup"><span data-stu-id="7399d-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="7399d-159">msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 페더레이션과 관련된 모든 설정을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-160">Msrtcsip-gateways-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="7399d-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="7399d-161">이 클래스에는 Lync Server 배포 전체에 적용 되는 모든 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-162">msRTCSIP-GlobalUserPolicy(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-163">이 클래스는 단일 Office Communications Server meeting policy를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="7399d-164">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-165">Msrtcsip-gateways-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="7399d-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="7399d-166">로컬 전역 토폴로지 설정 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="7399d-167">Lync Server 2010의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="7399d-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-168">Msrtcsip-gateways-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="7399d-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="7399d-169">전역 토폴로지 설정 개체를 포함할 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="7399d-170">Lync Server 2010의 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="7399d-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-171">Msrtcsip-gateways-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="7399d-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="7399d-172">이 클래스는 위치 정규화 규칙의 인스턴스를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-173">Msrtcsip-gateways-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="7399d-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="7399d-174">이 클래스는 회의 전화 교환 응용 프로그램에서 만들어지며 지역별 전화 번호를 분류 하는 데 사용 되는 특성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="7399d-175">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-176">Msrtcsip-gateways-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="7399d-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="7399d-177">이 클래스는 위치 대화 상대 매핑의 여러 인스턴스에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-178">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-179">Msrtcsip-gateways-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="7399d-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="7399d-180">이 클래스는 특정 위치 프로필을 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-181">msRTCSIP-LocationProfiles(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-182">이 클래스는 여러 위치 프로필에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-183">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-184">msRTCSIP-LocalNormalizations(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-185">이 클래스는 여러 로컬 정규화 규칙에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-186">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-187">Msrtcsip-gateways-MCU</span><span class="sxs-lookup"><span data-stu-id="7399d-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="7399d-188">이 클래스는 단일 회의 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="7399d-189">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-190">Msrtcsip-gateways-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="7399d-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="7399d-191">이 클래스는 여러 msRTCSIP-MCUFactory 클래스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-192">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-193">Msrtcsip-gateways-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="7399d-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="7399d-p103">이 클래스는 단일 미디어 유형에 대한 회의 서버 센터를 나타내는 컨테이너입니다. 이 특정 유형 및 공급업체에 대한 첫 번째 회의 서버가 활성화될 경우 이 클래스의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="7399d-196">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-197">Msrtcsip-gateways-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="7399d-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="7399d-198">이 클래스는 특정 풀에서 해당 회의 서버 센터까지의 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="7399d-199">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-200">Msrtcsip-gateways-MediationServer</span><span class="sxs-lookup"><span data-stu-id="7399d-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="7399d-201">이 클래스는 중재 서버의 서비스 제어 지점에 대한 항목을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="7399d-202">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-203">msRTCSIP-Meeting(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-204">msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 구성 가능한 모임 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="7399d-205">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-206">Msrtcsip-gateways-모바일</span><span class="sxs-lookup"><span data-stu-id="7399d-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="7399d-207">전역 모바일 설정을 저장하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-208">Msrtcsip-gateways-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="7399d-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="7399d-209">이 클래스는 단일 모니터링 서버에 대 한 설정을 나타내는 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="7399d-210">Communications Server 2007 r 2의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-211">msRTCSIP-PhoneRoute(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-p104">이 클래스는 특정 게이트웨이 또는 게이트웨이 집합에 대한 최소 비용 경로의 인스턴스를 나타내는 컨테이너입니다. 모든 엔터프라이즈 풀 또는 Standard Edition을 실행하는 서버는 가장 비용 효과적인 방법으로 발신 전화를 PSTN(공중 전화망)으로 라우팅하기 위해 이 정보를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="7399d-214">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-215">msRTCSIP-PhoneRoutes(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-216">이 클래스는 여러 최소 비용 경로에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-217">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-218">msRTCSIP-Policies(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-219">이 클래스는 여러 Lync Server 정책 클래스를 포함 하며 자체적으로 특성을 포함 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-220">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-221">Msrtcsip-gateways-풀</span><span class="sxs-lookup"><span data-stu-id="7399d-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="7399d-222">이 클래스는 단일 Lync Server 풀을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-223">Msrtcsip-gateways-풀</span><span class="sxs-lookup"><span data-stu-id="7399d-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="7399d-224">이 클래스는 여러 Lync Server 풀을 포함 하며 자체적으로 특성을 포함 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-225">Msrtcsip-gateways-PoolService</span><span class="sxs-lookup"><span data-stu-id="7399d-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="7399d-p105">이 클래스는 풀의 서비스 제어 지점을 나타냅니다. 풀에서 호스팅되는 사용자는 이 클래스의 인스턴스를 가리키는 msRTCSIP-PrimaryHomeServer 특성을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-228">Msrtcsip-gateways-현재 상태</span><span class="sxs-lookup"><span data-stu-id="7399d-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="7399d-229">전역 현재 상태 설정을 저장하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-230">Msrtcsip-gateways-등록자</span><span class="sxs-lookup"><span data-stu-id="7399d-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="7399d-231">msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 SIP 등록자 서버에서 유지 관리하는 사용자 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-232">msRTCSIP-RouteUsage(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-p106">이 클래스는 전화 경로 사용의 인스턴스를 나타내는 컨테이너입니다. 전화 경로 사용 클래스는 특성 필드 및 설명 필드로 구성됩니다. 특정 필드는 사용 유형을 정의합니다. 설명 필드를 사용하면 관리자는 전화 경로에서 이 특성의 사용을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="7399d-237">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-238">msRTCSIP-RouteUsages(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-239">이 클래스는 msRTCSIP-RouteUsage 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-240">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-241">Msrtcsip-gateways-검색</span><span class="sxs-lookup"><span data-stu-id="7399d-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="7399d-242">msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 검색 결과의 범위를 제한 및 제어하는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-243">Msrtcsip-gateways-Server</span><span class="sxs-lookup"><span data-stu-id="7399d-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="7399d-244">이 클래스는 Lync Server를 실행 하는 단일 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-245">Msrtcsip-gateways-서비스</span><span class="sxs-lookup"><span data-stu-id="7399d-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="7399d-246">이 클래스는 전역 설정 컨테이너 및 msRTCSIP-Domain 개체를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-247">Msrtcsip-gateways로이 Mcu</span><span class="sxs-lookup"><span data-stu-id="7399d-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="7399d-248">이 클래스는 트러스트된 회의 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="7399d-249">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-250">Msrtcsip-gateways-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="7399d-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="7399d-251">이 클래스는 msRTCSIP-TrustedMCU 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-252">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-253">Msrtcsip-gateways 프록시</span><span class="sxs-lookup"><span data-stu-id="7399d-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="7399d-254">이 클래스는 여러 msRTCSIP-TrustedProxy 클래스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-255">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-256">Msrtcsip-gateways 프록시</span><span class="sxs-lookup"><span data-stu-id="7399d-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="7399d-p107">이 클래스는 프록시 서버를 실행하는 서버를 나타내는 컨테이너입니다. AD DS에 가입된 컴퓨터에서 새 프록시 서버를 활성화할 경우 이 클래스의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="7399d-259">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-260">Msrtcsip-gateways 서버</span><span class="sxs-lookup"><span data-stu-id="7399d-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="7399d-261">이 클래스는 트러스트된 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-262">Msrtcsip-gateways 서비스</span><span class="sxs-lookup"><span data-stu-id="7399d-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="7399d-263">이 클래스는 GRUU(Globally Routable User Agent URI) 주소를 사용하여 라우팅할 수 있는 트러스트된 서비스를 나타내는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="7399d-264">이 클래스의 인스턴스는 Lync Server에서 신뢰 하는 새 서버가 활성화 될 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="7399d-265">이 트러스트된 서버는 Active Directory 도메인에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="7399d-266">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-267">Msrtcsip-gateways 서비스</span><span class="sxs-lookup"><span data-stu-id="7399d-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="7399d-268">이 클래스는 여러 GRUU 서버에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-269">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-270">Msrtcsip-gateways-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="7399d-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="7399d-271">이 클래스는 트러스트된 웹 구성 요소에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="7399d-272">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-273">Msrtcsip-gateways-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="7399d-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="7399d-274">이 클래스는 msRTCSIP-TrustedWebComponentServer 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="7399d-275">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-276">msRTCSIP-UnifiedCommunications(사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="7399d-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7399d-277">msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 통합 통신과 관련된 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="7399d-278">Lync Server 2010에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-279">Msrtcsip-gateways-WebComponents</span><span class="sxs-lookup"><span data-stu-id="7399d-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="7399d-p109">이 클래스는 IIS(Internet Information Server)의 서비스 제어 지점을 포함하고 있으며 서버를 웹 구성 요소 서버로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="7399d-282">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399d-283">Msrtcsip-gateways-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="7399d-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="7399d-284">이 클래스는 특정 풀에서 해당 풀이 사용하는 웹 구성 요소까지의 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="7399d-285">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399d-286">Msrtcsip-gateways-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="7399d-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="7399d-287">msRTCSIP-WebComponents에 대한 이 보조 클래스는 웹 구성 요소에 대한 설정을 나타내는 특성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7399d-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="7399d-288">Communications Server 2007의 새로운 정보</span><span class="sxs-lookup"><span data-stu-id="7399d-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

