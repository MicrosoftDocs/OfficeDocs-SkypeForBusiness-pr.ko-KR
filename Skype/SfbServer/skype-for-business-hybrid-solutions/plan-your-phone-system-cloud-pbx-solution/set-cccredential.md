---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 설정-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 설정 합니다.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221572"
---
# <a name="set-cccredential"></a><span data-ttu-id="17ee5-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="17ee5-103">Set-CcCredential</span></span>
 
<span data-ttu-id="17ee5-104">설정-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="17ee5-105">클라우드 커넥터 버전 2.0 이상을 사용 하는 경우이 cmdlet은 가상 컴퓨터 관리자 및 도메인 관리자에 대 한 계정 정보도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="17ee5-106">예제</span><span class="sxs-lookup"><span data-stu-id="17ee5-106">Examples</span></span>
<span data-ttu-id="17ee5-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="17ee5-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="17ee5-108">예 1</span><span class="sxs-lookup"><span data-stu-id="17ee5-108">Example 1</span></span>

<span data-ttu-id="17ee5-109">다음 예에서는 테 넌 트 관리자의 계정 이름 및 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="17ee5-110">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="17ee5-110">Detailed Description</span></span>
<span data-ttu-id="17ee5-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="17ee5-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="17ee5-112">Set-CcCredential cmdlet은 테 넌 트 관리자의 계정 이름 및 암호를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="17ee5-113">2.0 이전 버전의 경우이 관리자는 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="17ee5-114">클라우드 커넥터는이 계정을 사용 하 여 구성 정보를 가져오고, 구성 매개 변수를 설정 하 고, Microsoft 365 또는 Office 365 조직 구성으로 기기 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="17ee5-115">릴리스 2.0 이상에서이 cmdlet을 사용 하 여 VmAdmin 및 DomainAdmin 계정의 암호를 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="17ee5-116">매개 변수 </span><span class="sxs-lookup"><span data-stu-id="17ee5-116">Parameters</span></span>
<span data-ttu-id="17ee5-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="17ee5-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="17ee5-118">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="17ee5-118">**Parameter**</span></span>|<span data-ttu-id="17ee5-119">**필수**</span><span class="sxs-lookup"><span data-stu-id="17ee5-119">**Required**</span></span>|<span data-ttu-id="17ee5-120">**유형**</span><span class="sxs-lookup"><span data-stu-id="17ee5-120">**Type**</span></span>|<span data-ttu-id="17ee5-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="17ee5-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="17ee5-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="17ee5-122">AccountType</span></span> <br/> | <span data-ttu-id="17ee5-123">필수</span><span class="sxs-lookup"><span data-stu-id="17ee5-123">Required</span></span> <br/> |<span data-ttu-id="17ee5-124">System.string</span><span class="sxs-lookup"><span data-stu-id="17ee5-124">System.String</span></span>  <br/> | <span data-ttu-id="17ee5-125">매개 변수 값은 "TenantAdmin", "VmAdmin" 또는 "DomainAdmin" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="17ee5-126">입력 형식</span><span class="sxs-lookup"><span data-stu-id="17ee5-126">Input Types</span></span>
<span data-ttu-id="17ee5-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17ee5-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="17ee5-128">없음</span><span class="sxs-lookup"><span data-stu-id="17ee5-128">None.</span></span> <span data-ttu-id="17ee5-129">설정-CcCredential cmdlet은 파이프라인 된 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17ee5-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="17ee5-130">반환 형식</span><span class="sxs-lookup"><span data-stu-id="17ee5-130">Return Types</span></span>
<span data-ttu-id="17ee5-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17ee5-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="17ee5-132">없음</span><span class="sxs-lookup"><span data-stu-id="17ee5-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17ee5-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17ee5-133">See also</span></span>
<span data-ttu-id="17ee5-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17ee5-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="17ee5-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="17ee5-135">Get-CcCredential</span></span>](get-cccredential.md)
  

