---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 테이블에는 준수 이벤트를 처리한 모든 서버가 포함됩니다.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809798"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="ec195-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="ec195-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="ec195-104">tblComplianceFanout 테이블에는 준수 이벤트를 처리한 모든 서버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec195-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="ec195-105">**열**</span><span class="sxs-lookup"><span data-stu-id="ec195-105">**Columns**</span></span>

|<span data-ttu-id="ec195-106">**열**</span><span class="sxs-lookup"><span data-stu-id="ec195-106">**Column**</span></span>|<span data-ttu-id="ec195-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="ec195-107">**Type**</span></span>|<span data-ttu-id="ec195-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="ec195-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ec195-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ec195-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ec195-110">int</span><span class="sxs-lookup"><span data-stu-id="ec195-110">int</span></span>  <br/> |<span data-ttu-id="ec195-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ec195-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="ec195-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="ec195-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="ec195-113">int</span><span class="sxs-lookup"><span data-stu-id="ec195-113">int</span></span>  <br/> |<span data-ttu-id="ec195-114">서버 ID(tblServerIdentity.serverID 테이블에 해당됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="ec195-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="ec195-115">**키**</span><span class="sxs-lookup"><span data-stu-id="ec195-115">**Key**</span></span>

|<span data-ttu-id="ec195-116">**열**</span><span class="sxs-lookup"><span data-stu-id="ec195-116">**Column**</span></span>|<span data-ttu-id="ec195-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="ec195-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec195-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ec195-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ec195-119">tblComplianceData.cmplEventID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ec195-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

