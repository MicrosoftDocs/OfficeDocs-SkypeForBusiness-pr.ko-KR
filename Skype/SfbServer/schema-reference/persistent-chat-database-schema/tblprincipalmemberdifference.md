---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196614"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="8b9bc-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="8b9bc-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="8b9bc-104">tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9bc-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="8b9bc-105">**열**</span><span class="sxs-lookup"><span data-stu-id="8b9bc-105">**Columns**</span></span>

|<span data-ttu-id="8b9bc-106">**열**</span><span class="sxs-lookup"><span data-stu-id="8b9bc-106">**Column**</span></span>|<span data-ttu-id="8b9bc-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="8b9bc-107">**Type**</span></span>|<span data-ttu-id="8b9bc-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="8b9bc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b9bc-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8b9bc-109">prinGuid</span></span>  <br/> |<span data-ttu-id="8b9bc-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="8b9bc-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="8b9bc-111">변경 된 그룹의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9bc-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="8b9bc-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="8b9bc-112">memberADPath</span></span>  <br/> |<span data-ttu-id="8b9bc-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8b9bc-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="8b9bc-114">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9bc-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="8b9bc-115">memberRemoved 됨</span><span class="sxs-lookup"><span data-stu-id="8b9bc-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="8b9bc-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="8b9bc-116">bit, not null</span></span>  <br/> |<span data-ttu-id="8b9bc-117">구성원이 추가 된 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9bc-117">False if the member was added.</span></span> <span data-ttu-id="8b9bc-118">구성원이 제거 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9bc-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="8b9bc-119">**키**</span><span class="sxs-lookup"><span data-stu-id="8b9bc-119">**Key**</span></span>

|<span data-ttu-id="8b9bc-120">**열**</span><span class="sxs-lookup"><span data-stu-id="8b9bc-120">**Column**</span></span>|<span data-ttu-id="8b9bc-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="8b9bc-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b9bc-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="8b9bc-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="8b9bc-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9bc-123">Primary key.</span></span>  <br/> |
   

