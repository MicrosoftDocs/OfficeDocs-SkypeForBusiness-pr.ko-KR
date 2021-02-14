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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 이 Get-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 버전 배포의 자격 증명을 반환합니다.
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800398"
---
# <a name="get-cccredential"></a><span data-ttu-id="811be-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="811be-103">Get-CcCredential</span></span>
 
<span data-ttu-id="811be-104">이 Get-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 버전 배포의 자격 증명을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="811be-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="811be-105">버전 2.0 이상에서는 -DisplayPassword 매개 변수를 사용하여 TenantAdmin, DomainAdmin 및 VMAdmin의 암호를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811be-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="811be-106">예</span><span class="sxs-lookup"><span data-stu-id="811be-106">Examples</span></span>
<span data-ttu-id="811be-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="811be-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="811be-108">예 1</span><span class="sxs-lookup"><span data-stu-id="811be-108">Example 1</span></span>

<span data-ttu-id="811be-109">다음 예에서는 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자 자격 증명을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="811be-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="811be-110">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="811be-110">Detailed Description</span></span>
<span data-ttu-id="811be-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="811be-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="811be-112">이 Get-CcCredential cmdlet은 지정된 계정 유형에 대한 자격 증명 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="811be-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="811be-113">이러한 자격 증명은 현재 어플라이언스를 배포할 때 Register-CcAppliance 및 Install-CcAppliance cmdlet을 실행한 관리자가 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="811be-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="811be-114">이 Get-CcCredential cmdlet은 System.Management.Automation.PSCredential 개체의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="811be-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="811be-115">반환 개체의 암호 속성은 System.Security.SecureString입니다.</span><span class="sxs-lookup"><span data-stu-id="811be-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="811be-116">도메인 관리자 암호의 명확한 텍스트를 얻으면 호스트 서버의 현재 로그온 계정에서 암호를 입력한 다음 관리자 권한으로 PowerShell 콘솔을 열고 아래 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="811be-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="811be-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="811be-117">Parameters</span></span>
<span data-ttu-id="811be-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="811be-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="811be-119">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="811be-119">**Parameter**</span></span>|<span data-ttu-id="811be-120">**필수**</span><span class="sxs-lookup"><span data-stu-id="811be-120">**Required**</span></span>|<span data-ttu-id="811be-121">**유형**</span><span class="sxs-lookup"><span data-stu-id="811be-121">**Type**</span></span>|<span data-ttu-id="811be-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="811be-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="811be-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="811be-123">AccountType</span></span> <br/> |<span data-ttu-id="811be-124">필수</span><span class="sxs-lookup"><span data-stu-id="811be-124">Required</span></span>  <br/> | <span data-ttu-id="811be-125">System.String</span><span class="sxs-lookup"><span data-stu-id="811be-125">System.String</span></span> <br/> | <span data-ttu-id="811be-126">AccountType 값은 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811be-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="811be-127">VmAdmin: 클라우드 커넥터 가상 컴퓨터의 로컬 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="811be-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="811be-128">DomainAdmin: 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="811be-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="811be-129">SafeModeAdmin: 클라우드 커넥터 가상 컴퓨터 도메인 컨트롤러의 SafeModeAdmin</span><span class="sxs-lookup"><span data-stu-id="811be-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="811be-130">ExternalCert: 에지 서버에 설치된 외부 인증서의 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="811be-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="811be-131">TenantAdmin: O365 테넌트의 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="811be-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="811be-132">입력 형식</span><span class="sxs-lookup"><span data-stu-id="811be-132">Input Types</span></span>
<span data-ttu-id="811be-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="811be-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="811be-134">없음</span><span class="sxs-lookup"><span data-stu-id="811be-134">None.</span></span> <span data-ttu-id="811be-135">이 Get-CcCredential cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="811be-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="811be-136">반환 형식</span><span class="sxs-lookup"><span data-stu-id="811be-136">Return Types</span></span>
<span data-ttu-id="811be-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="811be-137"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="811be-138">이 Get-CcCredential cmdlet은 System.Management.Automation.PSCredential 개체의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="811be-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="811be-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="811be-139">See also</span></span>
<span data-ttu-id="811be-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="811be-140"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="811be-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="811be-141">Set-CcCredential</span></span>](set-cccredential.md)
  

