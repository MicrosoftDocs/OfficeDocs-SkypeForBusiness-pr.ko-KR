---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 공유 디렉터리 아래에 있는 CA 폴더의 인증 기관 서비스 백업 파일을 제거 합니다.
ms.openlocfilehash: d7036633eaf092130fc6e4acaebda39d04ff17df
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003298"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="878c5-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="878c5-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="878c5-104">CcCertificationAuthorityFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 사이트 공유 디렉터리&lt;아래의&gt;CA 폴더에서 "SiteRootDirectory \CA\SfB CCE Root. p12" 인증 기관 서비스 백업 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="878c5-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="878c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="878c5-105">Parameters</span></span>

<span data-ttu-id="878c5-106">없음</span><span class="sxs-lookup"><span data-stu-id="878c5-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="878c5-107">예제</span><span class="sxs-lookup"><span data-stu-id="878c5-107">Examples</span></span>
<span data-ttu-id="878c5-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="878c5-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="878c5-109">예제 1</span><span class="sxs-lookup"><span data-stu-id="878c5-109">Example 1</span></span>

<span data-ttu-id="878c5-110">다음 예에서는 사이트 공유 디렉터리 아래의 CA 폴더에서 인증&lt;기관&gt;서비스 백업 파일 "SiteRootDirectory \CA\SfB CCE Root: p12"를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="878c5-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="878c5-111">입력 형식</span><span class="sxs-lookup"><span data-stu-id="878c5-111">Input Types</span></span>
<span data-ttu-id="878c5-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="878c5-112"></span></span>

<span data-ttu-id="878c5-113">없음.</span><span class="sxs-lookup"><span data-stu-id="878c5-113">None.</span></span> <span data-ttu-id="878c5-114">CcCertificationAuthorityFile cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="878c5-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="878c5-115">반환 형식</span><span class="sxs-lookup"><span data-stu-id="878c5-115">Return Types</span></span>
<span data-ttu-id="878c5-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="878c5-116"></span></span>

<span data-ttu-id="878c5-117">없음</span><span class="sxs-lookup"><span data-stu-id="878c5-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="878c5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="878c5-118">See also</span></span>
<span data-ttu-id="878c5-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="878c5-119"></span></span>

[<span data-ttu-id="878c5-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="878c5-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

