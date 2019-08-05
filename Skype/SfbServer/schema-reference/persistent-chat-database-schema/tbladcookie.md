---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196651"
---
# <a name="tbladcookie"></a><span data-ttu-id="e3b82-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="e3b82-103">tblADCookie</span></span>
 
<span data-ttu-id="e3b82-104">tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="e3b82-105">**열**</span><span class="sxs-lookup"><span data-stu-id="e3b82-105">**Columns**</span></span>

|<span data-ttu-id="e3b82-106">**열**</span><span class="sxs-lookup"><span data-stu-id="e3b82-106">**Column**</span></span>|<span data-ttu-id="e3b82-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="e3b82-107">**Type**</span></span>|<span data-ttu-id="e3b82-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="e3b82-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3b82-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3b82-109">prinGuid</span></span>  <br/> |<span data-ttu-id="e3b82-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="e3b82-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="e3b82-111">모니터링 중인 도메인의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="e3b82-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="e3b82-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="e3b82-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="e3b82-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="e3b82-114">Active Directory 도메인 서비스 동기화에 사용 되는 현재 도메인 컨트롤러의 FQDN (정규화 된 도메인 이름)입니다. 정보 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="e3b82-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="e3b82-115">adcContent</span></span>  <br/> |<span data-ttu-id="e3b82-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="e3b82-116">image (binary)</span></span>  <br/> |<span data-ttu-id="e3b82-117">Active Directory 동기화 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="e3b82-118">lastUpdated 됨</span><span class="sxs-lookup"><span data-stu-id="e3b82-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="e3b82-119">dmtf</span><span class="sxs-lookup"><span data-stu-id="e3b82-119">datetime</span></span>  <br/> |<span data-ttu-id="e3b82-120">행 업데이트 시간이 포함 된 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="e3b82-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="e3b82-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="e3b82-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="e3b82-122">datetime</span></span>  <br/> |<span data-ttu-id="e3b82-123">행이 변경 내용에 맞게 잠길 때 까지의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="e3b82-124">이는 채팅 서비스 중 하나만 Active Directory Sync를 한 번에 수행 하도록 하는 소프트웨어 연동 메커니즘의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="e3b82-125">**핵심**</span><span class="sxs-lookup"><span data-stu-id="e3b82-125">**Keys**</span></span>

|<span data-ttu-id="e3b82-126">**개 열**</span><span class="sxs-lookup"><span data-stu-id="e3b82-126">**Column(s)**</span></span>|<span data-ttu-id="e3b82-127">**설명**</span><span class="sxs-lookup"><span data-stu-id="e3b82-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3b82-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3b82-128">prinGuid</span></span>  <br/> |<span data-ttu-id="e3b82-129">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e3b82-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3b82-130">prinGuid</span></span>  <br/> |<span data-ttu-id="e3b82-131">PrinGuid 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b82-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

