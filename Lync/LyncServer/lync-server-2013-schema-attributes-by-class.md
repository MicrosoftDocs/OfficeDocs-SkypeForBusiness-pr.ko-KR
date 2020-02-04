---
title: 'Lync Server 2013: 클래스별 스키마 특성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 160a148705ececfcbe105dcbc3fca819d4790a0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="a24ea-102">Lync Server 2013의 클래스별 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="a24ea-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a24ea-103">_**마지막으로 수정한 주제:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="a24ea-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="a24ea-104">이 섹션에서는 각 Lync Server 2013 클래스에 포함할 수 있는 스키마 특성과 다른 클래스에 포함 될 수 있는 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a24ea-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="a24ea-105">모든 수업 목록과 해당 설명은 [Lync Server 2013의 스키마 클래스 및 설명을](lync-server-2013-schema-classes-and-descriptions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a24ea-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="a24ea-106">모든 특성 목록과 해당 설명에 대 한 자세한 내용은 [Lync Server 2013의 스키마 특성 및 설명을](lync-server-2013-schema-attributes-and-descriptions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a24ea-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="a24ea-107">클래스별 특성</span><span class="sxs-lookup"><span data-stu-id="a24ea-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a24ea-108">클래스만</span><span class="sxs-lookup"><span data-stu-id="a24ea-108">Class</span></span></th>
<th><span data-ttu-id="a24ea-109">이러한 특성이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24ea-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-110">Contact</span><span class="sxs-lookup"><span data-stu-id="a24ea-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="a24ea-111">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="a24ea-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="a24ea-112">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="a24ea-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="a24ea-113">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="a24ea-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="a24ea-114">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="a24ea-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="a24ea-115">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="a24ea-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="a24ea-116">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="a24ea-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="a24ea-117">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="a24ea-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="a24ea-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="a24ea-119">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="a24ea-120">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="a24ea-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="a24ea-121">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="a24ea-122">msRTCSIP 선</span><span class="sxs-lookup"><span data-stu-id="a24ea-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="a24ea-123">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="a24ea-124">msRTCSIP 플래그</span><span class="sxs-lookup"><span data-stu-id="a24ea-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="a24ea-125">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="a24ea-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="a24ea-126">msRTCSIP-소유자 Urn</span><span class="sxs-lookup"><span data-stu-id="a24ea-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="a24ea-127">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="a24ea-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="a24ea-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="a24ea-129">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="a24ea-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="a24ea-130">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a24ea-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="a24ea-131">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="a24ea-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="a24ea-132">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="a24ea-133">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="a24ea-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="a24ea-134">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="a24ea-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="a24ea-135">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="a24ea-136">UserExtension msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="a24ea-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="a24ea-137">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="a24ea-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="a24ea-138">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="a24ea-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="a24ea-139">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="a24ea-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="a24ea-140">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a24ea-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="a24ea-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a24ea-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-142">메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="a24ea-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="a24ea-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="a24ea-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a24ea-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-145">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="a24ea-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="a24ea-146">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="a24ea-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-147">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="a24ea-148">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="a24ea-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="a24ea-149">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="a24ea-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="a24ea-150">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a24ea-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="a24ea-151">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-152">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="a24ea-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="a24ea-153">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="a24ea-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="a24ea-154">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="a24ea-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="a24ea-155">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="a24ea-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="a24ea-156">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a24ea-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-157">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="a24ea-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="a24ea-158">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="a24ea-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="a24ea-159">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="a24ea-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-160">msRTCSIP-도메인</span><span class="sxs-lookup"><span data-stu-id="a24ea-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="a24ea-161">msRTCSIP-기본값</span><span class="sxs-lookup"><span data-stu-id="a24ea-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="a24ea-162">msRTCSIP-도메인 데이터</span><span class="sxs-lookup"><span data-stu-id="a24ea-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="a24ea-163">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="a24ea-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-164">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="a24ea-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="a24ea-165">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="a24ea-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="a24ea-166">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="a24ea-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-167">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="a24ea-168">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="a24ea-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="a24ea-169">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="a24ea-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="a24ea-170">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-171">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="a24ea-172">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a24ea-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="a24ea-173">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="a24ea-174">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="a24ea-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-175">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="a24ea-176">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="a24ea-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="a24ea-177">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="a24ea-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="a24ea-178">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="a24ea-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="a24ea-179">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-180">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="a24ea-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="a24ea-181">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="a24ea-182">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a24ea-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="a24ea-183">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="a24ea-184">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-185">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="a24ea-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="a24ea-186">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="a24ea-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-187">msRTCSIP-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="a24ea-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="a24ea-188">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a24ea-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="a24ea-189">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="a24ea-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="a24ea-190">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="a24ea-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-191">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="a24ea-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="a24ea-192">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="a24ea-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="a24ea-193">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="a24ea-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="a24ea-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="a24ea-195">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="a24ea-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="a24ea-196">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="a24ea-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="a24ea-197">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="a24ea-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="a24ea-198">msRTCSIP-M가공선</span><span class="sxs-lookup"><span data-stu-id="a24ea-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="a24ea-199">msRTCSIP-MCUVendor 공급 업체</span><span class="sxs-lookup"><span data-stu-id="a24ea-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="a24ea-200">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="a24ea-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="a24ea-201">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-202">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="a24ea-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="a24ea-203">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="a24ea-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-204">msRTCSIP-이동성</span><span class="sxs-lookup"><span data-stu-id="a24ea-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="a24ea-205">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="a24ea-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="a24ea-206">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="a24ea-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-207">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="a24ea-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="a24ea-208">dnsHostName</span></span></p>
<p><span data-ttu-id="a24ea-209">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a24ea-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="a24ea-210">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-211">msRTCSIP-풀</span><span class="sxs-lookup"><span data-stu-id="a24ea-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="a24ea-212">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="a24ea-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="a24ea-213">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="a24ea-214">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="a24ea-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="a24ea-215">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="a24ea-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="a24ea-216">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="a24ea-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="a24ea-217">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="a24ea-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="a24ea-218">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="a24ea-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="a24ea-219">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="a24ea-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="a24ea-220">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="a24ea-221">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="a24ea-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-222">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="a24ea-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="a24ea-223">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="a24ea-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-224">msRTCSIP-현재 상태</span><span class="sxs-lookup"><span data-stu-id="a24ea-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="a24ea-225">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="a24ea-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="a24ea-226">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="a24ea-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-227">msRTCSIP 된 Mcu</span><span class="sxs-lookup"><span data-stu-id="a24ea-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="a24ea-228">msRTCSIP-M가공선</span><span class="sxs-lookup"><span data-stu-id="a24ea-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="a24ea-229">msRTCSIP-MCUVendor 공급 업체</span><span class="sxs-lookup"><span data-stu-id="a24ea-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="a24ea-230">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="a24ea-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="a24ea-231">msRTCSIP-Trustedm데이터</span><span class="sxs-lookup"><span data-stu-id="a24ea-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="a24ea-232">msRTCSIP-Trustedm의 Fqdn</span><span class="sxs-lookup"><span data-stu-id="a24ea-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="a24ea-233">msRTCSIP Serverversion</span><span class="sxs-lookup"><span data-stu-id="a24ea-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-234">msRTCSIP 프록시</span><span class="sxs-lookup"><span data-stu-id="a24ea-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="a24ea-235">msRTCSIP Proxydata</span><span class="sxs-lookup"><span data-stu-id="a24ea-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="a24ea-236">msRTCSIP-을 (를)로 하는 Proxyfqdn</span><span class="sxs-lookup"><span data-stu-id="a24ea-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="a24ea-237">msRTCSIP Serverversion</span><span class="sxs-lookup"><span data-stu-id="a24ea-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-238">msRTCSIP 서버</span><span class="sxs-lookup"><span data-stu-id="a24ea-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="a24ea-239">msRTCSIP Serverdata</span><span class="sxs-lookup"><span data-stu-id="a24ea-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="a24ea-240">msRTCSIP-로 비트 하는 Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="a24ea-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="a24ea-241">msRTCSIP Serverversion</span><span class="sxs-lookup"><span data-stu-id="a24ea-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-242">msRTCSIP 서비스</span><span class="sxs-lookup"><span data-stu-id="a24ea-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="a24ea-243">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a24ea-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="a24ea-244">msRTCSIP-라우팅 가능</span><span class="sxs-lookup"><span data-stu-id="a24ea-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="a24ea-245">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="a24ea-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="a24ea-246">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="a24ea-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="a24ea-247">msRTCSIP-로 비트 하는 Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="a24ea-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="a24ea-248">msRTCSIP Serverversion</span><span class="sxs-lookup"><span data-stu-id="a24ea-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="a24ea-249">msRTCSIP-(비트)로가는 플래그</span><span class="sxs-lookup"><span data-stu-id="a24ea-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="a24ea-250">msRTCSIP-(와)로 이루어진 Serviceport</span><span class="sxs-lookup"><span data-stu-id="a24ea-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="a24ea-251">msRTCSIP의로이는 Servicetype</span><span class="sxs-lookup"><span data-stu-id="a24ea-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-252">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="a24ea-253">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="a24ea-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="a24ea-254">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="a24ea-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="a24ea-255">msRTCSIP Serverversion</span><span class="sxs-lookup"><span data-stu-id="a24ea-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-256">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="a24ea-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="a24ea-257">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="a24ea-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-258">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="a24ea-259">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="a24ea-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="a24ea-260">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="a24ea-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="a24ea-261">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a24ea-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-262">사용자</span><span class="sxs-lookup"><span data-stu-id="a24ea-262">User</span></span></p></td>
<td><p><span data-ttu-id="a24ea-263">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="a24ea-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="a24ea-264">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="a24ea-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="a24ea-265">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="a24ea-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="a24ea-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="a24ea-267">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="a24ea-268">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="a24ea-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="a24ea-269">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="a24ea-270">msRTCSIP 선</span><span class="sxs-lookup"><span data-stu-id="a24ea-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="a24ea-271">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="a24ea-272">msRTCSIP 플래그</span><span class="sxs-lookup"><span data-stu-id="a24ea-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="a24ea-273">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="a24ea-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="a24ea-274">msRTCSIP-소유자 Urn</span><span class="sxs-lookup"><span data-stu-id="a24ea-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="a24ea-275">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="a24ea-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="a24ea-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="a24ea-277">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="a24ea-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="a24ea-278">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="a24ea-279">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="a24ea-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="a24ea-280">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="a24ea-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="a24ea-281">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="a24ea-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="a24ea-282">UserExtension msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="a24ea-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="a24ea-283">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="a24ea-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="a24ea-284">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="a24ea-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="a24ea-285">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="a24ea-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="a24ea-286">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a24ea-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="a24ea-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a24ea-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="a24ea-288">다른 클래스에 포함 된 클래스</span><span class="sxs-lookup"><span data-stu-id="a24ea-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a24ea-289">클래스만</span><span class="sxs-lookup"><span data-stu-id="a24ea-289">Class</span></span></th>
<th><span data-ttu-id="a24ea-290">이 클래스가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24ea-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="a24ea-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="a24ea-292">msRTCSIP-서버</span><span class="sxs-lookup"><span data-stu-id="a24ea-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="a24ea-293">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="a24ea-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="a24ea-294">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="a24ea-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="a24ea-295">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="a24ea-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="a24ea-296">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="a24ea-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="a24ea-297">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="a24ea-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="a24ea-298">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="a24ea-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="a24ea-299">msRTCSIP-서비스</span><span class="sxs-lookup"><span data-stu-id="a24ea-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="a24ea-300">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="a24ea-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="a24ea-301">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="a24ea-302">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-303">msRTCSIP-서비스</span><span class="sxs-lookup"><span data-stu-id="a24ea-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="a24ea-304">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="a24ea-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="a24ea-305">msRTCSIP-풀</span><span class="sxs-lookup"><span data-stu-id="a24ea-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="a24ea-306">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="a24ea-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="a24ea-307">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="a24ea-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="a24ea-308">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="a24ea-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="a24ea-309">msRTCSIP 프록시</span><span class="sxs-lookup"><span data-stu-id="a24ea-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="a24ea-310">msRTCSIP 서비스</span><span class="sxs-lookup"><span data-stu-id="a24ea-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="a24ea-311">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="a24ea-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="a24ea-312">msRTCSIP-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="a24ea-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="a24ea-313">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="a24ea-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="a24ea-314">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-315">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="a24ea-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="a24ea-316">msRTCSIP-도메인</span><span class="sxs-lookup"><span data-stu-id="a24ea-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="a24ea-317">msRTCSIP 서버</span><span class="sxs-lookup"><span data-stu-id="a24ea-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="a24ea-318">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="a24ea-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="a24ea-319">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-320">msRTCSIP-풀</span><span class="sxs-lookup"><span data-stu-id="a24ea-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="a24ea-321">msRTCSIP-풀</span><span class="sxs-lookup"><span data-stu-id="a24ea-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-322">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="a24ea-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="a24ea-323">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="a24ea-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-324">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="a24ea-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="a24ea-325">msRTCSIP 된 Mcu</span><span class="sxs-lookup"><span data-stu-id="a24ea-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-326">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="a24ea-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="a24ea-327">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="a24ea-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-328">msRTCSIP 프록시</span><span class="sxs-lookup"><span data-stu-id="a24ea-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="a24ea-329">msRTCSIP 프록시</span><span class="sxs-lookup"><span data-stu-id="a24ea-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-330">msRTCSIP 서비스</span><span class="sxs-lookup"><span data-stu-id="a24ea-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="a24ea-331">msRTCSIP 서비스</span><span class="sxs-lookup"><span data-stu-id="a24ea-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-332">msRTCSIP-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="a24ea-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="a24ea-333">msRTCSIP-Location연락처 매핑</span><span class="sxs-lookup"><span data-stu-id="a24ea-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24ea-334">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="a24ea-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="a24ea-335">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="a24ea-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24ea-336">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="a24ea-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="a24ea-337">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="a24ea-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

