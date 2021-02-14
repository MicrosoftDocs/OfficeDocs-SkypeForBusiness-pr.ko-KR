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
description: 이 Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 에지 서버의 인증서가 저장되는 경로를 지정합니다.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824202"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="234c0-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="234c0-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="234c0-104">이 Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 에지 서버의 인증서가 저장되는 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="234c0-105">이 인증서는 배포 중에 또는 비즈니스용 Skype 클라우드 커넥터 Edition의 새 어플라이언스를 추가할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="234c0-106">또한 이 명령을 사용하면 배포 후에 중재 서버에 대한 새 인증서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="234c0-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="234c0-108">예</span><span class="sxs-lookup"><span data-stu-id="234c0-108">Examples</span></span>
<span data-ttu-id="234c0-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="234c0-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="234c0-110">예 1</span><span class="sxs-lookup"><span data-stu-id="234c0-110">Example 1</span></span>

<span data-ttu-id="234c0-111">다음 예에서는 에지 서버의 인증서 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="234c0-112">예 2</span><span class="sxs-lookup"><span data-stu-id="234c0-112">Example 2</span></span>

<span data-ttu-id="234c0-113">다음 예에서는 중재 서버의 인증서 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="234c0-114">예 3</span><span class="sxs-lookup"><span data-stu-id="234c0-114">Example 3</span></span>

<span data-ttu-id="234c0-115">다음 예에서는 중재 서버의 인증서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="234c0-116">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="234c0-116">Detailed Description</span></span>
<span data-ttu-id="234c0-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="234c0-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="234c0-118">배포 중이나 토폴로지 수정 중에 에지 서버 인증서의 경로를 지정하고 중재 서버 인증서에 대한 경로를 선택적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="234c0-119">게이트웨이와 중재 서버 간에 TLS를 사용하려면 중재 서버에 대한 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="234c0-120">클라우드 커넥터 어플라이언스를 배포하고 TLS를 배포하려는 경우 중재 서버에 배포할 인증서의 경로만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="234c0-121">그러나 이미 배포된 어플라이언스에서 중재 인증서를 업데이트하려면 경로와 -Import 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="234c0-122">경로를 표시하기 위해 Get-CCExternalCertificateFilePath cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="234c0-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="234c0-123">Parameters</span></span>
<span data-ttu-id="234c0-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="234c0-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="234c0-125">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="234c0-125">**Parameter**</span></span>|<span data-ttu-id="234c0-126">**필수**</span><span class="sxs-lookup"><span data-stu-id="234c0-126">**Required**</span></span>|<span data-ttu-id="234c0-127">**유형**</span><span class="sxs-lookup"><span data-stu-id="234c0-127">**Type**</span></span>|<span data-ttu-id="234c0-128">**설명**</span><span class="sxs-lookup"><span data-stu-id="234c0-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="234c0-129">Target(대상)</span><span class="sxs-lookup"><span data-stu-id="234c0-129">Target</span></span> <br/> | <span data-ttu-id="234c0-130">필수</span><span class="sxs-lookup"><span data-stu-id="234c0-130">Required</span></span> <br/> |<span data-ttu-id="234c0-131">System.String</span><span class="sxs-lookup"><span data-stu-id="234c0-131">System.String</span></span>  <br/> |<span data-ttu-id="234c0-132">요청된 파일 경로의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-132">Type of file path requested.</span></span> <span data-ttu-id="234c0-133">유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-133">Types include:</span></span>  <br/> <span data-ttu-id="234c0-134">EdgeServer(기본값)</span><span class="sxs-lookup"><span data-stu-id="234c0-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="234c0-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="234c0-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="234c0-136">가져오기</span><span class="sxs-lookup"><span data-stu-id="234c0-136">Import</span></span>  <br/> |<span data-ttu-id="234c0-137">선택</span><span class="sxs-lookup"><span data-stu-id="234c0-137">Optional</span></span>  <br/> |<span data-ttu-id="234c0-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="234c0-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="234c0-139">중재 서버로 인증서를 가져와야 것 을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="234c0-140">어플라이언스를 처음 배포하는 경우 이 매개 변수가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="234c0-141">이미 배포된 버전에서 기존 인증서를 변경하려면 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="234c0-142">입력 형식</span><span class="sxs-lookup"><span data-stu-id="234c0-142">Input Types</span></span>
<span data-ttu-id="234c0-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="234c0-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="234c0-144">이 Set-CcExternalCertificateFilePath cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="234c0-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="234c0-145">반환 형식</span><span class="sxs-lookup"><span data-stu-id="234c0-145">Return Types</span></span>
<span data-ttu-id="234c0-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="234c0-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="234c0-147">없음</span><span class="sxs-lookup"><span data-stu-id="234c0-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="234c0-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="234c0-148">See also</span></span>
<span data-ttu-id="234c0-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="234c0-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="234c0-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="234c0-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

