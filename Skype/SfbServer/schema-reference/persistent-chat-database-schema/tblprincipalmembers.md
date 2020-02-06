---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers에는 principal 구성원 자격이 포함 됩니다.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813946"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="0ed0c-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="0ed0c-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="0ed0c-104">tblPrincipalMembers에는 principal 구성원 자격이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0c-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="0ed0c-105">**열**</span><span class="sxs-lookup"><span data-stu-id="0ed0c-105">**Columns**</span></span>

|<span data-ttu-id="0ed0c-106">**열**</span><span class="sxs-lookup"><span data-stu-id="0ed0c-106">**Column**</span></span>|<span data-ttu-id="0ed0c-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="0ed0c-107">**Type**</span></span>|<span data-ttu-id="0ed0c-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="0ed0c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ed0c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="0ed0c-109">prinID</span></span>  <br/> |<span data-ttu-id="0ed0c-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="0ed0c-110">int, not null</span></span>  <br/> |<span data-ttu-id="0ed0c-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="0ed0c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="0ed0c-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="0ed0c-112">memberADPath</span></span>  <br/> |<span data-ttu-id="0ed0c-113">nvarchar (384), null 아님</span><span class="sxs-lookup"><span data-stu-id="0ed0c-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="0ed0c-114">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0c-114">Distinguished name of a member.</span></span> <span data-ttu-id="0ed0c-115">멤버가 principal (tblPrincipal 테이블) 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0c-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="0ed0c-116">**핵심**</span><span class="sxs-lookup"><span data-stu-id="0ed0c-116">**Keys**</span></span>

|<span data-ttu-id="0ed0c-117">**열**</span><span class="sxs-lookup"><span data-stu-id="0ed0c-117">**Column**</span></span>|<span data-ttu-id="0ed0c-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="0ed0c-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0ed0c-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="0ed0c-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="0ed0c-120">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0c-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0ed0c-121">prinID</span><span class="sxs-lookup"><span data-stu-id="0ed0c-121">prinID</span></span>  <br/> |<span data-ttu-id="0ed0c-122">TblPrincipal prinID에 조회가 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0c-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

