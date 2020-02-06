---
title: 영구 채팅 서버 테이블 세부 정보
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: 다음 항목에서는 각 영구 채팅 데이터베이스 스키마 테이블의 열에 대해 자세히 설명 합니다.
ms.openlocfilehash: f9dbc6a4633b48c384cbea36eaffb3c7f1d074f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814736"
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="7422d-103">영구 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7422d-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="7422d-104">다음 항목에서는 각 영구 채팅 데이터베이스 스키마 테이블의 열에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7422d-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7422d-105">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="7422d-105">In this section</span></span>

- [<span data-ttu-id="7422d-106">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="7422d-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="7422d-107">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="7422d-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="7422d-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="7422d-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="7422d-109">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="7422d-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="7422d-110">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="7422d-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="7422d-111">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="7422d-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="7422d-112">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="7422d-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="7422d-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="7422d-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="7422d-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="7422d-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="7422d-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="7422d-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="7422d-116">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="7422d-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="7422d-117">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="7422d-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="7422d-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="7422d-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="7422d-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="7422d-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="7422d-120">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="7422d-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="7422d-121">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="7422d-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="7422d-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="7422d-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="7422d-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="7422d-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="7422d-124">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="7422d-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="7422d-125">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="7422d-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="7422d-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="7422d-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="7422d-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="7422d-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="7422d-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="7422d-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="7422d-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="7422d-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="7422d-130">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="7422d-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="7422d-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="7422d-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="7422d-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="7422d-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="7422d-133">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="7422d-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="7422d-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="7422d-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="7422d-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="7422d-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="7422d-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="7422d-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

