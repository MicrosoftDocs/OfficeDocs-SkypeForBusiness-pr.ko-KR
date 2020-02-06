---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout에는 규정 준수 이벤트를 처리 한 모든 서버가 포함 됩니다.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814656"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="042ce-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="042ce-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="042ce-104">tblComplianceFanout에는 규정 준수 이벤트를 처리 한 모든 서버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="042ce-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="042ce-105">**열**</span><span class="sxs-lookup"><span data-stu-id="042ce-105">**Columns**</span></span>

|<span data-ttu-id="042ce-106">**열**</span><span class="sxs-lookup"><span data-stu-id="042ce-106">**Column**</span></span>|<span data-ttu-id="042ce-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="042ce-107">**Type**</span></span>|<span data-ttu-id="042ce-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="042ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="042ce-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="042ce-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="042ce-110">int</span><span class="sxs-lookup"><span data-stu-id="042ce-110">int</span></span>  <br/> |<span data-ttu-id="042ce-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="042ce-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="042ce-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="042ce-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="042ce-113">int</span><span class="sxs-lookup"><span data-stu-id="042ce-113">int</span></span>  <br/> |<span data-ttu-id="042ce-114">서버 id (tblServerIdentity. serverID 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="042ce-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="042ce-115">**키**</span><span class="sxs-lookup"><span data-stu-id="042ce-115">**Key**</span></span>

|<span data-ttu-id="042ce-116">**열**</span><span class="sxs-lookup"><span data-stu-id="042ce-116">**Column**</span></span>|<span data-ttu-id="042ce-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="042ce-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="042ce-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="042ce-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="042ce-119">TblComplianceData에서 조회를 사용 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="042ce-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

