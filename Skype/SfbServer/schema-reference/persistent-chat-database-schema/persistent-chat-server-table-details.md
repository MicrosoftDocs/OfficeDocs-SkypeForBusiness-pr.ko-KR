---
title: 영구 채팅 서버 테이블 세부 정보
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: 다음 항목에서는 각 영구 채팅 데이터베이스 schema 테이블의 열에 대해 자세히 설명합니다.
ms.openlocfilehash: 71cec482d5b799eefc1817b84993a9fbe3ca884a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812998"
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="29f1d-103">영구 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="29f1d-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="29f1d-104">다음 항목에서는 각 영구 채팅 데이터베이스 schema 테이블의 열에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="29f1d-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="29f1d-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="29f1d-105">In this section</span></span>

- [<span data-ttu-id="29f1d-106">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="29f1d-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="29f1d-107">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="29f1d-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="29f1d-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="29f1d-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="29f1d-109">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="29f1d-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="29f1d-110">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="29f1d-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="29f1d-111">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="29f1d-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="29f1d-112">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="29f1d-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="29f1d-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="29f1d-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="29f1d-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="29f1d-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="29f1d-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="29f1d-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="29f1d-116">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="29f1d-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="29f1d-117">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="29f1d-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="29f1d-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="29f1d-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="29f1d-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="29f1d-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="29f1d-120">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="29f1d-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="29f1d-121">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="29f1d-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="29f1d-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="29f1d-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="29f1d-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="29f1d-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="29f1d-124">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="29f1d-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="29f1d-125">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="29f1d-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="29f1d-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="29f1d-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="29f1d-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="29f1d-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="29f1d-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="29f1d-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="29f1d-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="29f1d-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="29f1d-130">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="29f1d-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="29f1d-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="29f1d-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="29f1d-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="29f1d-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="29f1d-133">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="29f1d-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="29f1d-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="29f1d-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="29f1d-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="29f1d-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="29f1d-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="29f1d-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

