---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: 이 Get-CcSiteDirectory cmdlet은 사이트 수준 구성 파일이 저장되는 현재 디렉터리를 보여줍니다. 폴더에는 기본 VHD 및 비즈니스용 Skype 클라우드 커넥터 버전 설치 파일이 포함되어 있습니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 어플라이언스와 공유해야 합니다.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799868"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="f22c0-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="f22c0-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="f22c0-106">이 Get-CcSiteDirectory cmdlet은 사이트 수준 구성 파일이 저장되는 현재 디렉터리를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="f22c0-107">폴더에는 기본 VHD 및 비즈니스용 Skype 클라우드 커넥터 버전 설치 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="f22c0-108">이 폴더는 클라우드 커넥터 사이트의 다른 모든 어플라이언스와 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="f22c0-109">이 cmdlet은 Cloud Connector Edition 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="f22c0-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f22c0-110">Parameters</span></span>

<span data-ttu-id="f22c0-111">없음</span><span class="sxs-lookup"><span data-stu-id="f22c0-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f22c0-112">예</span><span class="sxs-lookup"><span data-stu-id="f22c0-112">Examples</span></span>
<span data-ttu-id="f22c0-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f22c0-114">예 1</span><span class="sxs-lookup"><span data-stu-id="f22c0-114">Example 1</span></span>

<span data-ttu-id="f22c0-115">다음 예에서는 클라우드 커넥터 구성 요소의 구성 및 가상 컴퓨터 파일이 저장되는 현재 폴더를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="f22c0-116">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f22c0-116">Detailed Description</span></span>
<span data-ttu-id="f22c0-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f22c0-118">게이트웨이 관련성 및 고가용성을 제공하기 위해 Cloud Connector 어플라이언스를 사이트에 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="f22c0-119">사용자는 클라우드 커넥터 어플라이언스 대신 사이트에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="f22c0-120">각 사이트에는 기본 VHD 및 클라우드 커넥터 설치 파일이 저장되는 공유 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="f22c0-121">어플라이언스에서는 배포 중에 이 폴더를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="f22c0-122">기본 폴더는 C:\Users \% userprofile%\CloudConnector\SiteRoot입니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="f22c0-123">이 cmdlet을 사용하여 경로를 변경할 Set-CcSiteDirectory 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f22c0-124">입력 형식</span><span class="sxs-lookup"><span data-stu-id="f22c0-124">Input Types</span></span>
<span data-ttu-id="f22c0-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f22c0-126">없음</span><span class="sxs-lookup"><span data-stu-id="f22c0-126">None.</span></span> <span data-ttu-id="f22c0-127">이 Get-CcSiteDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f22c0-128">반환 형식</span><span class="sxs-lookup"><span data-stu-id="f22c0-128">Return Types</span></span>
<span data-ttu-id="f22c0-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f22c0-130">이 명령은 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f22c0-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f22c0-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f22c0-131">See also</span></span>
<span data-ttu-id="f22c0-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="f22c0-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="f22c0-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

