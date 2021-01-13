---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity에는 영구 채팅 서버 풀의 활성 채팅 서버가 포함되어 있습니다.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831498"
---
# <a name="tblserveridentity"></a><span data-ttu-id="c95f7-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="c95f7-103">tblServerIdentity</span></span>
 
<span data-ttu-id="c95f7-104">tblServerIdentity에는 영구 채팅 서버 풀의 활성 채팅 서버가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f7-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="c95f7-105">**열**</span><span class="sxs-lookup"><span data-stu-id="c95f7-105">**Columns**</span></span>

|<span data-ttu-id="c95f7-106">**열**</span><span class="sxs-lookup"><span data-stu-id="c95f7-106">**Column**</span></span>|<span data-ttu-id="c95f7-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="c95f7-107">**Type**</span></span>|<span data-ttu-id="c95f7-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="c95f7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c95f7-109">serverID</span><span class="sxs-lookup"><span data-stu-id="c95f7-109">serverID</span></span>  <br/> |<span data-ttu-id="c95f7-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="c95f7-110">int, not null</span></span>  <br/> |<span data-ttu-id="c95f7-111">서버 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c95f7-111">Server ID.</span></span> <span data-ttu-id="c95f7-112">중앙 관리 저장소의 인스턴스 ID에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f7-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="c95f7-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="c95f7-113">serverAddress</span></span>  <br/> |<span data-ttu-id="c95f7-114">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="c95f7-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c95f7-115">Windows Communication Foundation 주소를 사용 중인 서버 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c95f7-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="c95f7-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="c95f7-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="c95f7-117">datetime</span><span class="sxs-lookup"><span data-stu-id="c95f7-117">datetime</span></span>  <br/> |<span data-ttu-id="c95f7-118">실행 중임에 대한 증거를 제공하기 위해 채널 서버가 이 행을 마지막으로 업데이트한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c95f7-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="c95f7-119">**키**</span><span class="sxs-lookup"><span data-stu-id="c95f7-119">**Key**</span></span>

|<span data-ttu-id="c95f7-120">**열**</span><span class="sxs-lookup"><span data-stu-id="c95f7-120">**Column**</span></span>|<span data-ttu-id="c95f7-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="c95f7-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c95f7-122">serverID</span><span class="sxs-lookup"><span data-stu-id="c95f7-122">serverID</span></span>  <br/> |<span data-ttu-id="c95f7-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c95f7-123">Primary key.</span></span>  <br/> |
   

