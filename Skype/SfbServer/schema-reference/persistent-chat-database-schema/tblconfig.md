---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814626"
---
# <a name="tblconfig"></a><span data-ttu-id="d3968-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="d3968-103">tblConfig</span></span>
 
<span data-ttu-id="d3968-104">tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3968-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="d3968-105">**열**</span><span class="sxs-lookup"><span data-stu-id="d3968-105">**Columns**</span></span>

|<span data-ttu-id="d3968-106">**열**</span><span class="sxs-lookup"><span data-stu-id="d3968-106">**Column**</span></span>|<span data-ttu-id="d3968-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="d3968-107">**Type**</span></span>|<span data-ttu-id="d3968-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="d3968-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3968-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="d3968-109">configLabel</span></span>  <br/> |<span data-ttu-id="d3968-110">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="d3968-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d3968-111">"Pool"를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3968-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="d3968-112">configContent</span><span class="sxs-lookup"><span data-stu-id="d3968-112">configContent</span></span>  <br/> |<span data-ttu-id="d3968-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="d3968-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="d3968-114">구성 콘텐츠.</span><span class="sxs-lookup"><span data-stu-id="d3968-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="d3968-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="d3968-115">configPoolID</span></span>  <br/> |<span data-ttu-id="d3968-116">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="d3968-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="d3968-117">데이터베이스 인스턴스의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d3968-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="d3968-118">**키**</span><span class="sxs-lookup"><span data-stu-id="d3968-118">**Key**</span></span>

|<span data-ttu-id="d3968-119">**열**</span><span class="sxs-lookup"><span data-stu-id="d3968-119">**Column**</span></span>|<span data-ttu-id="d3968-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="d3968-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3968-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="d3968-121">configLabel</span></span>  <br/> |<span data-ttu-id="d3968-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d3968-122">Primary key.</span></span>  <br/> |
   

