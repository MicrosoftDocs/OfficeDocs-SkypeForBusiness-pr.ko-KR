---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: 이 Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 배포에 대한 외부 인증서 파일 경로를 반환합니다. 사용자가 이 인증서를 준비합니다.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799908"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="c8f05-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="c8f05-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="c8f05-105">이 Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 배포에 대한 외부 인증서 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-105">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="c8f05-106">사용자가 이 인증서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-106">The user prepares this certificate.</span></span>
  
<span data-ttu-id="c8f05-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="c8f05-108">예</span><span class="sxs-lookup"><span data-stu-id="c8f05-108">Examples</span></span>
<span data-ttu-id="c8f05-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f05-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c8f05-110">예 1</span><span class="sxs-lookup"><span data-stu-id="c8f05-110">Example 1</span></span>

<span data-ttu-id="c8f05-111">다음 예에서는 에지 서버의 인증서 경로를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="c8f05-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="c8f05-112">예 2</span><span class="sxs-lookup"><span data-stu-id="c8f05-112">Example 2</span></span>

<span data-ttu-id="c8f05-113">다음 예에서는 중재 서버에 대한 인증서 집합을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="c8f05-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c8f05-114">Detailed Description</span></span>
<span data-ttu-id="c8f05-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f05-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c8f05-116">배포 중이나 토폴로지 수정 시에는 에지 서버 인증서의 경로와 중재 서버의 경로를 선택적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-116">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server.</span></span> <span data-ttu-id="c8f05-117">게이트웨이와 중재 서버 간에 TLS를 사용하려면 중재 서버에 대한 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-117">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="c8f05-118">경로를 변경하기 위해 Set-CcExternalCertificateFilePath cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-118">To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c8f05-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8f05-119">Parameters</span></span>
<span data-ttu-id="c8f05-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f05-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c8f05-121">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="c8f05-121">**Parameter**</span></span>|<span data-ttu-id="c8f05-122">**필수**</span><span class="sxs-lookup"><span data-stu-id="c8f05-122">**Required**</span></span>|<span data-ttu-id="c8f05-123">**유형**</span><span class="sxs-lookup"><span data-stu-id="c8f05-123">**Type**</span></span>|<span data-ttu-id="c8f05-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="c8f05-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c8f05-125">Target(대상)</span><span class="sxs-lookup"><span data-stu-id="c8f05-125">Target</span></span>  <br/> |<span data-ttu-id="c8f05-126">선택</span><span class="sxs-lookup"><span data-stu-id="c8f05-126">Optional</span></span>  <br/> | <span data-ttu-id="c8f05-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c8f05-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="c8f05-128">요청된 파일 경로의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-128">Type of file path requested.</span></span> <span data-ttu-id="c8f05-129">유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-129">Types include:</span></span>  <br/> <span data-ttu-id="c8f05-130">EdgeServer(기본값)</span><span class="sxs-lookup"><span data-stu-id="c8f05-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="c8f05-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="c8f05-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c8f05-132">입력 형식</span><span class="sxs-lookup"><span data-stu-id="c8f05-132">Input Types</span></span>
<span data-ttu-id="c8f05-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f05-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c8f05-134">이 Get-CcExternalCertificateFilePath cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c8f05-135">반환 형식</span><span class="sxs-lookup"><span data-stu-id="c8f05-135">Return Types</span></span>
<span data-ttu-id="c8f05-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f05-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c8f05-137">이 명령은 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f05-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8f05-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8f05-138">See also</span></span>
<span data-ttu-id="c8f05-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f05-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c8f05-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="c8f05-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

