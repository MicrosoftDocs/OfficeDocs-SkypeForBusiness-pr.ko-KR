---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations에는 Active Directory 도메인 서비스 보안 그룹을 비롯한 위치의 구성원 자격을 도메인의 Active Directory 컨테이너에 설명하는 보안 주체 정보가 포함되어 있습니다.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815868"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="02ad3-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="02ad3-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="02ad3-104">tblPrincipalAffiliations에는 Active Directory 도메인 서비스 보안 그룹을 비롯한 위치의 구성원 자격을 도메인의 Active Directory 컨테이너에 설명하는 보안 주체 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="02ad3-105">**열**</span><span class="sxs-lookup"><span data-stu-id="02ad3-105">**Columns**</span></span>

|<span data-ttu-id="02ad3-106">**열**</span><span class="sxs-lookup"><span data-stu-id="02ad3-106">**Column**</span></span>|<span data-ttu-id="02ad3-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="02ad3-107">**Type**</span></span>|<span data-ttu-id="02ad3-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="02ad3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="02ad3-109">principalID</span><span class="sxs-lookup"><span data-stu-id="02ad3-109">principalID</span></span>  <br/> |<span data-ttu-id="02ad3-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02ad3-110">int, not null</span></span>  <br/> |<span data-ttu-id="02ad3-111">연관된 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="02ad3-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="02ad3-112">affiliationID</span></span>  <br/> |<span data-ttu-id="02ad3-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02ad3-113">int, not null</span></span>  <br/> |<span data-ttu-id="02ad3-p101">회원 정보를 나타내는 사용자의 ID입니다. 각 사용자(system-user-types 제외)에는 self-affiliation도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="02ad3-116">index</span><span class="sxs-lookup"><span data-stu-id="02ad3-116">index</span></span>  <br/> |<span data-ttu-id="02ad3-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02ad3-117">int, not null</span></span>  <br/> |<span data-ttu-id="02ad3-118">색인입니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-118">Index.</span></span> <span data-ttu-id="02ad3-119">자체 소속 값은 -1로, 다른 소속의 경우 각 버킷 내에서 1부터 일차적으로 \<principalID, affiliationId\> 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="02ad3-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="02ad3-120">updatedBy</span></span>  <br/> |<span data-ttu-id="02ad3-121">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02ad3-121">int, not null</span></span>  <br/> |<span data-ttu-id="02ad3-p103">최근 업데이트를 수행한 사용자입니다. 이 값은 일반적으로 Active Directory 동기화를 의미하는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="02ad3-124">**키**</span><span class="sxs-lookup"><span data-stu-id="02ad3-124">**Keys**</span></span>

|<span data-ttu-id="02ad3-125">**열**</span><span class="sxs-lookup"><span data-stu-id="02ad3-125">**Columns**</span></span>|<span data-ttu-id="02ad3-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="02ad3-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="02ad3-127">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="02ad3-128">principalID</span><span class="sxs-lookup"><span data-stu-id="02ad3-128">principalID</span></span>  <br/> |<span data-ttu-id="02ad3-129">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="02ad3-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="02ad3-130">affiliationID</span></span>  <br/> |<span data-ttu-id="02ad3-131">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="02ad3-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

