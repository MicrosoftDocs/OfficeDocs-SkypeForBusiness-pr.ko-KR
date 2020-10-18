---
title: 'Lync Server 2013: 등록 보기'
description: 'Lync Server 2013: 등록 보기입니다.'
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
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578531"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="7dd42-103">Lync Server 2013의 등록 보기</span><span class="sxs-lookup"><span data-stu-id="7dd42-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dd42-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7dd42-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7dd42-105">등록 보기에는 사용자 등록에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="7dd42-106">이 보기는 Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dd42-107">열</span><span class="sxs-lookup"><span data-stu-id="7dd42-107">Column</span></span></th>
<th><span data-ttu-id="7dd42-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7dd42-108">Data Type</span></span></th>
<th><span data-ttu-id="7dd42-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7dd42-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7dd42-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7dd42-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-112">Time of session request.</span></span> <span data-ttu-id="7dd42-113">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="7dd42-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7dd42-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-116">int</span><span class="sxs-lookup"><span data-stu-id="7dd42-116">int</span></span></p></td>
<td><p><span data-ttu-id="7dd42-117">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-117">ID number to identify the session.</span></span> <span data-ttu-id="7dd42-118">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="7dd42-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7dd42-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-120"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-121">datetime</span><span class="sxs-lookup"><span data-stu-id="7dd42-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="7dd42-122">등록이 발생한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-123"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7dd42-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-125">등록한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-126"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-128">등록한 사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="7dd42-129">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7dd42-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-130"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-132">등록한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-132">Tenant of the user who registered.</span></span> <span data-ttu-id="7dd42-133">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7dd42-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-135">고유</span><span class="sxs-lookup"><span data-stu-id="7dd42-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7dd42-136">등록한 사용자의 끝점에 대한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-137"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-138">고유</span><span class="sxs-lookup"><span data-stu-id="7dd42-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7dd42-139">동일 사용자 및 동일 끝점이 포함된 등록을 구분하는 데 사용되는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-141">datetime</span><span class="sxs-lookup"><span data-stu-id="7dd42-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="7dd42-142">등록 취소가 발생한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-145">등록 취소에 대한 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-146"><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.clientversion</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-148">등록한 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-150">int</span><span class="sxs-lookup"><span data-stu-id="7dd42-150">int</span></span></p></td>
<td><p><span data-ttu-id="7dd42-151">등록한 사용자가 사용한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-151">Client used by the user who registered.</span></span> <span data-ttu-id="7dd42-152">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7dd42-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7dd42-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-155">등록한 사용자가 사용한 클라이언트의 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-156"><strong>Address</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-158">사용자가 등록한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-158">IP Address the user registered with.</span></span> <span data-ttu-id="7dd42-159">IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-161">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="7dd42-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-p108">SIP 대화 ID입니다. 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="7dd42-164">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="7dd42-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-166">int</span><span class="sxs-lookup"><span data-stu-id="7dd42-166">int</span></span></p></td>
<td><p><span data-ttu-id="7dd42-p109">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-170"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-171">int</span><span class="sxs-lookup"><span data-stu-id="7dd42-171">int</span></span></p></td>
<td><p><span data-ttu-id="7dd42-172">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-173"><strong>등록자</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-175">등록자의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-176"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-178">세션에 대해 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-181">등록한 사용자가 사용한 에지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-183">비트만</span><span class="sxs-lookup"><span data-stu-id="7dd42-183">bit</span></span></p></td>
<td><p><span data-ttu-id="7dd42-184">사용자가 내부 네트워크에서 로그온했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-186">비트만</span><span class="sxs-lookup"><span data-stu-id="7dd42-186">bit</span></span></p></td>
<td><p><span data-ttu-id="7dd42-187">등록 시에 UserService를 사용할 수 있었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-189">비트만</span><span class="sxs-lookup"><span data-stu-id="7dd42-189">bit</span></span></p></td>
<td><p><span data-ttu-id="7dd42-190">기본 등록자로 등록이 수행되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-192">bigint</span><span class="sxs-lookup"><span data-stu-id="7dd42-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="7dd42-193">등록된 장치의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd42-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-196">등록된 장치의 제조업체입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="7dd42-197">자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7dd42-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd42-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7dd42-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd42-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7dd42-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd42-200">등록된 장치의 하드웨어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd42-200">Hardware version of the device registered.</span></span> <span data-ttu-id="7dd42-201">자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7dd42-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

