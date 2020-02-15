---
title: 'Lync Server 2013: 영구 채팅 서버 테이블 세부 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3caf59185bc3fbe985ea8b7d4371d464b515e3fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="189bd-102">Lync Server 2013의 영구 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="189bd-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="189bd-103">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="189bd-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="189bd-104">다음 항목에서는 각 영구 채팅 데이터베이스 스키마 테이블에 있는 열에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="189bd-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="189bd-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="189bd-105">In This Section</span></span>

  - [<span data-ttu-id="189bd-106">Lync Server 2013의 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="189bd-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="189bd-107">Lync Server 2013의 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="189bd-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="189bd-108">Lync Server 2013의 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="189bd-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="189bd-109">Lync Server 2013의 tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="189bd-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="189bd-110">Lync Server 2013의 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="189bd-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="189bd-111">Lync Server 2013의 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="189bd-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="189bd-112">Lync Server 2013의 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="189bd-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="189bd-113">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="189bd-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="189bd-114">Lync Server 2013의 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="189bd-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="189bd-115">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="189bd-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="189bd-116">Lync Server 2013의 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="189bd-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="189bd-117">Lync Server 2013의 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="189bd-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="189bd-118">Lync Server 2013의 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="189bd-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="189bd-119">Lync Server 2013의 tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="189bd-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="189bd-120">Lync Server 2013의 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="189bd-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="189bd-121">Lync Server 2013의 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="189bd-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="189bd-122">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="189bd-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="189bd-123">Lync Server 2013의 tblChat</span><span class="sxs-lookup"><span data-stu-id="189bd-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="189bd-124">Lync Server 2013의 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="189bd-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="189bd-125">Lync Server 2013의 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="189bd-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="189bd-126">Lync Server 2013의 tblPreference 설정</span><span class="sxs-lookup"><span data-stu-id="189bd-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="189bd-127">Lync Server 2013의 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="189bd-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="189bd-128">Lync Server 2013의 tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="189bd-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="189bd-129">Lync Server 2013의 tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="189bd-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="189bd-130">Lync Server 2013의 tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="189bd-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="189bd-131">Lync Server 2013의 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="189bd-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="189bd-132">Lync Server 2013의 tblConfig</span><span class="sxs-lookup"><span data-stu-id="189bd-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="189bd-133">Lync Server 2013의 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="189bd-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="189bd-134">Lync Server 2013의 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="189bd-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="189bd-135">Lync Server 2013의 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="189bd-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="189bd-136">Lync Server 2013의 tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="189bd-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

