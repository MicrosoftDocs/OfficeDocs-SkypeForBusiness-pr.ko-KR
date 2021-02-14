---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 로컬 파일에서 클라우드 커넥터 호스트 서버로 비즈니스용 Skype 클라우드 커넥터 버전 구성을 가져올 수 있습니다.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799858"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="2b6c2-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b6c2-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="2b6c2-104">로컬 파일에서 클라우드 커넥터 호스트 서버로 비즈니스용 Skype 클라우드 커넥터 버전 구성을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="2b6c2-105">예</span><span class="sxs-lookup"><span data-stu-id="2b6c2-105">Examples</span></span>
<span data-ttu-id="2b6c2-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b6c2-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2b6c2-107">예 1</span><span class="sxs-lookup"><span data-stu-id="2b6c2-107">Example 1</span></span>

<span data-ttu-id="2b6c2-108">다음 예에서는 클라우드 CloudConnector.ini 어플라이언스 디렉터리의 응용 프로그램을 %SystemDrive%\ProgramData\CloudConnector 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="2b6c2-109">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="2b6c2-109">Detailed Description</span></span>
<span data-ttu-id="2b6c2-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b6c2-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="2b6c2-111">이 cmdlet은 클라우드 CloudConnector.ini 어플라이언스 디렉터리의 응용 프로그램을 %SystemDrive%\ProgramData\CloudConnector 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="2b6c2-112">어플라이언스 디렉터리는 Set-CcApplianceDirectory 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="2b6c2-113">이 cmdlet은 %SystemDrive%\ProgramData\CloudConnector의 기존 파일을 덮어 덮어 덮어 니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="2b6c2-114">이 명령은 Cloud Connector Edition 버전 2.0.1 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2b6c2-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b6c2-115">Parameters</span></span>
<span data-ttu-id="2b6c2-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b6c2-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="2b6c2-117">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="2b6c2-117">**Parameter**</span></span>|<span data-ttu-id="2b6c2-118">**필수**</span><span class="sxs-lookup"><span data-stu-id="2b6c2-118">**Required**</span></span>|<span data-ttu-id="2b6c2-119">**유형**</span><span class="sxs-lookup"><span data-stu-id="2b6c2-119">**Type**</span></span>|<span data-ttu-id="2b6c2-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="2b6c2-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b6c2-121">Force</span><span class="sxs-lookup"><span data-stu-id="2b6c2-121">Force</span></span>  <br/> |<span data-ttu-id="2b6c2-122">선택</span><span class="sxs-lookup"><span data-stu-id="2b6c2-122">Optional</span></span>  <br/> |<span data-ttu-id="2b6c2-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2b6c2-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="2b6c2-124">알림 없이 %SystemDrive%\ProgramData\CloudConnector의 기존 파일을 덮어 니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2b6c2-125">입력 형식</span><span class="sxs-lookup"><span data-stu-id="2b6c2-125">Input Types</span></span>
<span data-ttu-id="2b6c2-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b6c2-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="2b6c2-127">없음</span><span class="sxs-lookup"><span data-stu-id="2b6c2-127">None.</span></span> <span data-ttu-id="2b6c2-128">이 Import-CcConfiguration cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2b6c2-129">반환 형식</span><span class="sxs-lookup"><span data-stu-id="2b6c2-129">Return Types</span></span>
<span data-ttu-id="2b6c2-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b6c2-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="2b6c2-131">없음</span><span class="sxs-lookup"><span data-stu-id="2b6c2-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b6c2-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b6c2-132">See also</span></span>
<span data-ttu-id="2b6c2-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b6c2-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="2b6c2-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b6c2-134">Export-CcConfiguration</span></span>
  

