---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations에는 읽을 수 없는 소속 (일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해)이 포함 됩니다.
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196594"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="657fa-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="657fa-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="657fa-104">tblSkippedAffiliations에는 읽을 수 없는 소속 (일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="657fa-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="657fa-105">**열**</span><span class="sxs-lookup"><span data-stu-id="657fa-105">**Columns**</span></span>

|<span data-ttu-id="657fa-106">**열**</span><span class="sxs-lookup"><span data-stu-id="657fa-106">**Column**</span></span>|<span data-ttu-id="657fa-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="657fa-107">**Type**</span></span>|<span data-ttu-id="657fa-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="657fa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="657fa-109">prinID</span><span class="sxs-lookup"><span data-stu-id="657fa-109">prinID</span></span>  <br/> |<span data-ttu-id="657fa-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="657fa-110">int, not null</span></span>  <br/> |<span data-ttu-id="657fa-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="657fa-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="657fa-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="657fa-112">affDescription</span></span>  <br/> |<span data-ttu-id="657fa-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="657fa-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="657fa-114">소속을 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="657fa-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="657fa-115">형식: guid: _{0}_ uri: _{1}_> id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="657fa-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="657fa-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="657fa-116">updatedBy</span></span>  <br/> |<span data-ttu-id="657fa-117">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="657fa-117">int, not null</span></span>  <br/> |<span data-ttu-id="657fa-118">이 행을 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="657fa-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="657fa-119">Active Directory 동기화가 이러한 항목에 대 한 유일한 원본 이므로 항상 1 (시스템 사용자)입니다.</span><span class="sxs-lookup"><span data-stu-id="657fa-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="657fa-120">**핵심**</span><span class="sxs-lookup"><span data-stu-id="657fa-120">**Keys**</span></span>

|<span data-ttu-id="657fa-121">**개 열**</span><span class="sxs-lookup"><span data-stu-id="657fa-121">**Column(s)**</span></span>|<span data-ttu-id="657fa-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="657fa-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="657fa-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="657fa-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="657fa-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="657fa-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="657fa-125">prinID</span><span class="sxs-lookup"><span data-stu-id="657fa-125">prinID</span></span>  <br/> |<span data-ttu-id="657fa-126">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="657fa-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

