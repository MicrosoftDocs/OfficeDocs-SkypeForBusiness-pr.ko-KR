---
title: Get-CcSiteLogDirectory
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
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 이 Get-CcSiteLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전에 대한 사이트 수준 로그가 저장되는 현재 디렉터리를 보여줍니다.
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799888"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="cc1a8-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="cc1a8-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="cc1a8-104">이 Get-CcSiteLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전에 대한 사이트 수준 로그가 저장되는 현재 디렉터리를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="cc1a8-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="cc1a8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc1a8-106">Parameters</span></span>

<span data-ttu-id="cc1a8-107">없음</span><span class="sxs-lookup"><span data-stu-id="cc1a8-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="cc1a8-108">예</span><span class="sxs-lookup"><span data-stu-id="cc1a8-108">Examples</span></span>
<span data-ttu-id="cc1a8-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1a8-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="cc1a8-110">예 1</span><span class="sxs-lookup"><span data-stu-id="cc1a8-110">Example 1</span></span>

<span data-ttu-id="cc1a8-111">다음 예에서는 클라우드 커넥터 사이트의 로그 파일이 저장되는 현재 폴더를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="cc1a8-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="cc1a8-112">Detailed Description</span></span>
<span data-ttu-id="cc1a8-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1a8-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="cc1a8-114">기본 폴더는 C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="cc1a8-115">이 cmdlet을 실행하여 폴더를 변경할 Set-CcSiteDirectory 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="cc1a8-116">사이트 디렉터리를 변경하지 않고 로그 폴더 위치만 변경하는 별도의 cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="cc1a8-117">입력 형식</span><span class="sxs-lookup"><span data-stu-id="cc1a8-117">Input Types</span></span>
<span data-ttu-id="cc1a8-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1a8-118"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="cc1a8-119">없음</span><span class="sxs-lookup"><span data-stu-id="cc1a8-119">None.</span></span> <span data-ttu-id="cc1a8-120">이 Get-CcSiteLogDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cc1a8-121">반환 형식</span><span class="sxs-lookup"><span data-stu-id="cc1a8-121">Return Types</span></span>
<span data-ttu-id="cc1a8-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1a8-122"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="cc1a8-123">이 명령은 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc1a8-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc1a8-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc1a8-124">See also</span></span>
<span data-ttu-id="cc1a8-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1a8-125"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="cc1a8-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="cc1a8-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

