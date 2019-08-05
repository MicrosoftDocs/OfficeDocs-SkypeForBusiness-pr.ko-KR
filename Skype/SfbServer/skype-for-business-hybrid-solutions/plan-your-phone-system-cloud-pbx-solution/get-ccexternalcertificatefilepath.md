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
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 배포에 대 한 외부 인증서 파일 경로를 반환 합니다. 사용자가이 인증서를 준비 합니다.
ms.openlocfilehash: ed725814380741aade73166d01025650dfa78538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190779"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="7e292-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="7e292-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="7e292-105">Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 배포에 대 한 외부 인증서 파일 경로를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-105">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="7e292-106">사용자가이 인증서를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-106">The user prepares this certificate.</span></span>
  
<span data-ttu-id="7e292-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="7e292-108">예제</span><span class="sxs-lookup"><span data-stu-id="7e292-108">Examples</span></span>
<span data-ttu-id="7e292-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7e292-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="7e292-110">예제 1</span><span class="sxs-lookup"><span data-stu-id="7e292-110">Example 1</span></span>

<span data-ttu-id="7e292-111">다음 예에서는 Edge 서버용 인증서의 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="7e292-112">예제 2</span><span class="sxs-lookup"><span data-stu-id="7e292-112">Example 2</span></span>

<span data-ttu-id="7e292-113">다음 예에서는 중재 서버에 대 한 인증서 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="7e292-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="7e292-114">Detailed Description</span></span>
<span data-ttu-id="7e292-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7e292-115"></span></span>

<span data-ttu-id="7e292-116">배포 중 또는 토폴로지를 수정할 때 Edge 서버 인증서의 경로를 지정 하 고 필요에 따라 중재 서버에 대 한 경로를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-116">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server.</span></span> <span data-ttu-id="7e292-117">게이트웨이 및 중재 서버 간에 TLS를 사용 하는 경우 중재 서버용 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-117">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="7e292-118">경로를 변경 하려면 Set-CcExternalCertificateFilePath cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-118">To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7e292-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e292-119">Parameters</span></span>
<span data-ttu-id="7e292-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7e292-120"></span></span>

|<span data-ttu-id="7e292-121">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="7e292-121">**Parameter**</span></span>|<span data-ttu-id="7e292-122">**필수**</span><span class="sxs-lookup"><span data-stu-id="7e292-122">**Required**</span></span>|<span data-ttu-id="7e292-123">**유형**</span><span class="sxs-lookup"><span data-stu-id="7e292-123">**Type**</span></span>|<span data-ttu-id="7e292-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="7e292-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e292-125">대상</span><span class="sxs-lookup"><span data-stu-id="7e292-125">Target</span></span>  <br/> |<span data-ttu-id="7e292-126">선택</span><span class="sxs-lookup"><span data-stu-id="7e292-126">Optional</span></span>  <br/> | <span data-ttu-id="7e292-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7e292-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="7e292-128">요청 된 파일 경로 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-128">Type of file path requested.</span></span> <span data-ttu-id="7e292-129">유형에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-129">Types include:</span></span>  <br/> <span data-ttu-id="7e292-130">EdgeServer (기본값)</span><span class="sxs-lookup"><span data-stu-id="7e292-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="7e292-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="7e292-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7e292-132">입력 형식</span><span class="sxs-lookup"><span data-stu-id="7e292-132">Input Types</span></span>
<span data-ttu-id="7e292-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7e292-133"></span></span>

<span data-ttu-id="7e292-134">Get-CcExternalCertificateFilePath cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7e292-135">반환 형식</span><span class="sxs-lookup"><span data-stu-id="7e292-135">Return Types</span></span>
<span data-ttu-id="7e292-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7e292-136"></span></span>

<span data-ttu-id="7e292-137">이 명령은 파일 경로를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e292-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7e292-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e292-138">See also</span></span>
<span data-ttu-id="7e292-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7e292-139"></span></span>

[<span data-ttu-id="7e292-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="7e292-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

