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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout에는 규정 준수 이벤트를 처리 한 모든 서버가 포함 됩니다.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196640"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="1784c-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="1784c-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="1784c-104">tblComplianceFanout에는 규정 준수 이벤트를 처리 한 모든 서버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1784c-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="1784c-105">**열**</span><span class="sxs-lookup"><span data-stu-id="1784c-105">**Columns**</span></span>

|<span data-ttu-id="1784c-106">**열**</span><span class="sxs-lookup"><span data-stu-id="1784c-106">**Column**</span></span>|<span data-ttu-id="1784c-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="1784c-107">**Type**</span></span>|<span data-ttu-id="1784c-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="1784c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1784c-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1784c-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1784c-110">int</span><span class="sxs-lookup"><span data-stu-id="1784c-110">int</span></span>  <br/> |<span data-ttu-id="1784c-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1784c-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="1784c-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="1784c-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="1784c-113">int</span><span class="sxs-lookup"><span data-stu-id="1784c-113">int</span></span>  <br/> |<span data-ttu-id="1784c-114">서버 id (tblServerIdentity. serverID 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="1784c-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="1784c-115">**키**</span><span class="sxs-lookup"><span data-stu-id="1784c-115">**Key**</span></span>

|<span data-ttu-id="1784c-116">**열**</span><span class="sxs-lookup"><span data-stu-id="1784c-116">**Column**</span></span>|<span data-ttu-id="1784c-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="1784c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1784c-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1784c-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1784c-119">TblComplianceData에서 조회를 사용 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1784c-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

