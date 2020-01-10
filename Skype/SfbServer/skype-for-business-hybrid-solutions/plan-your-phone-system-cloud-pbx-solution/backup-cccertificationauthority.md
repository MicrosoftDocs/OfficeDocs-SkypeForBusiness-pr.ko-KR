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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업 하 고 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003028"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="8ef82-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="8ef82-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="8ef82-104">CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업 하 고 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef82-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="8ef82-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ef82-105">Parameters</span></span>

<span data-ttu-id="8ef82-106">없음</span><span class="sxs-lookup"><span data-stu-id="8ef82-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8ef82-107">예제</span><span class="sxs-lookup"><span data-stu-id="8ef82-107">Examples</span></span>
<span data-ttu-id="8ef82-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8ef82-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="8ef82-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="8ef82-109">Example 1</span></span>

<span data-ttu-id="8ef82-110">다음 예에서는 인증 기관 서비스를 파일에 백업 하 고 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef82-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="8ef82-111">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="8ef82-111">Detailed Description</span></span>
<span data-ttu-id="8ef82-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8ef82-112"></span></span>

<span data-ttu-id="8ef82-113">재해가 발생 했을 때와 동일한 인증서를 사용 하 여 클라우드 커넥터 기기를 다시 배포 하려는 경우 또는 기기를 새 하드웨어로 이동 하려는 경우 인증 기관 백업이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ef82-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="8ef82-114">명령이 AD 서버에서 클라우드 커넥터 인증 기관 서비스의 복사본을 "\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12"로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef82-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8ef82-115">입력 형식</span><span class="sxs-lookup"><span data-stu-id="8ef82-115">Input Types</span></span>
<span data-ttu-id="8ef82-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ef82-116"></span></span>

<span data-ttu-id="8ef82-117">없음.</span><span class="sxs-lookup"><span data-stu-id="8ef82-117">None.</span></span> <span data-ttu-id="8ef82-118">CcCertificationAuthority cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ef82-118">The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8ef82-119">반환 형식</span><span class="sxs-lookup"><span data-stu-id="8ef82-119">Return Types</span></span>
<span data-ttu-id="8ef82-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ef82-120"></span></span>

<span data-ttu-id="8ef82-121">없음</span><span class="sxs-lookup"><span data-stu-id="8ef82-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ef82-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ef82-122">See also</span></span>
<span data-ttu-id="8ef82-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ef82-123"></span></span>

[<span data-ttu-id="8ef82-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="8ef82-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

