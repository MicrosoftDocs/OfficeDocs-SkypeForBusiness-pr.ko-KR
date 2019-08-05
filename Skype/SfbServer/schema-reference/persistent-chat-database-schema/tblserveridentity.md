---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity는 영구 채팅 서버 풀의 활성 채팅 서버를 포함 합니다.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196601"
---
# <a name="tblserveridentity"></a><span data-ttu-id="c3dbd-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="c3dbd-103">tblServerIdentity</span></span>
 
<span data-ttu-id="c3dbd-104">tblServerIdentity는 영구 채팅 서버 풀의 활성 채팅 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dbd-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="c3dbd-105">**열**</span><span class="sxs-lookup"><span data-stu-id="c3dbd-105">**Columns**</span></span>

|<span data-ttu-id="c3dbd-106">**열**</span><span class="sxs-lookup"><span data-stu-id="c3dbd-106">**Column**</span></span>|<span data-ttu-id="c3dbd-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="c3dbd-107">**Type**</span></span>|<span data-ttu-id="c3dbd-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="c3dbd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3dbd-109">serverID</span><span class="sxs-lookup"><span data-stu-id="c3dbd-109">serverID</span></span>  <br/> |<span data-ttu-id="c3dbd-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c3dbd-110">int, not null</span></span>  <br/> |<span data-ttu-id="c3dbd-111">서버 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dbd-111">Server ID.</span></span> <span data-ttu-id="c3dbd-112">중앙 관리 저장소의 인스턴스 ID에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dbd-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="c3dbd-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="c3dbd-113">serverAddress</span></span>  <br/> |<span data-ttu-id="c3dbd-114">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="c3dbd-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c3dbd-115">Windows Communication Foundation 주소를 사용 하는 서버 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dbd-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="c3dbd-116">Serverlast(Time)</span><span class="sxs-lookup"><span data-stu-id="c3dbd-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="c3dbd-117">dmtf</span><span class="sxs-lookup"><span data-stu-id="c3dbd-117">datetime</span></span>  <br/> |<span data-ttu-id="c3dbd-118">채널 서버가이 행을 업데이트 하 여 증거를 실행 하 고 있음을 제공 하는 최근 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dbd-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="c3dbd-119">**키**</span><span class="sxs-lookup"><span data-stu-id="c3dbd-119">**Key**</span></span>

|<span data-ttu-id="c3dbd-120">**열**</span><span class="sxs-lookup"><span data-stu-id="c3dbd-120">**Column**</span></span>|<span data-ttu-id="c3dbd-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="c3dbd-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c3dbd-122">serverID</span><span class="sxs-lookup"><span data-stu-id="c3dbd-122">serverID</span></span>  <br/> |<span data-ttu-id="c3dbd-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c3dbd-123">Primary key.</span></span>  <br/> |
   

