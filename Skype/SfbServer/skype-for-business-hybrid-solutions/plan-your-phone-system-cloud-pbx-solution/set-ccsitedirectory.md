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
description: Set-CcSiteDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 구성 파일이 저장 되는 디렉터리를 설정 합니다. 폴더에 기본 VHD 및 클라우드 커넥터 구성 파일이 포함 됩니다.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824192"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="a56b4-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="a56b4-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="a56b4-105">Set-CcSiteDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 구성 파일이 저장 되는 디렉터리를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="a56b4-106">폴더에 기본 VHD 및 클라우드 커넥터 구성 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="a56b4-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="a56b4-108">예제</span><span class="sxs-lookup"><span data-stu-id="a56b4-108">Examples</span></span>
<span data-ttu-id="a56b4-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a56b4-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a56b4-110">예제 1</span><span class="sxs-lookup"><span data-stu-id="a56b4-110">Example 1</span></span>

<span data-ttu-id="a56b4-111">다음 예에서는 사이트 루트 디렉토리를 SiteShare\CloudConnector로 \\설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="a56b4-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a56b4-112">Detailed Description</span></span>
<span data-ttu-id="a56b4-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a56b4-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a56b4-114">게이트웨이 선호도 및 고가용성을 제공 하기 위해 사이트에서 클라우드 커넥터 기기를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="a56b4-115">클라우드 커넥터 기기 대신 사용자가 사이트에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="a56b4-116">각 사이트에는 기본 VHD 및 클라우드 커넥터 설치 파일이 저장 되어 있는 공유 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="a56b4-117">기기는 배포 중에이 폴더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="a56b4-118">이 폴더는 클라우드 커넥터 사이트의 다른 모든 기기와 공유 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="a56b4-119">기본 폴더는 C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="a56b4-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="a56b4-120">Path는 Get-CcSiteDirectory cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a56b4-121">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a56b4-121">Parameters</span></span>
<span data-ttu-id="a56b4-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a56b4-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a56b4-123">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="a56b4-123">**Parameter**</span></span>|<span data-ttu-id="a56b4-124">**필수**</span><span class="sxs-lookup"><span data-stu-id="a56b4-124">**Required**</span></span>|<span data-ttu-id="a56b4-125">**유형**</span><span class="sxs-lookup"><span data-stu-id="a56b4-125">**Type**</span></span>|<span data-ttu-id="a56b4-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="a56b4-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a56b4-127">패스가</span><span class="sxs-lookup"><span data-stu-id="a56b4-127">Path</span></span> <br/> | <span data-ttu-id="a56b4-128">필수</span><span class="sxs-lookup"><span data-stu-id="a56b4-128">Required</span></span> <br/> | <span data-ttu-id="a56b4-129">System.String</span><span class="sxs-lookup"><span data-stu-id="a56b4-129">System.String</span></span> <br/> |<span data-ttu-id="a56b4-130">클라우드 커넥터 사이트 파일이 저장 되는 폴더의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a56b4-131">입력 형식</span><span class="sxs-lookup"><span data-stu-id="a56b4-131">Input Types</span></span>
<span data-ttu-id="a56b4-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a56b4-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a56b4-133">없음.</span><span class="sxs-lookup"><span data-stu-id="a56b4-133">None.</span></span> <span data-ttu-id="a56b4-134">Set-CcSiteDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a56b4-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a56b4-135">반환 형식</span><span class="sxs-lookup"><span data-stu-id="a56b4-135">Return Types</span></span>
<span data-ttu-id="a56b4-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a56b4-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a56b4-137">없음</span><span class="sxs-lookup"><span data-stu-id="a56b4-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a56b4-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a56b4-138">See also</span></span>
<span data-ttu-id="a56b4-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a56b4-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="a56b4-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="a56b4-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

