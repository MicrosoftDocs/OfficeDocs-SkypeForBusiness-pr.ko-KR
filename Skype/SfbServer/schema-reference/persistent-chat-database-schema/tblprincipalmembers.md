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
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers에는 principal 구성원 자격이 포함 됩니다.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196608"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="a50ab-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="a50ab-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="a50ab-104">tblPrincipalMembers에는 principal 구성원 자격이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a50ab-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="a50ab-105">**열**</span><span class="sxs-lookup"><span data-stu-id="a50ab-105">**Columns**</span></span>

|<span data-ttu-id="a50ab-106">**열**</span><span class="sxs-lookup"><span data-stu-id="a50ab-106">**Column**</span></span>|<span data-ttu-id="a50ab-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="a50ab-107">**Type**</span></span>|<span data-ttu-id="a50ab-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="a50ab-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a50ab-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a50ab-109">prinID</span></span>  <br/> |<span data-ttu-id="a50ab-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="a50ab-110">int, not null</span></span>  <br/> |<span data-ttu-id="a50ab-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="a50ab-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a50ab-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="a50ab-112">memberADPath</span></span>  <br/> |<span data-ttu-id="a50ab-113">nvarchar (384), null 아님</span><span class="sxs-lookup"><span data-stu-id="a50ab-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a50ab-114">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a50ab-114">Distinguished name of a member.</span></span> <span data-ttu-id="a50ab-115">멤버가 principal (tblPrincipal 테이블) 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a50ab-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="a50ab-116">**핵심**</span><span class="sxs-lookup"><span data-stu-id="a50ab-116">**Keys**</span></span>

|<span data-ttu-id="a50ab-117">**열**</span><span class="sxs-lookup"><span data-stu-id="a50ab-117">**Column**</span></span>|<span data-ttu-id="a50ab-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="a50ab-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a50ab-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="a50ab-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="a50ab-120">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a50ab-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a50ab-121">prinID</span><span class="sxs-lookup"><span data-stu-id="a50ab-121">prinID</span></span>  <br/> |<span data-ttu-id="a50ab-122">TblPrincipal prinID에 조회가 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a50ab-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

