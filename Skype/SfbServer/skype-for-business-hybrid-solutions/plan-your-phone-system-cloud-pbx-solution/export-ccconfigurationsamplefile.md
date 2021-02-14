---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: 이 Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 샘플 구성 파일(.ini)을 Cloud Connector 어플라이언스 디렉터리로 내보낼 수 있습니다. 배포에 사용할 파일을 수정하고 이름을 변경할 수 있습니다.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801008"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="122f3-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="122f3-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="122f3-105">이 Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 샘플 구성 파일(.ini)을 Cloud Connector 어플라이언스 디렉터리로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="122f3-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="122f3-106">배포에 사용할 파일을 수정하고 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="122f3-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="122f3-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="122f3-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="122f3-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="122f3-108">Parameters</span></span>

<span data-ttu-id="122f3-109">없음</span><span class="sxs-lookup"><span data-stu-id="122f3-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="122f3-110">예</span><span class="sxs-lookup"><span data-stu-id="122f3-110">Examples</span></span>
<span data-ttu-id="122f3-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="122f3-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="122f3-112">예 1</span><span class="sxs-lookup"><span data-stu-id="122f3-112">Example 1</span></span>

<span data-ttu-id="122f3-113">다음 예제에서는 Microsoft 사이트에서 샘플 구성 파일을 다운로드하여 Cloud Connector appliance의 어플라이언스 디렉터리에 쓴다.</span><span class="sxs-lookup"><span data-stu-id="122f3-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="122f3-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="122f3-114">Detailed Description</span></span>
<span data-ttu-id="122f3-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="122f3-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="122f3-116">현재 버전의 클라우드 커넥터를 사용하려면 .ini 파일에 여러 매개 변수를 제공해야 합니다. 예를 들어 클라우드 커넥터 구성 요소에 대한 가상 컴퓨터의 IP 주소, 구성 요소 이름, 게이트웨이 매개 변수 등의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="122f3-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="122f3-117">이 cmdlet은 클라우드 커넥터의 호스트 머신에서 실행되는 경우 Microsoft 사이트에서 구성 예제가 포함된 샘플 .ini 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="122f3-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="122f3-118">이 cmdlet은 클라우드 커넥터 어플라이언스 디렉터리에 파일을 쓴다.</span><span class="sxs-lookup"><span data-stu-id="122f3-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="122f3-119">어플라이언스 디렉터리는 Set-CcApplianceDirectory 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="122f3-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="122f3-120">입력 형식</span><span class="sxs-lookup"><span data-stu-id="122f3-120">Input Types</span></span>
<span data-ttu-id="122f3-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="122f3-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="122f3-122">없음</span><span class="sxs-lookup"><span data-stu-id="122f3-122">None.</span></span> <span data-ttu-id="122f3-123">이 Export-CcConfigurationSampleFile cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="122f3-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="122f3-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="122f3-124">Return Types</span></span>
<span data-ttu-id="122f3-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="122f3-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="122f3-126">없음</span><span class="sxs-lookup"><span data-stu-id="122f3-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="122f3-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="122f3-127">See also</span></span>
<span data-ttu-id="122f3-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="122f3-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="122f3-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="122f3-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

