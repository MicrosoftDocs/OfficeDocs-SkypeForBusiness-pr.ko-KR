---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations에는 일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해 읽을 수 없는 정보가 포함되어 있습니다.
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831428"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="ca541-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="ca541-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="ca541-104">tblSkippedAffiliations에는 일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해 읽을 수 없는 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca541-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="ca541-105">**열**</span><span class="sxs-lookup"><span data-stu-id="ca541-105">**Columns**</span></span>

|<span data-ttu-id="ca541-106">**열**</span><span class="sxs-lookup"><span data-stu-id="ca541-106">**Column**</span></span>|<span data-ttu-id="ca541-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="ca541-107">**Type**</span></span>|<span data-ttu-id="ca541-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="ca541-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ca541-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ca541-109">prinID</span></span>  <br/> |<span data-ttu-id="ca541-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ca541-110">int, not null</span></span>  <br/> |<span data-ttu-id="ca541-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ca541-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ca541-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="ca541-112">affDescription</span></span>  <br/> |<span data-ttu-id="ca541-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="ca541-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ca541-114">회원 정보를 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ca541-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="ca541-115">형식은 guid:  _{0}_ uri: _{1}_> ID입니다.  _{2}_</span><span class="sxs-lookup"><span data-stu-id="ca541-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="ca541-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ca541-116">updatedBy</span></span>  <br/> |<span data-ttu-id="ca541-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ca541-117">int, not null</span></span>  <br/> |<span data-ttu-id="ca541-p101">이 행을 업데이트한 사용자의 ID입니다. 이러한 항목에 대해서는 Active Directory 동기화가 유일한 소스이므로 이 값은 항상 1(시스템 사용자)입니다.</span><span class="sxs-lookup"><span data-stu-id="ca541-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="ca541-120">**키**</span><span class="sxs-lookup"><span data-stu-id="ca541-120">**Keys**</span></span>

|<span data-ttu-id="ca541-121">**Column(s)**</span><span class="sxs-lookup"><span data-stu-id="ca541-121">**Column(s)**</span></span>|<span data-ttu-id="ca541-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="ca541-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="ca541-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ca541-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ca541-124">prinID</span><span class="sxs-lookup"><span data-stu-id="ca541-124">prinID</span></span>  <br/> |<span data-ttu-id="ca541-125">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ca541-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

