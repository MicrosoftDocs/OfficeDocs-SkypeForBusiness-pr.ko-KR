---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations active directory 컨테이너에서 Active Directory 도메인 서비스 보안 그룹을 포함 한 위치의 구성원 자격을 도메인에 설명 하는 주요 소속을 포함 합니다.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196616"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="50109-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="50109-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="50109-104">tblPrincipalAffiliations active directory 컨테이너에서 Active Directory 도메인 서비스 보안 그룹을 포함 한 위치의 구성원 자격을 도메인에 설명 하는 주요 소속을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="50109-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="50109-105">**열**</span><span class="sxs-lookup"><span data-stu-id="50109-105">**Columns**</span></span>

|<span data-ttu-id="50109-106">**열**</span><span class="sxs-lookup"><span data-stu-id="50109-106">**Column**</span></span>|<span data-ttu-id="50109-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="50109-107">**Type**</span></span>|<span data-ttu-id="50109-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="50109-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="50109-109">principalID</span><span class="sxs-lookup"><span data-stu-id="50109-109">principalID</span></span>  <br/> |<span data-ttu-id="50109-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="50109-110">int, not null</span></span>  <br/> |<span data-ttu-id="50109-111">관련 된 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="50109-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="50109-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="50109-112">affiliationID</span></span>  <br/> |<span data-ttu-id="50109-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="50109-113">int, not null</span></span>  <br/> |<span data-ttu-id="50109-114">소속을 나타내는 주체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="50109-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="50109-115">각 주도자 (시스템-사용자 유형 제외)에는 자기 관련 된 것도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50109-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="50109-116">색인</span><span class="sxs-lookup"><span data-stu-id="50109-116">index</span></span>  <br/> |<span data-ttu-id="50109-117">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="50109-117">int, not null</span></span>  <br/> |<span data-ttu-id="50109-118">색인.</span><span class="sxs-lookup"><span data-stu-id="50109-118">Index.</span></span> <span data-ttu-id="50109-119">자기 소속에 대 한 값은-1 이며, 다른 소속은 각 \<principalid, affiliationId\> 버킷에 있는 1에서 순차적으로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="50109-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="50109-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="50109-120">updatedBy</span></span>  <br/> |<span data-ttu-id="50109-121">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="50109-121">int, not null</span></span>  <br/> |<span data-ttu-id="50109-122">최신 업데이트를 수행한 보안 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="50109-122">Principal that did the latest update.</span></span> <span data-ttu-id="50109-123">이는 일반적으로 Active Directory 동기화를 의미 하는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="50109-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="50109-124">**핵심**</span><span class="sxs-lookup"><span data-stu-id="50109-124">**Keys**</span></span>

|<span data-ttu-id="50109-125">**열**</span><span class="sxs-lookup"><span data-stu-id="50109-125">**Columns**</span></span>|<span data-ttu-id="50109-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="50109-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="50109-127">\<principalID, index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="50109-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="50109-128">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="50109-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="50109-129">principalID</span><span class="sxs-lookup"><span data-stu-id="50109-129">principalID</span></span>  <br/> |<span data-ttu-id="50109-130">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="50109-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="50109-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="50109-131">affiliationID</span></span>  <br/> |<span data-ttu-id="50109-132">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="50109-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

