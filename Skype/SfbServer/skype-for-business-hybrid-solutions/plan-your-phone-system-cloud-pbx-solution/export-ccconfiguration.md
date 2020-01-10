---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 비즈니스용 skype 클라우드 커넥터 에디션 구성을 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 로컬 파일로 내보냅니다.
ms.openlocfilehash: cb3ea5a48c4e8911dc94526f85a517082d057b6e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003438"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="54a05-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="54a05-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="54a05-104">비즈니스용 skype 클라우드 커넥터 에디션 구성을 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 로컬 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="54a05-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="54a05-105">예제</span><span class="sxs-lookup"><span data-stu-id="54a05-105">Examples</span></span>
<span data-ttu-id="54a05-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="54a05-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="54a05-107">예제 1</span><span class="sxs-lookup"><span data-stu-id="54a05-107">Example 1</span></span>

<span data-ttu-id="54a05-108">다음 예제에서는 경로 매개 변수를 전체 파일 경로로 설정 하 고 구성을 해당 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="54a05-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="54a05-109">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="54a05-109">Detailed Description</span></span>
<span data-ttu-id="54a05-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="54a05-110"></span></span>

<span data-ttu-id="54a05-111">수출-CcConfiguration cmdlet을 사용 하 여 클라우드 커넥터 구성을 선택한 경로에 있는 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54a05-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="54a05-112">이 명령은 클라우드 커넥터 버전 2.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54a05-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="54a05-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54a05-113">Parameters</span></span>
<span data-ttu-id="54a05-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="54a05-114"></span></span>

|<span data-ttu-id="54a05-115">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="54a05-115">**Parameter**</span></span>|<span data-ttu-id="54a05-116">**필수**</span><span class="sxs-lookup"><span data-stu-id="54a05-116">**Required**</span></span>|<span data-ttu-id="54a05-117">**유형**</span><span class="sxs-lookup"><span data-stu-id="54a05-117">**Type**</span></span>|<span data-ttu-id="54a05-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="54a05-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="54a05-119">패스가</span><span class="sxs-lookup"><span data-stu-id="54a05-119">Path</span></span>  <br/> |<span data-ttu-id="54a05-120">필수</span><span class="sxs-lookup"><span data-stu-id="54a05-120">Required</span></span>  <br/> |<span data-ttu-id="54a05-121">System.String</span><span class="sxs-lookup"><span data-stu-id="54a05-121">System.String</span></span>  <br/> |<span data-ttu-id="54a05-122">클라우드 커넥터 구성이 저장 되는 전체 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="54a05-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="54a05-123">입력 형식</span><span class="sxs-lookup"><span data-stu-id="54a05-123">Input Types</span></span>
<span data-ttu-id="54a05-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="54a05-124"></span></span>

<span data-ttu-id="54a05-125">없음.</span><span class="sxs-lookup"><span data-stu-id="54a05-125">None.</span></span> <span data-ttu-id="54a05-126">수출-CcConfiguration cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54a05-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="54a05-127">반환 형식</span><span class="sxs-lookup"><span data-stu-id="54a05-127">Return Types</span></span>
<span data-ttu-id="54a05-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="54a05-128"></span></span>

<span data-ttu-id="54a05-129">없음.</span><span class="sxs-lookup"><span data-stu-id="54a05-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="54a05-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54a05-130">See also</span></span>
<span data-ttu-id="54a05-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="54a05-131"></span></span>

<span data-ttu-id="54a05-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="54a05-132">Import-CcConfiguration</span></span>
  

