---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 이 Get-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 작업 디렉터리를 검색합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800848"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="dcb90-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="dcb90-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="dcb90-105">이 Get-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 작업 디렉터리를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="dcb90-106">모든 배포 파일은 이 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="dcb90-107">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="dcb90-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dcb90-108">Parameters</span></span>

<span data-ttu-id="dcb90-109">없음</span><span class="sxs-lookup"><span data-stu-id="dcb90-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="dcb90-110">예</span><span class="sxs-lookup"><span data-stu-id="dcb90-110">Examples</span></span>
<span data-ttu-id="dcb90-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="dcb90-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="dcb90-112">예 1</span><span class="sxs-lookup"><span data-stu-id="dcb90-112">Example 1</span></span>

<span data-ttu-id="dcb90-113">다음 예에서는 클라우드 커넥터 구성 요소의 구성 및 가상 컴퓨터 파일이 저장되는 현재 폴더를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="dcb90-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="dcb90-114">Detailed Description</span></span>
<span data-ttu-id="dcb90-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dcb90-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="dcb90-116">이 Get-CcApplianceDirectory cmdlet은 클라우드 커넥터 어플라이언스에 대해 모든 구성 및 가상 컴퓨터 파일, 로그 및 외부 인증서가 저장되는 위치를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="dcb90-117">각 클라우드 커넥터 어플라이언스에는 중재 서버, 중앙 관리 저장소, 에지 서버 및 도메인 컨트롤러의 네 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="dcb90-118">기본 폴더는 C:\Users \% userprofile%\CloudConnector\ApplianceRoot입니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="dcb90-119">이 폴더는 다음 cmdlet을 사용하여 변경할 Set-CCApplianceDirectory 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="dcb90-120">입력 형식</span><span class="sxs-lookup"><span data-stu-id="dcb90-120">Input Types</span></span>
<span data-ttu-id="dcb90-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dcb90-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="dcb90-122">없음</span><span class="sxs-lookup"><span data-stu-id="dcb90-122">None.</span></span> <span data-ttu-id="dcb90-123">이 Get-CCApplianceDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="dcb90-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="dcb90-124">Return Types</span></span>
<span data-ttu-id="dcb90-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dcb90-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="dcb90-126">이 명령은 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb90-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dcb90-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcb90-127">See also</span></span>
<span data-ttu-id="dcb90-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dcb90-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="dcb90-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="dcb90-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

