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
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList는 노드와 연결할 수 있는 등록 된 추가 기능 목록입니다.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196597"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="d36cc-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="d36cc-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="d36cc-104">tblSiopWhiteList는 노드와 연결할 수 있는 등록 된 추가 기능 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d36cc-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="d36cc-105">**열**</span><span class="sxs-lookup"><span data-stu-id="d36cc-105">**Columns**</span></span>

|<span data-ttu-id="d36cc-106">**열**</span><span class="sxs-lookup"><span data-stu-id="d36cc-106">**Column**</span></span>|<span data-ttu-id="d36cc-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="d36cc-107">**Type**</span></span>|<span data-ttu-id="d36cc-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="d36cc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d36cc-109">siopID</span><span class="sxs-lookup"><span data-stu-id="d36cc-109">siopID</span></span>  <br/> |<span data-ttu-id="d36cc-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="d36cc-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d36cc-111">추가 기능의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="d36cc-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d36cc-112">siopName</span><span class="sxs-lookup"><span data-stu-id="d36cc-112">siopName</span></span>  <br/> |<span data-ttu-id="d36cc-113">nvarchar (50), null 아님</span><span class="sxs-lookup"><span data-stu-id="d36cc-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="d36cc-114">Display-추가 기능의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d36cc-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d36cc-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="d36cc-115">siopUrl</span></span>  <br/> |<span data-ttu-id="d36cc-116">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="d36cc-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d36cc-117">추가 기능의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="d36cc-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="d36cc-118">**키**</span><span class="sxs-lookup"><span data-stu-id="d36cc-118">**Key**</span></span>

|<span data-ttu-id="d36cc-119">**열**</span><span class="sxs-lookup"><span data-stu-id="d36cc-119">**Column**</span></span>|<span data-ttu-id="d36cc-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="d36cc-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d36cc-121">siopID</span><span class="sxs-lookup"><span data-stu-id="d36cc-121">siopID</span></span>  <br/> |<span data-ttu-id="d36cc-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d36cc-122">Primary key.</span></span>  <br/> |
   

