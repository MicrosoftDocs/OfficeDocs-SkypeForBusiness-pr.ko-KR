---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 반환 합니다.
ms.openlocfilehash: 46c51783361ad6613d1e2971600969b324f0f350
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003388"
---
# <a name="get-cccredential"></a><span data-ttu-id="147a7-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="147a7-103">Get-CcCredential</span></span>
 
<span data-ttu-id="147a7-104">Get-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="147a7-105">버전 2.0 이상에서는-DisplayPassword 매개 변수를 사용 하 여 TenantAdmin, DomainAdmin, VMAdmin에 대 한 암호를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="147a7-106">예제</span><span class="sxs-lookup"><span data-stu-id="147a7-106">Examples</span></span>
<span data-ttu-id="147a7-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="147a7-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="147a7-108">예제 1</span><span class="sxs-lookup"><span data-stu-id="147a7-108">Example 1</span></span>

<span data-ttu-id="147a7-109">다음 예에서는 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자 자격 증명을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="147a7-110">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="147a7-110">Detailed Description</span></span>
<span data-ttu-id="147a7-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="147a7-111"></span></span>

<span data-ttu-id="147a7-112">Get-CcCredential cmdlet은 지정 된 계정 유형에 대 한 자격 증명 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="147a7-113">이러한 자격 증명은 현재 기기를 배포할 때 등록-CcAppliance 및 설치-CcAppliance cmdlet을 실행 하는 관리자가 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="147a7-114">Get-CcCredential cmdlet은 System.webserver 개체의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="147a7-115">반환 개체의 password 속성은 System.webserver입니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="147a7-116">도메인 관리자 암호의 일반 텍스트를 가져오려면 해당 암호가 호스트 서버의 현재 로그온 계정에 의해 입력 되었는지 확인 하 고 PowerShell 콘솔을 관리자로 열고 아래 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="147a7-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="147a7-117">Parameters</span></span>
<span data-ttu-id="147a7-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="147a7-118"></span></span>

|<span data-ttu-id="147a7-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="147a7-119">**Parameter**</span></span>|<span data-ttu-id="147a7-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="147a7-120">**Required**</span></span>|<span data-ttu-id="147a7-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="147a7-121">**Type**</span></span>|<span data-ttu-id="147a7-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="147a7-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="147a7-123">유형</span><span class="sxs-lookup"><span data-stu-id="147a7-123">AccountType</span></span> <br/> |<span data-ttu-id="147a7-124">필수</span><span class="sxs-lookup"><span data-stu-id="147a7-124">Required</span></span>  <br/> | <span data-ttu-id="147a7-125">System.String</span><span class="sxs-lookup"><span data-stu-id="147a7-125">System.String</span></span> <br/> | <span data-ttu-id="147a7-126">AccountType 값은 다음 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="147a7-127">VmAdmin: 클라우드 커넥터 가상 컴퓨터의 로컬 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="147a7-128">DomainAdmin: 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="147a7-129">컴퓨터 관리: 클라우드 커넥터 가상 컴퓨터 도메인 컨트롤러의 컴퓨터 분리 Emodeadmin.</span><span class="sxs-lookup"><span data-stu-id="147a7-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="147a7-130">ExternalCert: Edge 서버에 설치 된 외부 인증서의 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="147a7-131">TenantAdmin: O365 테 넌 트의 관리자.</span><span class="sxs-lookup"><span data-stu-id="147a7-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="147a7-132">입력 형식</span><span class="sxs-lookup"><span data-stu-id="147a7-132">Input Types</span></span>
<span data-ttu-id="147a7-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="147a7-133"></span></span>

<span data-ttu-id="147a7-134">없음.</span><span class="sxs-lookup"><span data-stu-id="147a7-134">None.</span></span> <span data-ttu-id="147a7-135">Get-CcCredential cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="147a7-136">반환 형식</span><span class="sxs-lookup"><span data-stu-id="147a7-136">Return Types</span></span>
<span data-ttu-id="147a7-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="147a7-137"></span></span>

<span data-ttu-id="147a7-138">Get-CcCredential cmdlet은 System.webserver 개체의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="147a7-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="147a7-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="147a7-139">See also</span></span>
<span data-ttu-id="147a7-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="147a7-140"></span></span>

[<span data-ttu-id="147a7-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="147a7-141">Set-CcCredential</span></span>](set-cccredential.md)
  

