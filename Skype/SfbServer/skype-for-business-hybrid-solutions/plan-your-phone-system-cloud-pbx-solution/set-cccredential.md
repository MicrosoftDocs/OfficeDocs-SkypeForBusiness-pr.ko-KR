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
description: 이 Set-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 버전 배포의 자격 증명을 설정합니다.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221572"
---
# <a name="set-cccredential"></a><span data-ttu-id="cf2cd-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="cf2cd-103">Set-CcCredential</span></span>
 
<span data-ttu-id="cf2cd-104">이 Set-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 버전 배포의 자격 증명을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="cf2cd-105">클라우드 커넥터 버전 2.0 이상에서는 이 cmdlet이 가상 컴퓨터 관리자 및 도메인 관리자에 대한 계정 정보를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="cf2cd-106">예</span><span class="sxs-lookup"><span data-stu-id="cf2cd-106">Examples</span></span>
<span data-ttu-id="cf2cd-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2cd-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="cf2cd-108">예 1</span><span class="sxs-lookup"><span data-stu-id="cf2cd-108">Example 1</span></span>

<span data-ttu-id="cf2cd-109">다음 예에서는 테넌트 관리자의 계정 이름과 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="cf2cd-110">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="cf2cd-110">Detailed Description</span></span>
<span data-ttu-id="cf2cd-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2cd-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="cf2cd-112">이 Set-CcCredential cmdlet은 테넌트 관리자의 계정 이름과 암호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="cf2cd-113">2.0 이전 릴리스의 경우 이 관리자는 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="cf2cd-114">클라우드 커넥터는 이 계정을 사용하여 구성 정보를 얻거나, 구성 매개 변수를 설정하고, 어플라이언스 상태를 Microsoft 365 또는 Office 365 조직 구성으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="cf2cd-115">릴리스 2.0 이상에서는 이 cmdlet을 사용하여 VmAdmin 및 DomainAdmin 계정의 암호를 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="cf2cd-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf2cd-116">Parameters</span></span>
<span data-ttu-id="cf2cd-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2cd-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="cf2cd-118">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="cf2cd-118">**Parameter**</span></span>|<span data-ttu-id="cf2cd-119">**필수**</span><span class="sxs-lookup"><span data-stu-id="cf2cd-119">**Required**</span></span>|<span data-ttu-id="cf2cd-120">**유형**</span><span class="sxs-lookup"><span data-stu-id="cf2cd-120">**Type**</span></span>|<span data-ttu-id="cf2cd-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="cf2cd-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cf2cd-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="cf2cd-122">AccountType</span></span> <br/> | <span data-ttu-id="cf2cd-123">필수</span><span class="sxs-lookup"><span data-stu-id="cf2cd-123">Required</span></span> <br/> |<span data-ttu-id="cf2cd-124">System.String</span><span class="sxs-lookup"><span data-stu-id="cf2cd-124">System.String</span></span>  <br/> | <span data-ttu-id="cf2cd-125">매개 변수 값은 "TenantAdmin", "VmAdmin" 또는 "DomainAdmin"입니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="cf2cd-126">입력 형식</span><span class="sxs-lookup"><span data-stu-id="cf2cd-126">Input Types</span></span>
<span data-ttu-id="cf2cd-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2cd-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="cf2cd-128">없음</span><span class="sxs-lookup"><span data-stu-id="cf2cd-128">None.</span></span> <span data-ttu-id="cf2cd-129">이 Set-CcCredential cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf2cd-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cf2cd-130">반환 형식</span><span class="sxs-lookup"><span data-stu-id="cf2cd-130">Return Types</span></span>
<span data-ttu-id="cf2cd-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2cd-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="cf2cd-132">없음</span><span class="sxs-lookup"><span data-stu-id="cf2cd-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf2cd-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf2cd-133">See also</span></span>
<span data-ttu-id="cf2cd-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2cd-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="cf2cd-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="cf2cd-135">Get-CcCredential</span></span>](get-cccredential.md)
  

