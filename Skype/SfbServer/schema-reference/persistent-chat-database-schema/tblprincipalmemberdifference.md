---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리하지 않은 그룹 구성원 변경(구성원 추가 및 제거된 구성원 모두)이 포함되어 있습니다.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809708"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="5494d-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="5494d-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="5494d-104">tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리하지 않은 그룹 구성원 변경(구성원 추가 및 제거된 구성원 모두)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5494d-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="5494d-105">**열**</span><span class="sxs-lookup"><span data-stu-id="5494d-105">**Columns**</span></span>

|<span data-ttu-id="5494d-106">**열**</span><span class="sxs-lookup"><span data-stu-id="5494d-106">**Column**</span></span>|<span data-ttu-id="5494d-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="5494d-107">**Type**</span></span>|<span data-ttu-id="5494d-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="5494d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5494d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="5494d-109">prinGuid</span></span>  <br/> |<span data-ttu-id="5494d-110">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5494d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="5494d-111">변경된 그룹의 사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="5494d-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="5494d-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="5494d-112">memberADPath</span></span>  <br/> |<span data-ttu-id="5494d-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5494d-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="5494d-114">구성원의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5494d-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="5494d-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="5494d-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="5494d-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5494d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5494d-p101">구성원이 추가된 경우 False입니다. 구성원이 제거된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5494d-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="5494d-119">**키**</span><span class="sxs-lookup"><span data-stu-id="5494d-119">**Key**</span></span>

|<span data-ttu-id="5494d-120">**열**</span><span class="sxs-lookup"><span data-stu-id="5494d-120">**Column**</span></span>|<span data-ttu-id="5494d-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="5494d-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="5494d-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5494d-122">Primary key.</span></span>  <br/> |
   

