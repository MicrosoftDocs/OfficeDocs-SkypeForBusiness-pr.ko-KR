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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196636"
---
# <a name="tblconfig"></a><span data-ttu-id="a3aa1-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="a3aa1-103">tblConfig</span></span>
 
<span data-ttu-id="a3aa1-104">tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa1-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="a3aa1-105">**열**</span><span class="sxs-lookup"><span data-stu-id="a3aa1-105">**Columns**</span></span>

|<span data-ttu-id="a3aa1-106">**열**</span><span class="sxs-lookup"><span data-stu-id="a3aa1-106">**Column**</span></span>|<span data-ttu-id="a3aa1-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="a3aa1-107">**Type**</span></span>|<span data-ttu-id="a3aa1-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="a3aa1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3aa1-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="a3aa1-109">configLabel</span></span>  <br/> |<span data-ttu-id="a3aa1-110">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="a3aa1-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a3aa1-111">"Pool"를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa1-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="a3aa1-112">configContent</span><span class="sxs-lookup"><span data-stu-id="a3aa1-112">configContent</span></span>  <br/> |<span data-ttu-id="a3aa1-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a3aa1-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="a3aa1-114">구성 콘텐츠.</span><span class="sxs-lookup"><span data-stu-id="a3aa1-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="a3aa1-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="a3aa1-115">configPoolID</span></span>  <br/> |<span data-ttu-id="a3aa1-116">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="a3aa1-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="a3aa1-117">데이터베이스 인스턴스의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa1-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="a3aa1-118">**키**</span><span class="sxs-lookup"><span data-stu-id="a3aa1-118">**Key**</span></span>

|<span data-ttu-id="a3aa1-119">**열**</span><span class="sxs-lookup"><span data-stu-id="a3aa1-119">**Column**</span></span>|<span data-ttu-id="a3aa1-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="a3aa1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3aa1-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="a3aa1-121">configLabel</span></span>  <br/> |<span data-ttu-id="a3aa1-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa1-122">Primary key.</span></span>  <br/> |
   

