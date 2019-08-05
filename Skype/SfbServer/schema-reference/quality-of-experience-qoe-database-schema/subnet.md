---
title: Subnet 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 서브넷 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196520"
---
# <a name="subnet-table"></a><span data-ttu-id="fa0af-104">Subnet 테이블</span><span class="sxs-lookup"><span data-stu-id="fa0af-104">Subnet table</span></span>
 
<span data-ttu-id="fa0af-105">서브넷 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0af-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="fa0af-106">각 레코드는 네트워크 구성 설정에 정의 된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa0af-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="fa0af-107">**열**</span><span class="sxs-lookup"><span data-stu-id="fa0af-107">**Column**</span></span>|<span data-ttu-id="fa0af-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="fa0af-108">**Data Type**</span></span>|<span data-ttu-id="fa0af-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="fa0af-109">**Key/Index**</span></span>|<span data-ttu-id="fa0af-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="fa0af-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fa0af-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="fa0af-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="fa0af-112">int</span><span class="sxs-lookup"><span data-stu-id="fa0af-112">int</span></span>  <br/> |<span data-ttu-id="fa0af-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="fa0af-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fa0af-114">서브넷 IP에 대 한 정수 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0af-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="fa0af-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="fa0af-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="fa0af-116">int</span><span class="sxs-lookup"><span data-stu-id="fa0af-116">int</span></span>  <br/> ||<span data-ttu-id="fa0af-117">서브넷 마스크.</span><span class="sxs-lookup"><span data-stu-id="fa0af-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="fa0af-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="fa0af-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="fa0af-119">int</span><span class="sxs-lookup"><span data-stu-id="fa0af-119">int</span></span>  <br/> |<span data-ttu-id="fa0af-120">외부</span><span class="sxs-lookup"><span data-stu-id="fa0af-120">Foreign</span></span>  <br/> |<span data-ttu-id="fa0af-121">[Usersite 테이블](usersite.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0af-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="fa0af-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="fa0af-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="fa0af-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="fa0af-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="fa0af-124">서브넷에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0af-124">The description for the subnet.</span></span>  <br/> |
   

