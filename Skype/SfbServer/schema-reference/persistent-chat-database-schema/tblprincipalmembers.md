---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers에는 사용자 구성원 자격이 포함됩니다.
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831598"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="e4a45-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="e4a45-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="e4a45-104">tblPrincipalMembers에는 사용자 구성원 자격이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a45-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="e4a45-105">**열**</span><span class="sxs-lookup"><span data-stu-id="e4a45-105">**Columns**</span></span>

|<span data-ttu-id="e4a45-106">**열**</span><span class="sxs-lookup"><span data-stu-id="e4a45-106">**Column**</span></span>|<span data-ttu-id="e4a45-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="e4a45-107">**Type**</span></span>|<span data-ttu-id="e4a45-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="e4a45-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4a45-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e4a45-109">prinID</span></span>  <br/> |<span data-ttu-id="e4a45-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e4a45-110">int, not null</span></span>  <br/> |<span data-ttu-id="e4a45-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a45-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e4a45-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="e4a45-112">memberADPath</span></span>  <br/> |<span data-ttu-id="e4a45-113">nvarchar(384), null이 아님</span><span class="sxs-lookup"><span data-stu-id="e4a45-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="e4a45-p101">구성원의 고유 이름입니다. 구성원은 tblPrincipal 테이블의 사용자일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a45-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="e4a45-116">**키**</span><span class="sxs-lookup"><span data-stu-id="e4a45-116">**Keys**</span></span>

|<span data-ttu-id="e4a45-117">**열**</span><span class="sxs-lookup"><span data-stu-id="e4a45-117">**Column**</span></span>|<span data-ttu-id="e4a45-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="e4a45-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="e4a45-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a45-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e4a45-120">prinID</span><span class="sxs-lookup"><span data-stu-id="e4a45-120">prinID</span></span>  <br/> |<span data-ttu-id="e4a45-121">tblPrincipal.prinID에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a45-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

