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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814706"
---
# <a name="tbladcookie"></a><span data-ttu-id="3b639-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="3b639-103">tblADCookie</span></span>
 
<span data-ttu-id="3b639-104">tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="3b639-105">**열**</span><span class="sxs-lookup"><span data-stu-id="3b639-105">**Columns**</span></span>

|<span data-ttu-id="3b639-106">**열**</span><span class="sxs-lookup"><span data-stu-id="3b639-106">**Column**</span></span>|<span data-ttu-id="3b639-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="3b639-107">**Type**</span></span>|<span data-ttu-id="3b639-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="3b639-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b639-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3b639-109">prinGuid</span></span>  <br/> |<span data-ttu-id="3b639-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="3b639-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3b639-111">모니터링 중인 도메인의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="3b639-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="3b639-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="3b639-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="3b639-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="3b639-114">Active Directory 도메인 서비스 동기화에 사용 되는 현재 도메인 컨트롤러의 FQDN (정규화 된 도메인 이름)입니다. 정보 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="3b639-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="3b639-115">adcContent</span></span>  <br/> |<span data-ttu-id="3b639-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="3b639-116">image (binary)</span></span>  <br/> |<span data-ttu-id="3b639-117">Active Directory 동기화 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="3b639-118">lastUpdated 됨</span><span class="sxs-lookup"><span data-stu-id="3b639-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="3b639-119">dmtf</span><span class="sxs-lookup"><span data-stu-id="3b639-119">datetime</span></span>  <br/> |<span data-ttu-id="3b639-120">행 업데이트 시간이 포함 된 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="3b639-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="3b639-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="3b639-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="3b639-122">datetime</span></span>  <br/> |<span data-ttu-id="3b639-123">행이 변경 내용에 맞게 잠길 때 까지의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="3b639-124">이는 채팅 서비스 중 하나만 Active Directory Sync를 한 번에 수행 하도록 하는 소프트웨어 연동 메커니즘의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="3b639-125">**핵심**</span><span class="sxs-lookup"><span data-stu-id="3b639-125">**Keys**</span></span>

|<span data-ttu-id="3b639-126">**개 열**</span><span class="sxs-lookup"><span data-stu-id="3b639-126">**Column(s)**</span></span>|<span data-ttu-id="3b639-127">**설명**</span><span class="sxs-lookup"><span data-stu-id="3b639-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b639-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3b639-128">prinGuid</span></span>  <br/> |<span data-ttu-id="3b639-129">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3b639-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3b639-130">prinGuid</span></span>  <br/> |<span data-ttu-id="3b639-131">PrinGuid 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="3b639-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

