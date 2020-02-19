---
title: 'Lync Server 2013: Lync 2013의 클라이언트 상호 운용성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a4616cbe9519a8196ce78e35f21c673a0d2c95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="d6b49-102">Lync 2013의 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d6b49-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6b49-103">_**마지막으로 수정 된 항목:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="d6b49-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="d6b49-104">이 항목에서는 Microsoft Lync Server 2013 클라이언트가 이전 버전의 Lync Server 및 Office Communications Server와 함께 사용 되 고 클라이언트와 상호 작용 하는 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="d6b49-105">서버 및 클라이언트 호환성</span><span class="sxs-lookup"><span data-stu-id="d6b49-105">Server and Client Compatibility</span></span>

<span data-ttu-id="d6b49-106">다음 표에는 지원 되는 클라이언트 버전 및 서버 버전 조합이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="d6b49-107">이 테이블은 클라이언트가 지정 된 서버에 연결 하려고 할 때 로그인이 지원 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="d6b49-108">Lync Server 2013는 이전 클라이언트 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="d6b49-109">또한 이전 릴리스와 달리 Lync Server 2010는 새 Lync 2013 클라이언트를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="d6b49-110">이를 통해 Lync Server 2010에서 업그레이드 하는 조직은 Lync Server 업그레이드에 관계 없이 새 클라이언트를 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6b49-111">클라이언트</span><span class="sxs-lookup"><span data-stu-id="d6b49-111">Client</span></span></th>
<th><span data-ttu-id="d6b49-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b49-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="d6b49-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d6b49-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="d6b49-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d6b49-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d6b49-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d6b49-116">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="d6b49-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="d6b49-118">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d6b49-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d6b49-120">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-121">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-122">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="d6b49-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="d6b49-124">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-125">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-126">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d6b49-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d6b49-128">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-129">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-130">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d6b49-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d6b49-132">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-133">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-134">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-135">Lync 2010 그룹 채팅</span><span class="sxs-lookup"><span data-stu-id="d6b49-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="d6b49-136">1</span><span class="sxs-lookup"><span data-stu-id="d6b49-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="d6b49-137">2</span><span class="sxs-lookup"><span data-stu-id="d6b49-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="d6b49-138">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d6b49-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="d6b49-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="d6b49-140">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-141">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-142">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="d6b49-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="d6b49-144">Supported3 아님</span><span class="sxs-lookup"><span data-stu-id="d6b49-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="d6b49-145">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-146">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d6b49-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d6b49-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="d6b49-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="d6b49-149">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-150">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="d6b49-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d6b49-152">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-153">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-154">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="d6b49-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="d6b49-156">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-157">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-158">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="d6b49-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="d6b49-160">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-161">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-162">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-163">Lync Windows 스토어 앱</span><span class="sxs-lookup"><span data-stu-id="d6b49-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="d6b49-164">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-165">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-166">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6b49-167">1For 자세한 내용은 [Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에서 Lync server 2013, 영구 채팅 서버로 마이그레이션을](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6b49-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="d6b49-168">2In Lync Server 2010에서 그룹 채팅 기능은 Lync Server 2010 용 타사 트러스트 응용 프로그램을 사용 하 여 그룹 채팅 서버에서 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="d6b49-169">Lync 2013 클라이언트는 Lync Server 2010, 그룹 채팅과 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="d6b49-170">3Lync Web App 2013는 이제 컴퓨터 오디오 및 비디오를 비롯 한 전체 모임 환경을 제공 하며 Lync 2010 참석자의 교체로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="d6b49-171">Lync 2010 참석자는 지원 되지 않는 브라우저 (Internet Explorer 6 또는 Internet Explorer 7) 및 Windows XP를 사용 하는 경우에만 Lync Server 2013에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="d6b49-172">4The Communicator 2007 R2의 현재 상태 및 IM 기능은 Lync Server 2013과 호환 되지만 회의 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="d6b49-173">Office Communications Server 2007 R2에서 마이그레이션하는 동안 Office Communicator 2007 R2는 현재 상태 및 IM 상호 운용성에 적합 하지만 lync Web App 2013을 사용 하 여 Lync Server 2013 meeting에 참가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="d6b49-174">5 제한에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "Lync Server 2010 회의의 Lync 2013 클라이언트에 대 한 회의 기능 지원"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6b49-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="d6b49-175">클라이언트 간 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d6b49-175">Interoperability among Clients</span></span>

<span data-ttu-id="d6b49-176">Lync Server 2013 릴리스를 사용 하면 다양 한 클라이언트 버전이 피어-투-피어 및 회의 시나리오에서 원활 하 게 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="d6b49-177">이 섹션에서는 사용자가 다른 버전의 클라이언트 및 서버를 사용 하는 다른 사용자와 상호 작용할 때의 기능 가용성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="d6b49-178">피어-투-피어 기능 지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="d6b49-179">피어 투 피어 기능은 서로 다른 서버 버전에 있고 다른 클라이언트 버전을 사용 하는 사용자에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="d6b49-180">최종 사용자 환경 및 사용 가능한 기능은 사용자 클라이언트의 기능과 사용자가 로그인 되어 있는 서버의 버전에 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="d6b49-181">위의 명령이 반환하는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-181">In other words:</span></span>

  - <span data-ttu-id="d6b49-182">사용자가 이전 클라이언트를 사용 하 여 Lync Server 2013에 로그인 되어 있으면 사용자는에 사용 하는 것과 같은 환경을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="d6b49-183">Lync Server 2013에 도입 된 새로운 기능은 사용자의 클라이언트를 업그레이드할 때까지 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="d6b49-184">비디오 갤러리 보기, HD 비디오, 업데이트 된 PowerPoint 공유, 모임 입장에서 모든 참석자 오디오 및 비디오 음소거 옵션을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="d6b49-185">새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한](lync-server-2013-what-s-new-for-clients.md)새로운 기능에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="d6b49-186">Lync 2013 클라이언트를 사용 하 여 Lync Server 2010에 로그인 한 사용자는 lync server 2013로 이동할 때까지 Lync Server 2010에서 지원 하지 않는 모든 새 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="d6b49-187">다음 표에서는 클라이언트가 Lync Server 2013 또는 Lync Server 2010에 로그인 한 피어 투 피어 세션의 기능 가용성을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6b49-188">Lync Web App 및 Lync 2010 참석자는 모임 전용 클라이언트이 고이 테이블에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="d6b49-189">클라이언트</span><span class="sxs-lookup"><span data-stu-id="d6b49-189">Client</span></span></th>
<th><span data-ttu-id="d6b49-190">인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="d6b49-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="d6b49-191">이들의</span><span class="sxs-lookup"><span data-stu-id="d6b49-191">Presence</span></span></th>
<th><span data-ttu-id="d6b49-192">음성</span><span class="sxs-lookup"><span data-stu-id="d6b49-192">Voice</span></span></th>
<th><span data-ttu-id="d6b49-193">비디오</span><span class="sxs-lookup"><span data-stu-id="d6b49-193">Video</span></span></th>
<th><span data-ttu-id="d6b49-194">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="d6b49-194">Application Sharing</span></span></th>
<th><span data-ttu-id="d6b49-195">파일 전송</span><span class="sxs-lookup"><span data-stu-id="d6b49-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d6b49-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d6b49-197">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-198">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-199">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-200">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-201">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-202">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d6b49-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d6b49-204">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-205">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-206">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-207">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-208">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-209">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d6b49-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d6b49-211">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-212">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-213">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-214">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-215">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-216">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d6b49-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d6b49-218">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-219">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-220">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-221">Lync 2010 모바일</span><span class="sxs-lookup"><span data-stu-id="d6b49-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="d6b49-222">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-223">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d6b49-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="d6b49-225">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-226">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-227">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d6b49-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d6b49-229">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-230">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-231">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-232">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="d6b49-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="d6b49-234">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-235">공용 IM (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="d6b49-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="d6b49-236">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-237">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-238">공용 IM (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="d6b49-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="d6b49-239">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-240">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-241">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-242">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d6b49-243">2012 년 9 월 1 일부 터 신규 또는 갱신 계약에 대 한 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="d6b49-244">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d6b49-245">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="d6b49-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="d6b49-246">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="d6b49-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d6b49-247">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-247">has been announced.</span></span> <span data-ttu-id="d6b49-248">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요..</span><span class="sxs-lookup"><span data-stu-id="d6b49-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="d6b49-249">PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!과 페더레이션 하는 데 필요한 사용자별 구독 라이선스 (매달)입니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d6b49-250">메신저로.</span><span class="sxs-lookup"><span data-stu-id="d6b49-250">Messenger.</span></span> <span data-ttu-id="d6b49-251">이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="d6b49-252">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d6b49-253">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d6b49-254">Lync 사용자가 IM 및 음성을 통해 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d6b49-255">1 Office Communicator 2007 R2에서는 데스크톱 공유 (및 프로그램 공유 아님)만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6b49-256">Office Communicator 2007 R2와 비즈니스용 Skype 2015 간의 데스크톱 공유는 비즈니스용 Skype 2015 클라이언트 사용자 인터페이스가 적용 되는 경우 최신 클라이언트에서 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="d6b49-257">Lync Server 2010 모임의 Lync 2013 클라이언트에 대 한 회의 기능 지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="d6b49-258">사용자가 lync 2013 클라이언트를 사용 하 여 Lync Server 2010 회의에 참가 하면 다음과 같은 예외 사항을 제외 하 고 Lync 2013 클라이언트 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="d6b49-259">모임 창에서 사람 아이콘을 가리켜 액세스할 수 있는 **참가자** 관리 옵션에서 **모임 메신저 대화** 상대가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="d6b49-260">갤러리 보기가 비디오 회의에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="d6b49-261">사용자는 모든 스피커가 아닌 활성 발표자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="d6b49-262">**레이아웃 옵션 선택** 목록에서 **갤러리 보기** 를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d6b49-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="d6b49-263">참가자 목록은 비디오 회의에 기본적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="d6b49-264">참가자 목록에서 사용자를 마우스 오른쪽 단추로 클릭 하는 경우에는 **비디오 스포트라이트** 및 **Pin을 갤러리** 참가자 관리 옵션으로 잠글 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="d6b49-265">Lync Server 2013 모임의 회의 기능 지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="d6b49-266">Lync Server 2013에서는 계정이 Lync Server 2013로 이동 되 고 Lync 2013 클라이언트에 로그인 한 후 사용자에 게 제공 되는 새로운 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="d6b49-267">비디오 갤러리 보기, HD 비디오, PowerPoint 공유 및 모든 참석자의 오디오 및 비디오를 모임 항목에 음소거 하는 옵션을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="d6b49-268">새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한](lync-server-2013-what-s-new-for-clients.md)새로운 기능에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="d6b49-269">Lync Server 2013 모임에서는 서로 다른 클라이언트 및 클라이언트 버전을 사용 하는 사용자 및 서버 버전에 따라 특정 회의 기능이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="d6b49-270">클라이언트가 Lync Server 2013 회의에 참가 하면 사용자는이 표에 나와 있는 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="d6b49-271">클라이언트</span><span class="sxs-lookup"><span data-stu-id="d6b49-271">Client</span></span></th>
<th><span data-ttu-id="d6b49-272">피어 투 피어 IM</span><span class="sxs-lookup"><span data-stu-id="d6b49-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="d6b49-273">음성</span><span class="sxs-lookup"><span data-stu-id="d6b49-273">Voice</span></span></th>
<th><span data-ttu-id="d6b49-274">비디오</span><span class="sxs-lookup"><span data-stu-id="d6b49-274">Video</span></span></th>
<th><span data-ttu-id="d6b49-275">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="d6b49-275">Application Sharing</span></span></th>
<th><span data-ttu-id="d6b49-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d6b49-276">PowerPoint</span></span></th>
<th><span data-ttu-id="d6b49-277">파일 전송</span><span class="sxs-lookup"><span data-stu-id="d6b49-277">File Transfer</span></span></th>
<th><span data-ttu-id="d6b49-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="d6b49-278">Whiteboard</span></span></th>
<th><span data-ttu-id="d6b49-279">폴링</span><span class="sxs-lookup"><span data-stu-id="d6b49-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d6b49-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d6b49-281">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-282">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-283">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-284">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-285">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-286">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-287">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-288">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d6b49-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d6b49-290">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-291">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-292">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-293">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-294">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-295">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-296">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-297">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="d6b49-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="d6b49-299">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-300">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-301">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-302">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-303">예2</span><span class="sxs-lookup"><span data-stu-id="d6b49-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="d6b49-304">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-305">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-306">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d6b49-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d6b49-308">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-309">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-310">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-311">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="d6b49-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="d6b49-313">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-314">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6b49-315">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="d6b49-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="d6b49-317">예</span><span class="sxs-lookup"><span data-stu-id="d6b49-317">Yes</span></span></p></td>
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


<span data-ttu-id="d6b49-318">1 Office Communicator 2007 R2에서는 데스크톱 공유 (및 프로그램 공유 아님)만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="d6b49-319">2 Lync Server 2013에서는 PowerPoint 파일을 업로드 하는 데 업데이트 된 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="d6b49-320">처음에 Lync Server 2010에 예약 된 모임에 참가 하는 lync Web App 사용자는 PowerPoint 프레젠테이션을 보고 탐색할 수 있지만 PowerPoint 파일을 업로드 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="d6b49-321">3 lync Server 2013에 회의가 예약 되었고 PowerPoint 슬라이드를 Lync 2013 클라이언트에서 업로드 한 경우 Lync 2010 사용자에 게 슬라이드에 대 한 보기 전용 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="d6b49-322">반대로, PowerPoint 슬라이드를 Lync 2010 사용자가 업로드 한 경우 Lync Server 2013 사용자는 보기 및 슬라이드를 볼 수 있으며, Office Web Apps 서버가 구성 되어 있으면 더 높은 해상도의 디스플레이, 애니메이션, 화면 전환과 같은 새로운 기능에 액세스 합니다. 포함 된 비디오</span><span class="sxs-lookup"><span data-stu-id="d6b49-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="d6b49-323">자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6b49-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="d6b49-324">4The Communicator 2007 R2의 현재 상태 및 IM 기능은 Lync Server 2013과 호환 되지만 회의 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="d6b49-325">Office Communications Server 2007 R2에서 마이그레이션하는 동안 Office Communicator 2007 R2는 현재 상태 및 IM 상호 운용성에 적합 하지만 lync Web App 2013을 사용 하 여 Lync Server 2013 meeting에 참가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="d6b49-326">추가 기능 지원 예약</span><span class="sxs-lookup"><span data-stu-id="d6b49-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="d6b49-327">다양 한 일정 추가 기능에 대 한 서버 지원은 서버 및 클라이언트 버전 호환성과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="d6b49-328">일반적으로 Lync Server 2013에서는 다음과 같은 예약 추가 기능이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="d6b49-329">그러나 이전 버전의 추가 기능은 모임 항목에 모든 참석자 오디오 및 비디오를 음소거 하는 옵션과 같은 새로운 Lync 2013 추가 기능 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="d6b49-330">**Lync 2013**   의 온라인 모임 추가 기능은 lync 2010에 대 한 온라인 모임 추가 기능과 같은 기능을 제공 하며, 모임 이끌이가 기본적으로 참석자의 오디오 및 비디오가 음소거 된 회의를 예약할 수 있도록 하는 참석자 음소거 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="d6b49-331">또한 관리자는 사용자 지정 로고, 지원 URL, 법적 고 지 사항 URL 또는 사용자 지정 바닥글 텍스트를 추가 하 여 조직의 모임 초대를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="d6b49-332">**Lync 2010**   용 온라인 모임 추가 기능은 lync 모임 예약을 제공 하 고 Office Live Meeting 회의를 예약 하는 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="d6b49-333">**Office communicator 2007 R2 회의 추가 기능**   office Live Meeting 회의 및 office Communicator 2007 R2 회의 모두의 일정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="d6b49-334">Lync Server 2013에서는 Live Meeting 회의를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="d6b49-335">예약 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d6b49-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="d6b49-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b49-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="d6b49-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d6b49-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="d6b49-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d6b49-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-339">Lync 2013 용 온라인 모임 추가 기능 (Office 2013, Outlook 2010 및 Outlook 2007과 함께 사용할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d6b49-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="d6b49-340">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-341">지원 (새 추가 기능 기능을 사용할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="d6b49-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="d6b49-342">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-343">Lync 2013 웹 스케줄러</span><span class="sxs-lookup"><span data-stu-id="d6b49-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="d6b49-344">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-345">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-346">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b49-347">Online Meeting Add-in for Lync 2010(Lync 2010용 온라인 모임 추가 기능)</span><span class="sxs-lookup"><span data-stu-id="d6b49-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d6b49-348">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-349">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-350">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b49-351">Office Communicator 2007 R2 회의 추가 기능</span><span class="sxs-lookup"><span data-stu-id="d6b49-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="d6b49-352">미지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-353">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="d6b49-354">지원됨</span><span class="sxs-lookup"><span data-stu-id="d6b49-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="d6b49-355">모임 참가 지원</span><span class="sxs-lookup"><span data-stu-id="d6b49-355">Support for Joining Meetings</span></span>

<span data-ttu-id="d6b49-356">Lync Server 2013에서 지 원하는 모든 클라이언트는 Lync 2013 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="d6b49-357">Lync Web App은 lync Server 2013 회의에 참가 하는 것과 같은 서버 웹 구성 요소 이므로, 최신 버전의 Lync Web App이 항상 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="d6b49-358">Lync 2013 클라이언트는 Lync 2010 및 Office Communications Server 2007 r 2에서 호스트 되는 모임에 확장 된 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="d6b49-359">모임 중인 기능은 모임이 호스트 되는 서버의 버전에 따라 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6b49-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6b49-360">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6b49-360">See Also</span></span>


[<span data-ttu-id="d6b49-361">Lync Server 2013에 대 한 lync Windows 스토어 앱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6b49-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="d6b49-362">Lync Server 2013의 새로운 회의 기능</span><span class="sxs-lookup"><span data-stu-id="d6b49-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="d6b49-363">Lync Server 2013의 새로운 클라이언트 기능</span><span class="sxs-lookup"><span data-stu-id="d6b49-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

