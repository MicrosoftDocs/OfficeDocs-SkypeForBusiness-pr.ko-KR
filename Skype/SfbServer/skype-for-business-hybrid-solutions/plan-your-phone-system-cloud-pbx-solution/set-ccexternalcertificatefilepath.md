---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 Edge 서버의 인증서가 저장 되는 경로를 지정 합니다.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824202"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="27d8d-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="27d8d-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="27d8d-104">Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 Edge 서버의 인증서가 저장 되는 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="27d8d-105">이 인증서는 배포 중에 또는 비즈니스용 Skype 클라우드 커넥터 에디션의 새 기기를 추가할 때 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="27d8d-106">이 명령을 사용 하면 배포 후 중재 서버에 대 한 새 인증서를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="27d8d-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="27d8d-108">예제</span><span class="sxs-lookup"><span data-stu-id="27d8d-108">Examples</span></span>
<span data-ttu-id="27d8d-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="27d8d-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="27d8d-110">예제 1</span><span class="sxs-lookup"><span data-stu-id="27d8d-110">Example 1</span></span>

<span data-ttu-id="27d8d-111">다음 예에서는 Edge 서버의 인증서 경로를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="27d8d-112">예제 2</span><span class="sxs-lookup"><span data-stu-id="27d8d-112">Example 2</span></span>

<span data-ttu-id="27d8d-113">다음 예에서는 중재 서버용 인증서 경로를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="27d8d-114">예제 3</span><span class="sxs-lookup"><span data-stu-id="27d8d-114">Example 3</span></span>

<span data-ttu-id="27d8d-115">다음 예제에서는 중재 서버에 대 한 인증서를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="27d8d-116">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="27d8d-116">Detailed Description</span></span>
<span data-ttu-id="27d8d-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="27d8d-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="27d8d-118">배포 중에 또는 토폴로지를 수정 하는 동안에는 Edge 서버 인증서에 대 한 경로를 지정 하 고 필요에 따라 중재 서버 인증서를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="27d8d-119">게이트웨이 및 중재 서버 간에 TLS를 사용 하는 경우 중재 서버용 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="27d8d-120">클라우드 커넥터 기기를 배포 하 고 TLS를 배포 하려는 경우 중재 서버에 배포 될 인증서의 경로만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="27d8d-121">그러나 이미 배포 된 기기에서 중재 인증서를 업데이트 하려는 경우 경로와-Import 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="27d8d-122">경로를 보려면 Get-CCExternalCertificateFilePath cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="27d8d-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27d8d-123">Parameters</span></span>
<span data-ttu-id="27d8d-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="27d8d-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="27d8d-125">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="27d8d-125">**Parameter**</span></span>|<span data-ttu-id="27d8d-126">**필수**</span><span class="sxs-lookup"><span data-stu-id="27d8d-126">**Required**</span></span>|<span data-ttu-id="27d8d-127">**유형**</span><span class="sxs-lookup"><span data-stu-id="27d8d-127">**Type**</span></span>|<span data-ttu-id="27d8d-128">**설명**</span><span class="sxs-lookup"><span data-stu-id="27d8d-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="27d8d-129">대상</span><span class="sxs-lookup"><span data-stu-id="27d8d-129">Target</span></span> <br/> | <span data-ttu-id="27d8d-130">필수</span><span class="sxs-lookup"><span data-stu-id="27d8d-130">Required</span></span> <br/> |<span data-ttu-id="27d8d-131">System.String</span><span class="sxs-lookup"><span data-stu-id="27d8d-131">System.String</span></span>  <br/> |<span data-ttu-id="27d8d-132">요청 된 파일 경로 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-132">Type of file path requested.</span></span> <span data-ttu-id="27d8d-133">유형에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-133">Types include:</span></span>  <br/> <span data-ttu-id="27d8d-134">EdgeServer (기본값)</span><span class="sxs-lookup"><span data-stu-id="27d8d-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="27d8d-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="27d8d-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="27d8d-136">Import</span><span class="sxs-lookup"><span data-stu-id="27d8d-136">Import</span></span>  <br/> |<span data-ttu-id="27d8d-137">선택</span><span class="sxs-lookup"><span data-stu-id="27d8d-137">Optional</span></span>  <br/> |<span data-ttu-id="27d8d-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="27d8d-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="27d8d-139">자격 증명을 중재 서버로 가져와야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="27d8d-140">처음으로 기기를 배포 하는 경우이 매개 변수는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="27d8d-141">이미 배포 된 버전에서 기존 인증서를 변경 하려는 경우에는 매개 변수가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="27d8d-142">입력 형식</span><span class="sxs-lookup"><span data-stu-id="27d8d-142">Input Types</span></span>
<span data-ttu-id="27d8d-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27d8d-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="27d8d-144">Set-CcExternalCertificateFilePath cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27d8d-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="27d8d-145">반환 형식</span><span class="sxs-lookup"><span data-stu-id="27d8d-145">Return Types</span></span>
<span data-ttu-id="27d8d-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27d8d-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="27d8d-147">없음</span><span class="sxs-lookup"><span data-stu-id="27d8d-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="27d8d-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27d8d-148">See also</span></span>
<span data-ttu-id="27d8d-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27d8d-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="27d8d-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="27d8d-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

