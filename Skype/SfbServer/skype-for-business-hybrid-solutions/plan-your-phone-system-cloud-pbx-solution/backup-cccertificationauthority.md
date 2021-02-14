---
title: Backup-CcCertificationAuthority
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
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: 이 Backup-CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리의 CA 폴더에 저장합니다.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803808"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="1d078-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="1d078-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="1d078-104">이 Backup-CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리의 CA 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1d078-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="1d078-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d078-105">Parameters</span></span>

<span data-ttu-id="1d078-106">없음</span><span class="sxs-lookup"><span data-stu-id="1d078-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1d078-107">예</span><span class="sxs-lookup"><span data-stu-id="1d078-107">Examples</span></span>
<span data-ttu-id="1d078-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1d078-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1d078-109">예 1</span><span class="sxs-lookup"><span data-stu-id="1d078-109">Example 1</span></span>

<span data-ttu-id="1d078-110">다음 예에서는 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리의 CA 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1d078-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="1d078-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="1d078-111">Detailed Description</span></span>
<span data-ttu-id="1d078-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1d078-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1d078-113">인증 기관 백업은 재해 발생 시 동일한 인증서를 사용하여 Cloud Connector 어플라이언스를 다시 재배포하려는 경우 또는 어플라이언스를 새 하드웨어로 이동하려는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d078-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="1d078-114">이 명령은 클라우드 커넥터 인증 기관 서비스의 복사본을 AD Server의 \< "SiteRootDirectory \> \CA\SfB CCE Root.p12"에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1d078-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="1d078-115">입력 형식</span><span class="sxs-lookup"><span data-stu-id="1d078-115">Input Types</span></span>
<span data-ttu-id="1d078-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1d078-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1d078-117">없음</span><span class="sxs-lookup"><span data-stu-id="1d078-117">None.</span></span> <span data-ttu-id="1d078-118">이 Backup-CcCertificationAuthority cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d078-118">The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1d078-119">반환 형식</span><span class="sxs-lookup"><span data-stu-id="1d078-119">Return Types</span></span>
<span data-ttu-id="1d078-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1d078-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1d078-121">없음</span><span class="sxs-lookup"><span data-stu-id="1d078-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1d078-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d078-122">See also</span></span>
<span data-ttu-id="1d078-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1d078-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1d078-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="1d078-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

