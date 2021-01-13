---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie에는 현재 LDAP(Lightweight Directory Access Protocol) 동기화 쿠키가 포함됩니다.
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814758"
---
# <a name="tbladcookie"></a><span data-ttu-id="75304-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="75304-103">tblADCookie</span></span>
 
<span data-ttu-id="75304-104">tblADCookie에는 현재 LDAP(Lightweight Directory Access Protocol) 동기화 쿠키가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="75304-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="75304-105">**열**</span><span class="sxs-lookup"><span data-stu-id="75304-105">**Columns**</span></span>

|<span data-ttu-id="75304-106">**열**</span><span class="sxs-lookup"><span data-stu-id="75304-106">**Column**</span></span>|<span data-ttu-id="75304-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="75304-107">**Type**</span></span>|<span data-ttu-id="75304-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="75304-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75304-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="75304-109">prinGuid</span></span>  <br/> |<span data-ttu-id="75304-110">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="75304-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="75304-111">모니터링 중인 도메인의 사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="75304-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="75304-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="75304-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="75304-113">nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="75304-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="75304-114">Active Directory 도메인 서비스 동기화에 사용되는 현재 도메인 컨트롤러의 FQDN(FQDN)입니다. 정보 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75304-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="75304-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="75304-115">adcContent</span></span>  <br/> |<span data-ttu-id="75304-116">image(바이너리)</span><span class="sxs-lookup"><span data-stu-id="75304-116">image (binary)</span></span>  <br/> |<span data-ttu-id="75304-117">Active Directory 동기화 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="75304-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="75304-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="75304-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="75304-119">datetime</span><span class="sxs-lookup"><span data-stu-id="75304-119">datetime</span></span>  <br/> |<span data-ttu-id="75304-120">행 업데이트 시간이 포함된 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="75304-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="75304-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="75304-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="75304-122">datetime</span><span class="sxs-lookup"><span data-stu-id="75304-122">datetime</span></span>  <br/> |<span data-ttu-id="75304-p101">변경할 수 없도록 행이 잠길 때까지의 시간입니다. 이 방식은 한 번에 하나의 채팅 서비스만 Active Directory 동기화를 수행할 수 있도록 보장하는 소프트웨어 내부 잠금 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="75304-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="75304-125">**키**</span><span class="sxs-lookup"><span data-stu-id="75304-125">**Keys**</span></span>

|<span data-ttu-id="75304-126">**Column(s)**</span><span class="sxs-lookup"><span data-stu-id="75304-126">**Column(s)**</span></span>|<span data-ttu-id="75304-127">**설명**</span><span class="sxs-lookup"><span data-stu-id="75304-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75304-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="75304-128">prinGuid</span></span>  <br/> |<span data-ttu-id="75304-129">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="75304-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="75304-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="75304-130">prinGuid</span></span>  <br/> |<span data-ttu-id="75304-131">Principal.prinGuid 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="75304-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

