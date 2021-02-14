---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: 이 Set-CcSiteDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전에 대한 사이트 수준 구성 파일이 저장될 디렉터리를 설정합니다. 폴더에는 기본 VHD 및 클라우드 커넥터 구성 파일이 포함되어 있습니다.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824192"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="430ff-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="430ff-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="430ff-105">이 Set-CcSiteDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전에 대한 사이트 수준 구성 파일이 저장될 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="430ff-106">폴더에는 기본 VHD 및 클라우드 커넥터 구성 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="430ff-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="430ff-108">예</span><span class="sxs-lookup"><span data-stu-id="430ff-108">Examples</span></span>
<span data-ttu-id="430ff-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="430ff-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="430ff-110">예 1</span><span class="sxs-lookup"><span data-stu-id="430ff-110">Example 1</span></span>

<span data-ttu-id="430ff-111">다음 예에서는 사이트 루트 디렉터리를 \\ SiteShare\CloudConnector로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="430ff-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="430ff-112">Detailed Description</span></span>
<span data-ttu-id="430ff-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="430ff-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="430ff-114">게이트웨이 관련성 및 고가용성을 제공하기 위해 Cloud Connector 어플라이언스를 사이트에 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="430ff-115">사용자는 클라우드 커넥터 어플라이언스 대신 사이트에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="430ff-116">각 사이트에는 기본 VHD 및 클라우드 커넥터 설치 파일이 저장되는 공유 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="430ff-117">어플라이언스에서는 배포 중에 이 폴더를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="430ff-118">이 폴더는 클라우드 커넥터 사이트의 다른 모든 어플라이언스와 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="430ff-119">기본 폴더는 C:\Users \% userprofile%\CloudConnector\SiteRoot입니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="430ff-120">경로는 이 cmdlet을 사용하여 볼 Get-CcSiteDirectory 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="430ff-121">매개 변수</span><span class="sxs-lookup"><span data-stu-id="430ff-121">Parameters</span></span>
<span data-ttu-id="430ff-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="430ff-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="430ff-123">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="430ff-123">**Parameter**</span></span>|<span data-ttu-id="430ff-124">**필수**</span><span class="sxs-lookup"><span data-stu-id="430ff-124">**Required**</span></span>|<span data-ttu-id="430ff-125">**유형**</span><span class="sxs-lookup"><span data-stu-id="430ff-125">**Type**</span></span>|<span data-ttu-id="430ff-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="430ff-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="430ff-127">경로</span><span class="sxs-lookup"><span data-stu-id="430ff-127">Path</span></span> <br/> | <span data-ttu-id="430ff-128">필수</span><span class="sxs-lookup"><span data-stu-id="430ff-128">Required</span></span> <br/> | <span data-ttu-id="430ff-129">System.String</span><span class="sxs-lookup"><span data-stu-id="430ff-129">System.String</span></span> <br/> |<span data-ttu-id="430ff-130">클라우드 커넥터 사이트 파일을 저장할 폴더의 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="430ff-131">입력 형식</span><span class="sxs-lookup"><span data-stu-id="430ff-131">Input Types</span></span>
<span data-ttu-id="430ff-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="430ff-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="430ff-133">없음</span><span class="sxs-lookup"><span data-stu-id="430ff-133">None.</span></span> <span data-ttu-id="430ff-134">이 Set-CcSiteDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="430ff-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="430ff-135">반환 형식</span><span class="sxs-lookup"><span data-stu-id="430ff-135">Return Types</span></span>
<span data-ttu-id="430ff-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="430ff-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="430ff-137">없음</span><span class="sxs-lookup"><span data-stu-id="430ff-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="430ff-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="430ff-138">See also</span></span>
<span data-ttu-id="430ff-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="430ff-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="430ff-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="430ff-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

