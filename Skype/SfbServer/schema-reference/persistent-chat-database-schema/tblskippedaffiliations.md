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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations에는 읽을 수 없는 소속 (일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해)이 포함 됩니다.
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812016"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="b0e97-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="b0e97-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="b0e97-104">tblSkippedAffiliations에는 읽을 수 없는 소속 (일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e97-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="b0e97-105">**열**</span><span class="sxs-lookup"><span data-stu-id="b0e97-105">**Columns**</span></span>

|<span data-ttu-id="b0e97-106">**열**</span><span class="sxs-lookup"><span data-stu-id="b0e97-106">**Column**</span></span>|<span data-ttu-id="b0e97-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="b0e97-107">**Type**</span></span>|<span data-ttu-id="b0e97-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="b0e97-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b0e97-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b0e97-109">prinID</span></span>  <br/> |<span data-ttu-id="b0e97-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="b0e97-110">int, not null</span></span>  <br/> |<span data-ttu-id="b0e97-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="b0e97-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b0e97-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="b0e97-112">affDescription</span></span>  <br/> |<span data-ttu-id="b0e97-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="b0e97-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b0e97-114">소속을 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e97-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="b0e97-115">형식: guid: _{0}_ uri: _{1}_> id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="b0e97-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="b0e97-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="b0e97-116">updatedBy</span></span>  <br/> |<span data-ttu-id="b0e97-117">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="b0e97-117">int, not null</span></span>  <br/> |<span data-ttu-id="b0e97-118">이 행을 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e97-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="b0e97-119">Active Directory 동기화가 이러한 항목에 대 한 유일한 원본 이므로 항상 1 (시스템 사용자)입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e97-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="b0e97-120">**핵심**</span><span class="sxs-lookup"><span data-stu-id="b0e97-120">**Keys**</span></span>

|<span data-ttu-id="b0e97-121">**개 열**</span><span class="sxs-lookup"><span data-stu-id="b0e97-121">**Column(s)**</span></span>|<span data-ttu-id="b0e97-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="b0e97-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e97-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="b0e97-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="b0e97-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e97-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b0e97-125">prinID</span><span class="sxs-lookup"><span data-stu-id="b0e97-125">prinID</span></span>  <br/> |<span data-ttu-id="b0e97-126">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e97-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

