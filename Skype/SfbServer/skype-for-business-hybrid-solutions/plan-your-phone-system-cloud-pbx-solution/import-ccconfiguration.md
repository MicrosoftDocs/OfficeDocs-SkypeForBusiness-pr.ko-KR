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
description: 로컬 파일에서 클라우드 커넥터 호스트 서버로의 비즈니스용 Skype 클라우드 커넥터 에디션 구성을 가져옵니다.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799858"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="24304-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="24304-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="24304-104">로컬 파일에서 클라우드 커넥터 호스트 서버로의 비즈니스용 Skype 클라우드 커넥터 에디션 구성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24304-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="24304-105">예제</span><span class="sxs-lookup"><span data-stu-id="24304-105">Examples</span></span>
<span data-ttu-id="24304-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="24304-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="24304-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="24304-107">Example 1</span></span>

<span data-ttu-id="24304-108">다음 예제에서는 클라우드 커넥터 인스턴스의 기기 디렉터리 에서%SystemDrive%\ProgramData\CloudConnector 디렉터리로 CloudConnector .ini를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="24304-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="24304-109">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="24304-109">Detailed Description</span></span>
<span data-ttu-id="24304-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="24304-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="24304-111">이 cmdlet은 클라우드 커넥터 기기의 기기 디렉터리 에서%SystemDrive%\ProgramData\CloudConnector 디렉터리로 CloudConnector .ini을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="24304-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="24304-112">CcApplianceDirectory cmdlet을 사용 하 여 기기 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24304-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="24304-113">Cmdlet 이%SystemDrive%\ProgramData\CloudConnector.의 모든 기존 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="24304-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="24304-114">이 명령은 Cloud Connector Edition 버전 2.0.1 이상에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24304-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="24304-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24304-115">Parameters</span></span>
<span data-ttu-id="24304-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="24304-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="24304-117">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="24304-117">**Parameter**</span></span>|<span data-ttu-id="24304-118">**필수**</span><span class="sxs-lookup"><span data-stu-id="24304-118">**Required**</span></span>|<span data-ttu-id="24304-119">**유형**</span><span class="sxs-lookup"><span data-stu-id="24304-119">**Type**</span></span>|<span data-ttu-id="24304-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="24304-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24304-121">Force</span><span class="sxs-lookup"><span data-stu-id="24304-121">Force</span></span>  <br/> |<span data-ttu-id="24304-122">선택</span><span class="sxs-lookup"><span data-stu-id="24304-122">Optional</span></span>  <br/> |<span data-ttu-id="24304-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="24304-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="24304-124">통지 없이%SystemDrive%\ProgramData\CloudConnector의 기존 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="24304-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="24304-125">입력 형식</span><span class="sxs-lookup"><span data-stu-id="24304-125">Input Types</span></span>
<span data-ttu-id="24304-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="24304-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="24304-127">없음.</span><span class="sxs-lookup"><span data-stu-id="24304-127">None.</span></span> <span data-ttu-id="24304-128">가져오기-CcConfiguration cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24304-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="24304-129">반환 형식</span><span class="sxs-lookup"><span data-stu-id="24304-129">Return Types</span></span>
<span data-ttu-id="24304-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="24304-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="24304-131">없음.</span><span class="sxs-lookup"><span data-stu-id="24304-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24304-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24304-132">See also</span></span>
<span data-ttu-id="24304-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="24304-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="24304-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="24304-134">Export-CcConfiguration</span></span>
  

