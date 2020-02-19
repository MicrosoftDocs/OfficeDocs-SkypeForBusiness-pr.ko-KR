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
ms.openlocfilehash: 1f6a48780535960a71a06f2edfcb6c2b8a95d999
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="df1c7-102">Lync Server 2013의 등록 보기</span><span class="sxs-lookup"><span data-stu-id="df1c7-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df1c7-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="df1c7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="df1c7-104">등록 보기에는 사용자 등록에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="df1c7-105">이 보기는 Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df1c7-106">열</span><span class="sxs-lookup"><span data-stu-id="df1c7-106">Column</span></span></th>
<th><span data-ttu-id="df1c7-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="df1c7-107">Data Type</span></span></th>
<th><span data-ttu-id="df1c7-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="df1c7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="df1c7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="df1c7-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-111">Time of session request.</span></span> <span data-ttu-id="df1c7-112">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="df1c7-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="df1c7-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-115">int</span><span class="sxs-lookup"><span data-stu-id="df1c7-115">int</span></span></p></td>
<td><p><span data-ttu-id="df1c7-116">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-116">ID number to identify the session.</span></span> <span data-ttu-id="df1c7-117">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="df1c7-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="df1c7-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-120">datetime</span><span class="sxs-lookup"><span data-stu-id="df1c7-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="df1c7-121">등록이 발생한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-122"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="df1c7-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-124">등록한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-125"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-127">등록한 사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="df1c7-128">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="df1c7-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-129"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-131">등록한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-131">Tenant of the user who registered.</span></span> <span data-ttu-id="df1c7-132">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df1c7-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-134">고유</span><span class="sxs-lookup"><span data-stu-id="df1c7-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="df1c7-135">등록한 사용자의 끝점에 대한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-137">고유</span><span class="sxs-lookup"><span data-stu-id="df1c7-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="df1c7-138">동일 사용자 및 동일 끝점이 포함된 등록을 구분하는 데 사용되는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-140">datetime</span><span class="sxs-lookup"><span data-stu-id="df1c7-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="df1c7-141">등록 취소가 발생한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-144">등록 취소에 대한 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-145"><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.clientversion</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-147">등록한 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-149">int</span><span class="sxs-lookup"><span data-stu-id="df1c7-149">int</span></span></p></td>
<td><p><span data-ttu-id="df1c7-150">등록한 사용자가 사용한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-150">Client used by the user who registered.</span></span> <span data-ttu-id="df1c7-151">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df1c7-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="df1c7-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-154">등록한 사용자가 사용한 클라이언트의 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-155"><strong>Address</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-157">사용자가 등록한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-157">IP Address the user registered with.</span></span> <span data-ttu-id="df1c7-158">IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="df1c7-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-p108">SIP 대화 ID입니다. 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="df1c7-163">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="df1c7-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-165">int</span><span class="sxs-lookup"><span data-stu-id="df1c7-165">int</span></span></p></td>
<td><p><span data-ttu-id="df1c7-p109">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-170">int</span><span class="sxs-lookup"><span data-stu-id="df1c7-170">int</span></span></p></td>
<td><p><span data-ttu-id="df1c7-171">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-172"><strong>등록자</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-174">등록자의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-175"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-177">세션에 대해 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-180">등록한 사용자가 사용한 에지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-182">비트만</span><span class="sxs-lookup"><span data-stu-id="df1c7-182">bit</span></span></p></td>
<td><p><span data-ttu-id="df1c7-183">사용자가 내부 네트워크에서 로그온했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-185">비트만</span><span class="sxs-lookup"><span data-stu-id="df1c7-185">bit</span></span></p></td>
<td><p><span data-ttu-id="df1c7-186">등록 시에 UserService를 사용할 수 있었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-188">비트만</span><span class="sxs-lookup"><span data-stu-id="df1c7-188">bit</span></span></p></td>
<td><p><span data-ttu-id="df1c7-189">기본 등록자로 등록이 수행되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-191">bigint</span><span class="sxs-lookup"><span data-stu-id="df1c7-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="df1c7-192">등록된 장치의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df1c7-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-195">등록된 장치의 제조업체입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="df1c7-196">자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="df1c7-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df1c7-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="df1c7-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="df1c7-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df1c7-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df1c7-199">등록된 장치의 하드웨어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c7-199">Hardware version of the device registered.</span></span> <span data-ttu-id="df1c7-200">자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="df1c7-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

