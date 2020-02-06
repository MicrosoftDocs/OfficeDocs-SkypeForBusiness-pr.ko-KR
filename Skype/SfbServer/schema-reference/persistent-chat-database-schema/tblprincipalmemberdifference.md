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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814076"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="0931c-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="0931c-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="0931c-104">tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0931c-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="0931c-105">**열**</span><span class="sxs-lookup"><span data-stu-id="0931c-105">**Columns**</span></span>

|<span data-ttu-id="0931c-106">**열**</span><span class="sxs-lookup"><span data-stu-id="0931c-106">**Column**</span></span>|<span data-ttu-id="0931c-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="0931c-107">**Type**</span></span>|<span data-ttu-id="0931c-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="0931c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0931c-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0931c-109">prinGuid</span></span>  <br/> |<span data-ttu-id="0931c-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="0931c-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="0931c-111">변경 된 그룹의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="0931c-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="0931c-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="0931c-112">memberADPath</span></span>  <br/> |<span data-ttu-id="0931c-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0931c-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="0931c-114">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0931c-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="0931c-115">memberRemoved 됨</span><span class="sxs-lookup"><span data-stu-id="0931c-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="0931c-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0931c-116">bit, not null</span></span>  <br/> |<span data-ttu-id="0931c-117">구성원이 추가 된 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="0931c-117">False if the member was added.</span></span> <span data-ttu-id="0931c-118">구성원이 제거 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="0931c-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="0931c-119">**키**</span><span class="sxs-lookup"><span data-stu-id="0931c-119">**Key**</span></span>

|<span data-ttu-id="0931c-120">**열**</span><span class="sxs-lookup"><span data-stu-id="0931c-120">**Column**</span></span>|<span data-ttu-id="0931c-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="0931c-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0931c-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="0931c-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="0931c-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0931c-123">Primary key.</span></span>  <br/> |
   

