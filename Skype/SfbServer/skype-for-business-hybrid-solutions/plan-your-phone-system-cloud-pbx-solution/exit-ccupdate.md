---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 업데이트 유지 관리 모드를 종료 합니다.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801768"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="9c684-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="9c684-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="9c684-104">CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 업데이트 유지 관리 모드를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c684-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="9c684-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c684-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="9c684-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c684-106">Parameters</span></span>

<span data-ttu-id="9c684-107">없음</span><span class="sxs-lookup"><span data-stu-id="9c684-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9c684-108">예제</span><span class="sxs-lookup"><span data-stu-id="9c684-108">Examples</span></span>
<span data-ttu-id="9c684-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c684-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9c684-110">예제 1</span><span class="sxs-lookup"><span data-stu-id="9c684-110">Example 1</span></span>

<span data-ttu-id="9c684-111">다음 명령은 프로덕션 모드로 다시 실행 되는 기기를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c684-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="9c684-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9c684-112">Detailed Description</span></span>
<span data-ttu-id="9c684-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9c684-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="9c684-114">-CcUpdate cmdlet을 지정 하 여 유지 관리 모드에 있는 기기를 사용 하는 경우에는이를 프로덕션 모드에 다시 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c684-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="9c684-115">유지 관리 모드에 기기를 배치 하는 방법에 대 한 자세한 내용은-CcUpdate 입력을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c684-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="9c684-116">입력 형식</span><span class="sxs-lookup"><span data-stu-id="9c684-116">Input Types</span></span>
<span data-ttu-id="9c684-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9c684-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="9c684-118">없음.</span><span class="sxs-lookup"><span data-stu-id="9c684-118">None.</span></span> <span data-ttu-id="9c684-119">CcUpdate cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c684-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9c684-120">반환 형식</span><span class="sxs-lookup"><span data-stu-id="9c684-120">Return Types</span></span>
<span data-ttu-id="9c684-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9c684-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="9c684-122">없음</span><span class="sxs-lookup"><span data-stu-id="9c684-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9c684-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c684-123">See also</span></span>
<span data-ttu-id="9c684-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9c684-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="9c684-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="9c684-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

