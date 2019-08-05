---
title: 가져오기-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 로컬 파일에서 클라우드 커넥터 호스트 서버로의 비즈니스용 Skype 클라우드 커넥터 에디션 구성을 가져옵니다.
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190743"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="022bc-103">가져오기-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="022bc-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="022bc-104">로컬 파일에서 클라우드 커넥터 호스트 서버로의 비즈니스용 Skype 클라우드 커넥터 에디션 구성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="022bc-105">예제</span><span class="sxs-lookup"><span data-stu-id="022bc-105">Examples</span></span>
<span data-ttu-id="022bc-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="022bc-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="022bc-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="022bc-107">Example 1</span></span>

<span data-ttu-id="022bc-108">다음 예제에서는 클라우드 커넥터 인스턴스의 기기 디렉터리에서%SystemDrive%\ProgramData\CloudConnector 디렉터리로 CloudConnector .ini를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="022bc-109">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="022bc-109">Detailed Description</span></span>
<span data-ttu-id="022bc-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="022bc-110"></span></span>

<span data-ttu-id="022bc-111">이 cmdlet은 클라우드 커넥터 기기의 기기 디렉터리에서%SystemDrive%\ProgramData\CloudConnector 디렉터리로 CloudConnector .ini을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="022bc-112">CcApplianceDirectory cmdlet을 사용 하 여 기기 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="022bc-113">Cmdlet이%SystemDrive%\ProgramData\CloudConnector.의 모든 기존 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="022bc-114">이 명령은 Cloud Connector Edition 버전 2.0.1 이상에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="022bc-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="022bc-115">Parameters</span></span>
<span data-ttu-id="022bc-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="022bc-116"></span></span>

|<span data-ttu-id="022bc-117">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="022bc-117">**Parameter**</span></span>|<span data-ttu-id="022bc-118">**필수**</span><span class="sxs-lookup"><span data-stu-id="022bc-118">**Required**</span></span>|<span data-ttu-id="022bc-119">**유형**</span><span class="sxs-lookup"><span data-stu-id="022bc-119">**Type**</span></span>|<span data-ttu-id="022bc-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="022bc-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="022bc-121">Force</span><span class="sxs-lookup"><span data-stu-id="022bc-121">Force</span></span>  <br/> |<span data-ttu-id="022bc-122">선택</span><span class="sxs-lookup"><span data-stu-id="022bc-122">Optional</span></span>  <br/> |<span data-ttu-id="022bc-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="022bc-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="022bc-124">통지 없이%SystemDrive%\ProgramData\CloudConnector의 기존 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="022bc-125">입력 형식</span><span class="sxs-lookup"><span data-stu-id="022bc-125">Input Types</span></span>
<span data-ttu-id="022bc-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="022bc-126"></span></span>

<span data-ttu-id="022bc-127">없음.</span><span class="sxs-lookup"><span data-stu-id="022bc-127">None.</span></span> <span data-ttu-id="022bc-128">가져오기-CcConfiguration cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="022bc-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="022bc-129">반환 형식</span><span class="sxs-lookup"><span data-stu-id="022bc-129">Return Types</span></span>
<span data-ttu-id="022bc-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="022bc-130"></span></span>

<span data-ttu-id="022bc-131">없음.</span><span class="sxs-lookup"><span data-stu-id="022bc-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="022bc-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="022bc-132">See also</span></span>
<span data-ttu-id="022bc-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="022bc-133"></span></span>

<span data-ttu-id="022bc-134">수출-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="022bc-134">Export-CcConfiguration</span></span>
  

