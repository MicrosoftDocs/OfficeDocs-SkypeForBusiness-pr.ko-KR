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
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory cmdlet은 사이트 수준 구성 파일이 저장 되는 현재 디렉터리를 표시 합니다. 폴더에는 기본 VHD 및 비즈니스용 Skype 클라우드 커넥터 에디션 설치 파일이 포함 되어 있습니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 기기와 공유 되어야 합니다.
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003368"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="616e9-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="616e9-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="616e9-106">Get-CcSiteDirectory cmdlet은 사이트 수준 구성 파일이 저장 되는 현재 디렉터리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="616e9-107">폴더에는 기본 VHD 및 비즈니스용 Skype 클라우드 커넥터 에디션 설치 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="616e9-108">이 폴더는 클라우드 커넥터 사이트의 다른 모든 기기와 공유 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="616e9-109">이 cmdlet은 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="616e9-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="616e9-110">Parameters</span></span>

<span data-ttu-id="616e9-111">없음</span><span class="sxs-lookup"><span data-stu-id="616e9-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="616e9-112">예제</span><span class="sxs-lookup"><span data-stu-id="616e9-112">Examples</span></span>
<span data-ttu-id="616e9-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="616e9-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="616e9-114">예제 1</span><span class="sxs-lookup"><span data-stu-id="616e9-114">Example 1</span></span>

<span data-ttu-id="616e9-115">다음 예제에서는 클라우드 커넥터 구성 요소의 구성 및 가상 컴퓨터 파일이 저장 되는 현재 폴더를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="616e9-116">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="616e9-116">Detailed Description</span></span>
<span data-ttu-id="616e9-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="616e9-117"></span></span>

<span data-ttu-id="616e9-118">게이트웨이 선호도 및 고가용성을 제공 하기 위해 사이트에서 클라우드 커넥터 기기를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="616e9-119">클라우드 커넥터 기기 대신 사용자가 사이트에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="616e9-120">각 사이트에는 기본 VHD 및 클라우드 커넥터 설치 파일이 저장 되어 있는 공유 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="616e9-121">기기는 배포 중에이 폴더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="616e9-122">기본 폴더는 C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="616e9-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="616e9-123">Set-CcSiteDirectory cmdlet을 사용 하 여 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="616e9-124">입력 형식</span><span class="sxs-lookup"><span data-stu-id="616e9-124">Input Types</span></span>
<span data-ttu-id="616e9-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="616e9-125"></span></span>

<span data-ttu-id="616e9-126">없음.</span><span class="sxs-lookup"><span data-stu-id="616e9-126">None.</span></span> <span data-ttu-id="616e9-127">Get-CcSiteDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="616e9-128">반환 형식</span><span class="sxs-lookup"><span data-stu-id="616e9-128">Return Types</span></span>
<span data-ttu-id="616e9-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="616e9-129"></span></span>

<span data-ttu-id="616e9-130">이 명령은 파일 경로를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="616e9-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="616e9-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="616e9-131">See also</span></span>
<span data-ttu-id="616e9-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="616e9-132"></span></span>

[<span data-ttu-id="616e9-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="616e9-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

