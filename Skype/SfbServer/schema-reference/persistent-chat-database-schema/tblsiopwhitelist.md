---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList는 노드와 연결할 수 있는 등록된 추가 기능 목록입니다.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831488"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="914fd-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="914fd-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="914fd-104">tblSiopWhiteList는 노드와 연결할 수 있는 등록된 추가 기능 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="914fd-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="914fd-105">**열**</span><span class="sxs-lookup"><span data-stu-id="914fd-105">**Columns**</span></span>

|<span data-ttu-id="914fd-106">**열**</span><span class="sxs-lookup"><span data-stu-id="914fd-106">**Column**</span></span>|<span data-ttu-id="914fd-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="914fd-107">**Type**</span></span>|<span data-ttu-id="914fd-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="914fd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="914fd-109">siopID</span><span class="sxs-lookup"><span data-stu-id="914fd-109">siopID</span></span>  <br/> |<span data-ttu-id="914fd-110">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="914fd-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="914fd-111">추가 기능의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="914fd-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="914fd-112">siopName</span><span class="sxs-lookup"><span data-stu-id="914fd-112">siopName</span></span>  <br/> |<span data-ttu-id="914fd-113">nvarchar(50), null이 아님</span><span class="sxs-lookup"><span data-stu-id="914fd-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="914fd-114">추가 기능의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="914fd-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="914fd-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="914fd-115">siopUrl</span></span>  <br/> |<span data-ttu-id="914fd-116">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="914fd-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="914fd-117">추가 기능의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="914fd-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="914fd-118">**키**</span><span class="sxs-lookup"><span data-stu-id="914fd-118">**Key**</span></span>

|<span data-ttu-id="914fd-119">**열**</span><span class="sxs-lookup"><span data-stu-id="914fd-119">**Column**</span></span>|<span data-ttu-id="914fd-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="914fd-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="914fd-121">siopID</span><span class="sxs-lookup"><span data-stu-id="914fd-121">siopID</span></span>  <br/> |<span data-ttu-id="914fd-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="914fd-122">Primary key.</span></span>  <br/> |
   

