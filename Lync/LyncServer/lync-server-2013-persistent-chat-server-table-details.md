---
title: 'Lync Server 2013: 영구 채팅 서버 테이블 세부 정보'
description: 'Lync Server 2013: 영구 채팅 서버 테이블 세부 정보'
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
ms.openlocfilehash: 6a27feaaccf861d537127f06920cf903be5ae000
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545134"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="6ac4e-103">Lync Server 2013의 영구 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="6ac4e-103">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ac4e-104">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="6ac4e-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="6ac4e-105">다음 항목에서는 각 영구 채팅 데이터베이스 스키마 테이블에 있는 열에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac4e-105">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6ac4e-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6ac4e-106">In This Section</span></span>

  - [<span data-ttu-id="6ac4e-107">Lync Server 2013의 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="6ac4e-107">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="6ac4e-108">Lync Server 2013의 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="6ac4e-108">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="6ac4e-109">Lync Server 2013의 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="6ac4e-109">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="6ac4e-110">Lync Server 2013의 tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="6ac4e-110">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="6ac4e-111">Lync Server 2013의 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="6ac4e-111">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="6ac4e-112">Lync Server 2013의 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="6ac4e-112">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="6ac4e-113">Lync Server 2013의 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="6ac4e-113">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="6ac4e-114">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="6ac4e-114">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="6ac4e-115">Lync Server 2013의 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="6ac4e-115">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="6ac4e-116">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="6ac4e-116">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="6ac4e-117">Lync Server 2013의 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="6ac4e-117">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="6ac4e-118">Lync Server 2013의 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="6ac4e-118">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="6ac4e-119">Lync Server 2013의 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="6ac4e-119">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="6ac4e-120">Lync Server 2013의 tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="6ac4e-120">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="6ac4e-121">Lync Server 2013의 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="6ac4e-121">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="6ac4e-122">Lync Server 2013의 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="6ac4e-122">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="6ac4e-123">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="6ac4e-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="6ac4e-124">Lync Server 2013의 tblChat</span><span class="sxs-lookup"><span data-stu-id="6ac4e-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="6ac4e-125">Lync Server 2013의 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="6ac4e-125">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="6ac4e-126">Lync Server 2013의 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="6ac4e-126">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="6ac4e-127">Lync Server 2013의 tblPreference 설정</span><span class="sxs-lookup"><span data-stu-id="6ac4e-127">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="6ac4e-128">Lync Server 2013의 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="6ac4e-128">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="6ac4e-129">Lync Server 2013의 tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="6ac4e-129">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="6ac4e-130">Lync Server 2013의 tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="6ac4e-130">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="6ac4e-131">Lync Server 2013의 tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="6ac4e-131">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="6ac4e-132">Lync Server 2013의 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="6ac4e-132">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="6ac4e-133">Lync Server 2013의 tblConfig</span><span class="sxs-lookup"><span data-stu-id="6ac4e-133">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="6ac4e-134">Lync Server 2013의 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="6ac4e-134">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="6ac4e-135">Lync Server 2013의 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="6ac4e-135">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="6ac4e-136">Lync Server 2013의 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="6ac4e-136">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="6ac4e-137">Lync Server 2013의 tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="6ac4e-137">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

