---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig에는 일부 영구 채팅 서버 지원되지 않는 구성이 한 행에 포함되어 있습니다.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809738"
---
# <a name="tblconfig"></a><span data-ttu-id="de438-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="de438-103">tblConfig</span></span>
 
<span data-ttu-id="de438-104">tblConfig에는 일부 영구 채팅 서버 지원되지 않는 구성이 한 행에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de438-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="de438-105">**열**</span><span class="sxs-lookup"><span data-stu-id="de438-105">**Columns**</span></span>

|<span data-ttu-id="de438-106">**열**</span><span class="sxs-lookup"><span data-stu-id="de438-106">**Column**</span></span>|<span data-ttu-id="de438-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="de438-107">**Type**</span></span>|<span data-ttu-id="de438-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="de438-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de438-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="de438-109">configLabel</span></span>  <br/> |<span data-ttu-id="de438-110">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="de438-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="de438-111">"풀"을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="de438-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="de438-112">configContent</span><span class="sxs-lookup"><span data-stu-id="de438-112">configContent</span></span>  <br/> |<span data-ttu-id="de438-113">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="de438-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="de438-114">구성 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="de438-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="de438-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="de438-115">configPoolID</span></span>  <br/> |<span data-ttu-id="de438-116">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="de438-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="de438-117">데이터베이스 인스턴스의 고유한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="de438-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="de438-118">**키**</span><span class="sxs-lookup"><span data-stu-id="de438-118">**Key**</span></span>

|<span data-ttu-id="de438-119">**열**</span><span class="sxs-lookup"><span data-stu-id="de438-119">**Column**</span></span>|<span data-ttu-id="de438-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="de438-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="de438-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="de438-121">configLabel</span></span>  <br/> |<span data-ttu-id="de438-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="de438-122">Primary key.</span></span>  <br/> |
   

