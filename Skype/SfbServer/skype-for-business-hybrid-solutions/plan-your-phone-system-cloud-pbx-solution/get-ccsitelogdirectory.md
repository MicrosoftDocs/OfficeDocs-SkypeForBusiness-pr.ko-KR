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
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 로그가 저장 되는 현재 디렉터리를 표시 합니다.
ms.openlocfilehash: bc47c2ea2d81e70538305daa98f97a35cf3d9e0a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190770"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="c0b5f-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="c0b5f-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="c0b5f-104">Get-CcSiteLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 로그가 저장 되는 현재 디렉터리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="c0b5f-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="c0b5f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0b5f-106">Parameters</span></span>

<span data-ttu-id="c0b5f-107">없음</span><span class="sxs-lookup"><span data-stu-id="c0b5f-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c0b5f-108">예제</span><span class="sxs-lookup"><span data-stu-id="c0b5f-108">Examples</span></span>
<span data-ttu-id="c0b5f-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c0b5f-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="c0b5f-110">예제 1</span><span class="sxs-lookup"><span data-stu-id="c0b5f-110">Example 1</span></span>

<span data-ttu-id="c0b5f-111">다음 예제에서는 클라우드 커넥터 사이트의 로그 파일이 저장 되어 있는 현재 폴더를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="c0b5f-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c0b5f-112">Detailed Description</span></span>
<span data-ttu-id="c0b5f-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c0b5f-113"></span></span>

<span data-ttu-id="c0b5f-114">기본 폴더는 C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="c0b5f-115">Set-CcSiteDirectory cmdlet을 실행 하 여 폴더를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="c0b5f-116">사이트 디렉터리를 변경 하지 않고 로그 폴더 위치만 변경 하는 별도의 cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c0b5f-117">입력 형식</span><span class="sxs-lookup"><span data-stu-id="c0b5f-117">Input Types</span></span>
<span data-ttu-id="c0b5f-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c0b5f-118"></span></span>

<span data-ttu-id="c0b5f-119">없음.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-119">None.</span></span> <span data-ttu-id="c0b5f-120">Get-CcSiteLogDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c0b5f-121">반환 형식</span><span class="sxs-lookup"><span data-stu-id="c0b5f-121">Return Types</span></span>
<span data-ttu-id="c0b5f-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c0b5f-122"></span></span>

<span data-ttu-id="c0b5f-123">이 명령은 파일 경로를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b5f-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c0b5f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0b5f-124">See also</span></span>
<span data-ttu-id="c0b5f-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c0b5f-125"></span></span>

[<span data-ttu-id="c0b5f-126">집합-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="c0b5f-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

