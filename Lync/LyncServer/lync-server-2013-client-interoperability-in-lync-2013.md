---
title: 'Lync Server 2013: Lync 2013 에서 클라이언트 상호 운용성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="44902-102">Lync 2013 에서 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="44902-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44902-103">_**마지막으로 수정한 주제:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="44902-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="44902-104">이 항목에서는 이전 버전의 Lync Server 및 Office Communications Server에서 클라이언트와 함께 사용 하 고 상호 작용 하는 Microsoft Lync Server 2013 클라이언트의 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="44902-105">서버 및 클라이언트 호환성</span><span class="sxs-lookup"><span data-stu-id="44902-105">Server and Client Compatibility</span></span>

<span data-ttu-id="44902-106">다음 표에는 클라이언트 버전과 서버 버전의 지원 되는 조합이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="44902-107">이 표에는 클라이언트가 표시 된 서버에 연결 하려고 할 때 로그인이 지원 되는지 여부가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="44902-108">Lync Server 2013는 이전 클라이언트 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="44902-109">또한 이전 릴리스와 달리 Lync Server 2010는 새로운 Lync 2013 클라이언트를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="44902-110">이를 통해 Lync Server 2010에서 업그레이드 하는 조직이 Lync Server 업그레이드와 독립적으로 새 클라이언트를 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44902-111">클라이언트</span><span class="sxs-lookup"><span data-stu-id="44902-111">Client</span></span></th>
<th><span data-ttu-id="44902-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44902-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="44902-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="44902-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="44902-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="44902-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44902-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="44902-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="44902-116">지원</span><span class="sxs-lookup"><span data-stu-id="44902-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="44902-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="44902-118">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="44902-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="44902-120">지원</span><span class="sxs-lookup"><span data-stu-id="44902-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-121">지원</span><span class="sxs-lookup"><span data-stu-id="44902-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-122">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="44902-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="44902-124">지원</span><span class="sxs-lookup"><span data-stu-id="44902-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-125">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-126">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="44902-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="44902-128">지원</span><span class="sxs-lookup"><span data-stu-id="44902-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-129">지원</span><span class="sxs-lookup"><span data-stu-id="44902-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-130">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-131">Lync 2010 수행자</span><span class="sxs-lookup"><span data-stu-id="44902-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="44902-132">지원</span><span class="sxs-lookup"><span data-stu-id="44902-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-133">지원</span><span class="sxs-lookup"><span data-stu-id="44902-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-134">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-135">Lync 2010 그룹 채팅</span><span class="sxs-lookup"><span data-stu-id="44902-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="44902-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="44902-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="44902-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="44902-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="44902-138">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44902-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="44902-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="44902-140">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-141">지원</span><span class="sxs-lookup"><span data-stu-id="44902-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-142">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-143">Lync 2010 참석자</span><span class="sxs-lookup"><span data-stu-id="44902-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="44902-144">Supported3 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="44902-145">지원</span><span class="sxs-lookup"><span data-stu-id="44902-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-146">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="44902-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="44902-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="44902-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="44902-149">지원</span><span class="sxs-lookup"><span data-stu-id="44902-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-150">지원</span><span class="sxs-lookup"><span data-stu-id="44902-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-151">Microsoft Office Communications Server 2007 R2 전화 교환</span><span class="sxs-lookup"><span data-stu-id="44902-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="44902-152">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-153">지원</span><span class="sxs-lookup"><span data-stu-id="44902-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-154">지원</span><span class="sxs-lookup"><span data-stu-id="44902-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="44902-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="44902-156">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-157">지원</span><span class="sxs-lookup"><span data-stu-id="44902-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-158">지원</span><span class="sxs-lookup"><span data-stu-id="44902-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="44902-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="44902-160">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-161">지원</span><span class="sxs-lookup"><span data-stu-id="44902-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-162">지원</span><span class="sxs-lookup"><span data-stu-id="44902-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-163">Lync Windows 스토어 앱</span><span class="sxs-lookup"><span data-stu-id="44902-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="44902-164">지원</span><span class="sxs-lookup"><span data-stu-id="44902-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-165">지원</span><span class="sxs-lookup"><span data-stu-id="44902-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-166">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="44902-167">1For 세부 정보는 [Lync server 2010, 그룹 채팅 또는 Office Communications server 2007 R2 그룹 채팅에서 Lync server 2013, 영구 채팅 서버로의 마이그레이션을](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44902-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="44902-168">2 Microsoft Lync Server 2010에서 그룹 채팅 기능은 Lync Server 2010 용 타사 신뢰할 수 있는 응용 프로그램, 그룹 채팅 서버에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="44902-169">Lync 2013 클라이언트는 Lync Server 2010, 그룹 채팅에서 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="44902-170">3 Lync Web App 2013는 이제 컴퓨터 오디오 및 비디오를 비롯 한 전체 모임 경험을 제공 하며 Lync 2010 참석자의 교체품으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="44902-171">Lync 2010 참석자는 지원 되지 않는 브라우저 (Internet Explorer 6 또는 Internet Explorer 7) 및 Windows XP를 사용 하는 경우에만 Lync Server 2013에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="44902-172">4 Office Communicator 2007 R2의 현재 상태 및 메신저 기능은 Lync Server 2013와 호환 되지만, 회의 기능은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="44902-173">Office Communications Server 2007 R2에서 마이그레이션하는 동안 Office Communicator 2007 R2는 현재 상태 및 IM 상호 운용성에 적합 하지만 사용자는 lync Web App 2013을 사용 하 여 Lync Server 2013 모임에 참가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="44902-174">제한에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "Lync Server 2010 모임에서 Lync 2013 클라이언트에 대 한 회의 기능 지원"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44902-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="44902-175">클라이언트 간 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="44902-175">Interoperability among Clients</span></span>

<span data-ttu-id="44902-176">Lync Server 2013 릴리스를 사용 하면 다양 한 클라이언트 버전이 피어 투 피어 및 회의 시나리오에서 원활 하 게 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="44902-177">이 섹션에서는 사용자가 다른 버전의 클라이언트 및 서버를 사용 하는 다른 사용자와 상호 작용할 때의 기능 사용 가능성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="44902-178">피어 투 피어 기능 지원</span><span class="sxs-lookup"><span data-stu-id="44902-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="44902-179">피어 투 피어 기능은 서로 다른 버전의 서버와 다른 클라이언트 버전을 사용 하는 사용자에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="44902-180">최종 사용자 환경 및 사용 가능한 기능은 사용자 클라이언트의 기능 및 사용자가 로그인 한 서버의 버전과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="44902-181">즉, 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-181">In other words:</span></span>

  - <span data-ttu-id="44902-182">사용자가 이전 클라이언트를 사용 하 여 Lync Server 2013에 로그인 한 경우에는 사용자가 사용 하는 것과 동일한 환경을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="44902-183">Lync Server 2013에 도입 된 새로운 기능은 사용자의 클라이언트가 업그레이드 될 때까지 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="44902-184">비디오 갤러리 보기, HD 비디오, 업데이트 된 PowerPoint 공유, 모임 입장에서 모든 참석자 오디오 및 비디오 음소거 옵션을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="44902-185">새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한 새로운](lync-server-2013-what-s-new-for-clients.md)기능에 개략적으로 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="44902-186">사용자가 lync 2013 클라이언트를 사용 하 여 Lync Server 2010에 로그인 한 경우 lync server 2010에서 지원 하지 않는 새로운 기능은 사용자가 Lync Server 2013로 이동할 때까지 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="44902-187">다음 표에서는 클라이언트가 Lync Server 2013 또는 Lync Server 2010에 로그인 한 피어 투 피어 세션의 기능 가용성을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44902-188">Lync Web App 및 Lync 2010 참석자는 모임 전용 클라이언트 이며이 표에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44902-189">클라이언트</span><span class="sxs-lookup"><span data-stu-id="44902-189">Client</span></span></th>
<th><span data-ttu-id="44902-190">인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="44902-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="44902-191">현재 상태</span><span class="sxs-lookup"><span data-stu-id="44902-191">Presence</span></span></th>
<th><span data-ttu-id="44902-192">음성</span><span class="sxs-lookup"><span data-stu-id="44902-192">Voice</span></span></th>
<th><span data-ttu-id="44902-193">비디오만</span><span class="sxs-lookup"><span data-stu-id="44902-193">Video</span></span></th>
<th><span data-ttu-id="44902-194">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="44902-194">Application Sharing</span></span></th>
<th><span data-ttu-id="44902-195">파일 전송</span><span class="sxs-lookup"><span data-stu-id="44902-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44902-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="44902-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="44902-197">예</span><span class="sxs-lookup"><span data-stu-id="44902-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-198">예</span><span class="sxs-lookup"><span data-stu-id="44902-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-199">예</span><span class="sxs-lookup"><span data-stu-id="44902-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-200">예</span><span class="sxs-lookup"><span data-stu-id="44902-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-201">예</span><span class="sxs-lookup"><span data-stu-id="44902-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-202">예</span><span class="sxs-lookup"><span data-stu-id="44902-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="44902-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="44902-204">예</span><span class="sxs-lookup"><span data-stu-id="44902-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-205">예</span><span class="sxs-lookup"><span data-stu-id="44902-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-206">예</span><span class="sxs-lookup"><span data-stu-id="44902-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-207">예</span><span class="sxs-lookup"><span data-stu-id="44902-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-208">예</span><span class="sxs-lookup"><span data-stu-id="44902-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-209">예</span><span class="sxs-lookup"><span data-stu-id="44902-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="44902-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="44902-211">예</span><span class="sxs-lookup"><span data-stu-id="44902-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-212">예</span><span class="sxs-lookup"><span data-stu-id="44902-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-213">예</span><span class="sxs-lookup"><span data-stu-id="44902-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-214">예</span><span class="sxs-lookup"><span data-stu-id="44902-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-215">예</span><span class="sxs-lookup"><span data-stu-id="44902-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-216">예</span><span class="sxs-lookup"><span data-stu-id="44902-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-217">Lync 2010 수행자</span><span class="sxs-lookup"><span data-stu-id="44902-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="44902-218">예</span><span class="sxs-lookup"><span data-stu-id="44902-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-219">예</span><span class="sxs-lookup"><span data-stu-id="44902-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-220">예</span><span class="sxs-lookup"><span data-stu-id="44902-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-221">Lync 2010 모바일</span><span class="sxs-lookup"><span data-stu-id="44902-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="44902-222">예</span><span class="sxs-lookup"><span data-stu-id="44902-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-223">예</span><span class="sxs-lookup"><span data-stu-id="44902-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="44902-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="44902-225">예</span><span class="sxs-lookup"><span data-stu-id="44902-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-226">예</span><span class="sxs-lookup"><span data-stu-id="44902-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-227">예</span><span class="sxs-lookup"><span data-stu-id="44902-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="44902-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="44902-229">예</span><span class="sxs-lookup"><span data-stu-id="44902-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-230">예</span><span class="sxs-lookup"><span data-stu-id="44902-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-231">예</span><span class="sxs-lookup"><span data-stu-id="44902-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-232">예</span><span class="sxs-lookup"><span data-stu-id="44902-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-233">예1</span><span class="sxs-lookup"><span data-stu-id="44902-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="44902-234">예</span><span class="sxs-lookup"><span data-stu-id="44902-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-235">공용 IM (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="44902-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="44902-236">예</span><span class="sxs-lookup"><span data-stu-id="44902-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-237">예</span><span class="sxs-lookup"><span data-stu-id="44902-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-238">공용 인스턴트 메시지 (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="44902-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="44902-239">예</span><span class="sxs-lookup"><span data-stu-id="44902-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-240">예</span><span class="sxs-lookup"><span data-stu-id="44902-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-241">예</span><span class="sxs-lookup"><span data-stu-id="44902-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-242">예</span><span class="sxs-lookup"><span data-stu-id="44902-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="44902-243">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)는 더 이상 신규 또는 갱신 계약을 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="44902-244">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="44902-245">서비스 종료 날짜까지 Messenger.</span><span class="sxs-lookup"><span data-stu-id="44902-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="44902-246">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="44902-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="44902-247">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-247">has been announced.</span></span> <span data-ttu-id="44902-248">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44902-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="44902-249">PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!에 페더레이션 하는 데 필요한 사용자별, 월별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="44902-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="44902-250">받으려면.</span><span class="sxs-lookup"><span data-stu-id="44902-250">Messenger.</span></span> <span data-ttu-id="44902-251">이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!의 지원으로 부과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="44902-252">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="44902-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="44902-253">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="44902-254">Skype 페더레이션은이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 통해 수백만 명에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="44902-255">1 Office Communicator 2007 R2에서는 데스크톱 공유 (프로그램 공유 아님)만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44902-256">비즈니스용 Skype 2015 클라이언트 사용자 인터페이스가 시행 되는 경우 Office Communicator 2007 R2와 비즈니스용 Skype 2015을 최신 버전의 클라이언트에서 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="44902-257">Lync Server 2010 모임에서 Lync 2013 클라이언트에 대 한 회의 기능 지원</span><span class="sxs-lookup"><span data-stu-id="44902-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="44902-258">Lync 2013 클라이언트를 사용 하 여 Lync Server 2010 모임에 참가 하면 다음과 같은 예외로 Lync 2013 클라이언트 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="44902-259">모임 창에서 사람 아이콘을 가리켜 액세스할 수 있는 **참가자** 관리 옵션에서 **모임 메신저 대화 없음** 옵션이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="44902-260">갤러리 보기는 영상 회의에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="44902-261">사용자는 모든 스피커가 아닌 활성 스피커로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="44902-262">**레이아웃 옵션 선택** 목록에서 **갤러리 보기** 를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44902-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="44902-263">참가자 목록은 기본적으로 비디오 회의에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="44902-264">참가자 목록에서 사용자를 마우스 오른쪽 단추로 클릭 하면 **비디오 스포트라이트** 및 **갤러리에 대 한 Pin** 참가 관리 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="44902-265">Lync Server 2013 모임에서 회의 기능 지원</span><span class="sxs-lookup"><span data-stu-id="44902-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="44902-266">Lync Server 2013는 계정이 Lync Server 2013로 이동 하 고 Lync 2013 클라이언트를 사용 하 여 로그인 한 후 사용자에 게 제공 되는 새로운 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="44902-267">비디오 갤러리 보기, HD 비디오, PowerPoint 공유, 모임 입력 시 모든 참석자 오디오 및 비디오 음소거 옵션을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="44902-268">새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한 새로운](lync-server-2013-what-s-new-for-clients.md)기능에 개략적으로 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="44902-269">Lync Server 2013 모임에서는 다른 버전의 서버에 거주 하는 사용자와 다른 클라이언트 및 클라이언트 버전을 사용 하는 경우 특정 회의 기능이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="44902-270">클라이언트가 Lync Server 2013 모임에 참가할 때 사용자는이 표에 표시 된 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44902-271">클라이언트</span><span class="sxs-lookup"><span data-stu-id="44902-271">Client</span></span></th>
<th><span data-ttu-id="44902-272">피어 투 피어 IM</span><span class="sxs-lookup"><span data-stu-id="44902-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="44902-273">음성</span><span class="sxs-lookup"><span data-stu-id="44902-273">Voice</span></span></th>
<th><span data-ttu-id="44902-274">비디오만</span><span class="sxs-lookup"><span data-stu-id="44902-274">Video</span></span></th>
<th><span data-ttu-id="44902-275">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="44902-275">Application Sharing</span></span></th>
<th><span data-ttu-id="44902-276">틀린</span><span class="sxs-lookup"><span data-stu-id="44902-276">PowerPoint</span></span></th>
<th><span data-ttu-id="44902-277">파일 전송</span><span class="sxs-lookup"><span data-stu-id="44902-277">File Transfer</span></span></th>
<th><span data-ttu-id="44902-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="44902-278">Whiteboard</span></span></th>
<th><span data-ttu-id="44902-279">투표</span><span class="sxs-lookup"><span data-stu-id="44902-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44902-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="44902-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="44902-281">예</span><span class="sxs-lookup"><span data-stu-id="44902-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-282">예</span><span class="sxs-lookup"><span data-stu-id="44902-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-283">예</span><span class="sxs-lookup"><span data-stu-id="44902-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-284">예</span><span class="sxs-lookup"><span data-stu-id="44902-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-285">예</span><span class="sxs-lookup"><span data-stu-id="44902-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-286">예</span><span class="sxs-lookup"><span data-stu-id="44902-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-287">예</span><span class="sxs-lookup"><span data-stu-id="44902-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-288">예</span><span class="sxs-lookup"><span data-stu-id="44902-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="44902-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="44902-290">예</span><span class="sxs-lookup"><span data-stu-id="44902-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-291">예</span><span class="sxs-lookup"><span data-stu-id="44902-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-292">예</span><span class="sxs-lookup"><span data-stu-id="44902-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-293">예</span><span class="sxs-lookup"><span data-stu-id="44902-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-294">예</span><span class="sxs-lookup"><span data-stu-id="44902-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-295">예</span><span class="sxs-lookup"><span data-stu-id="44902-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-296">예</span><span class="sxs-lookup"><span data-stu-id="44902-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-297">예</span><span class="sxs-lookup"><span data-stu-id="44902-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="44902-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="44902-299">예</span><span class="sxs-lookup"><span data-stu-id="44902-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-300">예</span><span class="sxs-lookup"><span data-stu-id="44902-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-301">예</span><span class="sxs-lookup"><span data-stu-id="44902-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-302">예</span><span class="sxs-lookup"><span data-stu-id="44902-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-303">예2</span><span class="sxs-lookup"><span data-stu-id="44902-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="44902-304">예</span><span class="sxs-lookup"><span data-stu-id="44902-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-305">예</span><span class="sxs-lookup"><span data-stu-id="44902-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-306">예</span><span class="sxs-lookup"><span data-stu-id="44902-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="44902-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="44902-308">예</span><span class="sxs-lookup"><span data-stu-id="44902-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-309">예</span><span class="sxs-lookup"><span data-stu-id="44902-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-310">예</span><span class="sxs-lookup"><span data-stu-id="44902-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-311">예</span><span class="sxs-lookup"><span data-stu-id="44902-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="44902-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="44902-313">예</span><span class="sxs-lookup"><span data-stu-id="44902-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-314">예</span><span class="sxs-lookup"><span data-stu-id="44902-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="44902-315">예</span><span class="sxs-lookup"><span data-stu-id="44902-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="44902-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="44902-317">예</span><span class="sxs-lookup"><span data-stu-id="44902-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="44902-318">1 Office Communicator 2007 R2에서는 데스크톱 공유 (프로그램 공유 아님)만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="44902-319">2 Lync Server 2013에서 PowerPoint 파일을 업로드 하는 데 업데이트 된 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="44902-320">원래 Lync Server 2010에서 예약한 모임에 참가 하는 lync Web App 사용자는 PowerPoint 프레젠테이션을 보고 탐색할 수 있지만 PowerPoint 파일을 업로드할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="44902-321">3 lync Server 2013 및 PowerPoint 슬라이드에 대 한 모임이 Lync 2013 클라이언트에 의해 업로드 된 경우 Lync 2010 사용자는 슬라이드에 보기 전용으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="44902-322">반대로, PowerPoint 슬라이드를 Lync 2010 사용자가 업로드 한 경우에는 Lync Server 2013 사용자가 보기 및 슬라이드를 수행할 수 있으며, Office Web Apps Server가 구성 되어 있는 경우 더 높은 해상도 표시, 애니메이션, 화면 전환 등의 새로운 기능에 액세스할 수 있습니다. 포함 된 비디오.</span><span class="sxs-lookup"><span data-stu-id="44902-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="44902-323">자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44902-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="44902-324">4 Office Communicator 2007 R2의 현재 상태 및 메신저 기능은 Lync Server 2013와 호환 되지만, 회의 기능은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="44902-325">Office Communications Server 2007 R2에서 마이그레이션하는 동안 Office Communicator 2007 R2는 현재 상태 및 IM 상호 운용성에 적합 하지만 사용자는 lync Web App 2013을 사용 하 여 Lync Server 2013 모임에 참가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="44902-326">추가 기능 지원 예약</span><span class="sxs-lookup"><span data-stu-id="44902-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="44902-327">다양 한 스케줄링 추가 기능에 대 한 서버 지원은 서버 및 클라이언트 버전 호환성과 일관성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="44902-328">일반적으로 Lync Server 2013에서 다음과 같은 일정 예약 추가 기능이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="44902-329">그러나 이전 버전의 추가 기능은 모임 항목에 모든 참석자 오디오 및 비디오를 음소거 하는 옵션과 같은 새로운 Lync 2013 추가 기능 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="44902-330">**Lync 2013**   의 온라인 모임 추가 기능을 사용 하면 모임 이끌이가 기본적으로 참석자 오디오와 비디오가 음소거 된 회의를 예약할 수 있는 참석자 음소거 컨트롤을 통해 lync 2010와 동일한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="44902-331">관리자는 사용자 지정 로고, 지원 URL, 법적 고 지 사항 URL 또는 사용자 지정 바닥글 텍스트를 추가 하 여 조직의 모임 초대를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="44902-332">**Lync 2010**   용 온라인 모임 추가 기능은 lync 모임에 대 한 예약을 제공 하 고 Office Live Meeting 회의를 예약 하는 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="44902-333">**Office communicator 2007 R2 회의 추가 기능**   을 통해 office Live 모임 컨퍼런스와 office Communicator 2007 R2 회의를 둘 다 사용할 계획을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="44902-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="44902-334">Lync Server 2013에서 Live Meeting 회의를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44902-335">예약 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44902-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="44902-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44902-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="44902-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="44902-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="44902-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="44902-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44902-339">Lync 2013 용 온라인 모임 추가 기능 (Office 2013, Outlook 2010 및 Outlook 2007에서 사용할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="44902-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="44902-340">지원</span><span class="sxs-lookup"><span data-stu-id="44902-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-341">지원 됨 (새 추가 기능 기능을 사용할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="44902-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="44902-342">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-343">Lync 2013 웹 스케줄러</span><span class="sxs-lookup"><span data-stu-id="44902-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="44902-344">지원</span><span class="sxs-lookup"><span data-stu-id="44902-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-345">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-346">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44902-347">Lync 2010 용 온라인 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="44902-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="44902-348">지원</span><span class="sxs-lookup"><span data-stu-id="44902-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-349">지원</span><span class="sxs-lookup"><span data-stu-id="44902-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-350">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44902-351">Office Communicator 2007 R2 회의 추가 기능</span><span class="sxs-lookup"><span data-stu-id="44902-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="44902-352">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="44902-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-353">지원</span><span class="sxs-lookup"><span data-stu-id="44902-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="44902-354">지원</span><span class="sxs-lookup"><span data-stu-id="44902-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="44902-355">모임 참가 지원</span><span class="sxs-lookup"><span data-stu-id="44902-355">Support for Joining Meetings</span></span>

<span data-ttu-id="44902-356">Lync Server 2013에서 지원 되는 모든 클라이언트는 Lync 2013 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="44902-357">Lync Web App이 서버의 웹 구성 요소 이기 때문에 lync Web App이 Lync Server 2013 모임에 참가 하는 데 사용 되는 경우에는 최신 버전의 Lync Web App이 항상 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="44902-358">Lync 2013 클라이언트는 Lync 2010 및 Office Communications Server 2007 R2에 호스트 된 모임에 확장 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44902-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="44902-359">모임 중 기능은 모임이 호스팅되는 서버의 버전으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44902-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44902-360">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44902-360">See Also</span></span>


[<span data-ttu-id="44902-361">Lync Server 2013에 대 한 lync Windows 스토어 앱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="44902-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="44902-362">Lync Server 2013의 새로운 회의 기능</span><span class="sxs-lookup"><span data-stu-id="44902-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="44902-363">Lync Server 2013의 새로운 클라이언트 기능</span><span class="sxs-lookup"><span data-stu-id="44902-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

