---
title: 'Lync Server 2013: 등록 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120f0cb40bb3401a327e495a460db400a9359891
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="6da17-102">Lync Server 2013의 등록 보기</span><span class="sxs-lookup"><span data-stu-id="6da17-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6da17-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6da17-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6da17-104">등록 보기에는 사용자 등록에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="6da17-105">이 보기는 Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6da17-106">열</span><span class="sxs-lookup"><span data-stu-id="6da17-106">Column</span></span></th>
<th><span data-ttu-id="6da17-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6da17-107">Data Type</span></span></th>
<th><span data-ttu-id="6da17-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="6da17-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6da17-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="6da17-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="6da17-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-111">Time of session request.</span></span> <span data-ttu-id="6da17-112">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="6da17-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6da17-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-115">int</span><span class="sxs-lookup"><span data-stu-id="6da17-115">int</span></span></p></td>
<td><p><span data-ttu-id="6da17-116">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-116">ID number to identify the session.</span></span> <span data-ttu-id="6da17-117">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="6da17-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6da17-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-120">dmtf</span><span class="sxs-lookup"><span data-stu-id="6da17-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="6da17-121">등록이 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6da17-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6da17-124">등록 된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-127">등록 된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="6da17-128">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6da17-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-129"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-131">등록 된 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-131">Tenant of the user who registered.</span></span> <span data-ttu-id="6da17-132">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6da17-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6da17-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6da17-135">등록 된 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-137">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6da17-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6da17-138">같은 사용자 및 같은 끝점과 관련 된 등록을 구분 하는 데 사용 되는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-140">dmtf</span><span class="sxs-lookup"><span data-stu-id="6da17-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="6da17-141">등록 취소가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-144">등록 취소 이유.</span><span class="sxs-lookup"><span data-stu-id="6da17-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-147">등록 한 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-149">int</span><span class="sxs-lookup"><span data-stu-id="6da17-149">int</span></span></p></td>
<td><p><span data-ttu-id="6da17-150">등록 한 사용자가 사용 하는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6da17-150">Client used by the user who registered.</span></span> <span data-ttu-id="6da17-151">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6da17-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6da17-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6da17-154">등록 하는 사용자가 사용 하는 클라이언트의 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-155"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-157">사용자가 등록 된 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-157">IP Address the user registered with.</span></span> <span data-ttu-id="6da17-158">IPv4 또는 IPv6 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="6da17-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="6da17-161">SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-161">SIP dialog ID.</span></span> <span data-ttu-id="6da17-162">의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-162">The format of the is:</span></span></p>
<p><span data-ttu-id="6da17-163">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="6da17-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-165">int</span><span class="sxs-lookup"><span data-stu-id="6da17-165">int</span></span></p></td>
<td><p><span data-ttu-id="6da17-166">세션 초대에 대 한 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="6da17-167">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="6da17-168">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-170">int</span><span class="sxs-lookup"><span data-stu-id="6da17-170">int</span></span></p></td>
<td><p><span data-ttu-id="6da17-171">SIP 헤더에서 진단 ID를 캡처 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-172"><strong>레지스터</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-174">등록자의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-175"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-177">세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-180">등록 된 사용자가 사용 하는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-182">다소</span><span class="sxs-lookup"><span data-stu-id="6da17-182">bit</span></span></p></td>
<td><p><span data-ttu-id="6da17-183">사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-184"><strong>IsUserServiceAvailable 가능</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-185">다소</span><span class="sxs-lookup"><span data-stu-id="6da17-185">bit</span></span></p></td>
<td><p><span data-ttu-id="6da17-186">등록할 때 UserService를 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-188">다소</span><span class="sxs-lookup"><span data-stu-id="6da17-188">bit</span></span></p></td>
<td><p><span data-ttu-id="6da17-189">등록이 기본 등록자를 사용 하 고 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-191">bigint</span><span class="sxs-lookup"><span data-stu-id="6da17-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="6da17-192">등록 된 디바이스의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da17-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-195">등록 된 디바이스의 제조업체입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="6da17-196">자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6da17-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da17-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="6da17-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="6da17-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6da17-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6da17-199">등록 된 디바이스의 하드웨어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6da17-199">Hardware version of the device registered.</span></span> <span data-ttu-id="6da17-200">자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6da17-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

