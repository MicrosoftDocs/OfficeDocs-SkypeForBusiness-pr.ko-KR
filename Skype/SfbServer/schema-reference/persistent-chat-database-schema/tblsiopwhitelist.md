---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList는 노드와 연결할 수 있는 등록 된 추가 기능 목록입니다.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812116"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="87c8f-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="87c8f-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="87c8f-104">tblSiopWhiteList는 노드와 연결할 수 있는 등록 된 추가 기능 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="87c8f-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="87c8f-105">**열**</span><span class="sxs-lookup"><span data-stu-id="87c8f-105">**Columns**</span></span>

|<span data-ttu-id="87c8f-106">**열**</span><span class="sxs-lookup"><span data-stu-id="87c8f-106">**Column**</span></span>|<span data-ttu-id="87c8f-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="87c8f-107">**Type**</span></span>|<span data-ttu-id="87c8f-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="87c8f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="87c8f-109">siopID</span><span class="sxs-lookup"><span data-stu-id="87c8f-109">siopID</span></span>  <br/> |<span data-ttu-id="87c8f-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="87c8f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="87c8f-111">추가 기능의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="87c8f-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="87c8f-112">siopName</span><span class="sxs-lookup"><span data-stu-id="87c8f-112">siopName</span></span>  <br/> |<span data-ttu-id="87c8f-113">nvarchar (50), null 아님</span><span class="sxs-lookup"><span data-stu-id="87c8f-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="87c8f-114">Display-추가 기능의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="87c8f-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="87c8f-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="87c8f-115">siopUrl</span></span>  <br/> |<span data-ttu-id="87c8f-116">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="87c8f-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="87c8f-117">추가 기능의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="87c8f-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="87c8f-118">**키**</span><span class="sxs-lookup"><span data-stu-id="87c8f-118">**Key**</span></span>

|<span data-ttu-id="87c8f-119">**열**</span><span class="sxs-lookup"><span data-stu-id="87c8f-119">**Column**</span></span>|<span data-ttu-id="87c8f-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="87c8f-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="87c8f-121">siopID</span><span class="sxs-lookup"><span data-stu-id="87c8f-121">siopID</span></span>  <br/> |<span data-ttu-id="87c8f-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="87c8f-122">Primary key.</span></span>  <br/> |
   

