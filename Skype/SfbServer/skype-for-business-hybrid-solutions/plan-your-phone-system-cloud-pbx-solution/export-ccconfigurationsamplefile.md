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
description: Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 샘플 구성 파일 (.ini)을 클라우드 커넥터 기기의 기기 디렉터리로 내보냅니다. 배포에 사용할 파일을 수정 하 고 이름을 바꿀 수 있습니다.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801008"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="64234-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="64234-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="64234-105">Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 샘플 구성 파일 (.ini)을 클라우드 커넥터 기기의 기기 디렉터리로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="64234-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="64234-106">배포에 사용할 파일을 수정 하 고 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64234-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="64234-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64234-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="64234-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64234-108">Parameters</span></span>

<span data-ttu-id="64234-109">없음</span><span class="sxs-lookup"><span data-stu-id="64234-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="64234-110">예제</span><span class="sxs-lookup"><span data-stu-id="64234-110">Examples</span></span>
<span data-ttu-id="64234-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="64234-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="64234-112">예제 1</span><span class="sxs-lookup"><span data-stu-id="64234-112">Example 1</span></span>

<span data-ttu-id="64234-113">다음 예제에서는 Microsoft 사이트에서 샘플 구성 파일을 다운로드 하 여 클라우드 커넥터 기기의 기기 디렉터리에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="64234-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="64234-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="64234-114">Detailed Description</span></span>
<span data-ttu-id="64234-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="64234-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="64234-116">현재 버전의 클라우드 커넥터는 .ini 파일에 여러 매개 변수를 제공 해야 합니다. 예를 들어 클라우드 커넥터 구성 요소, 구성 요소 이름, 게이트웨이 매개 변수 등에 대 한 가상 컴퓨터의 IP 주소와 같은 매개 변수</span><span class="sxs-lookup"><span data-stu-id="64234-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="64234-117">클라우드 커넥터의 호스트 컴퓨터에서 실행 되는 경우이 cmdlet을 사용 하 여 Microsoft 사이트의 구성 예제와 함께 샘플 .ini 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="64234-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="64234-118">Cmdlet은 클라우드 커넥터 기기의 기기 디렉터리에 파일을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="64234-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="64234-119">CcApplianceDirectory cmdlet을 사용 하 여 기기 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64234-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="64234-120">입력 형식</span><span class="sxs-lookup"><span data-stu-id="64234-120">Input Types</span></span>
<span data-ttu-id="64234-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64234-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="64234-122">없음.</span><span class="sxs-lookup"><span data-stu-id="64234-122">None.</span></span> <span data-ttu-id="64234-123">Export-CcConfigurationSampleFile cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64234-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="64234-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="64234-124">Return Types</span></span>
<span data-ttu-id="64234-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64234-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="64234-126">없음</span><span class="sxs-lookup"><span data-stu-id="64234-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64234-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64234-127">See also</span></span>
<span data-ttu-id="64234-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64234-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="64234-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="64234-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

