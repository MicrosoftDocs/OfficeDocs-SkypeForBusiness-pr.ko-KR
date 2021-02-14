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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: 이 Remove-CcCertificationAuthorityFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전용 사이트 공유 디렉터리 아래에 있는 CA 폴더의 인증 기관 서비스 백업 파일을 제거합니다.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824294"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="6e378-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="6e378-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="6e378-104">Remove-CcCertificationAuthorityFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전용 사이트 공유 디렉터리 아래에 있는 CA 폴더의 인증 기관 서비스 백업 파일 &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12"를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6e378-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="6e378-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e378-105">Parameters</span></span>

<span data-ttu-id="6e378-106">없음</span><span class="sxs-lookup"><span data-stu-id="6e378-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6e378-107">예</span><span class="sxs-lookup"><span data-stu-id="6e378-107">Examples</span></span>
<span data-ttu-id="6e378-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e378-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6e378-109">예 1</span><span class="sxs-lookup"><span data-stu-id="6e378-109">Example 1</span></span>

<span data-ttu-id="6e378-110">다음 예에서는 사이트 공유 디렉터리의 CA 폴더에서 인증 기관 서비스 백업 파일 &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12"를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6e378-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="6e378-111">입력 형식</span><span class="sxs-lookup"><span data-stu-id="6e378-111">Input Types</span></span>
<span data-ttu-id="6e378-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e378-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="6e378-113">없음</span><span class="sxs-lookup"><span data-stu-id="6e378-113">None.</span></span> <span data-ttu-id="6e378-114">이 Remove-CcCertificationAuthorityFile cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e378-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6e378-115">반환 형식</span><span class="sxs-lookup"><span data-stu-id="6e378-115">Return Types</span></span>
<span data-ttu-id="6e378-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e378-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="6e378-117">없음</span><span class="sxs-lookup"><span data-stu-id="6e378-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e378-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e378-118">See also</span></span>
<span data-ttu-id="6e378-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6e378-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="6e378-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="6e378-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

