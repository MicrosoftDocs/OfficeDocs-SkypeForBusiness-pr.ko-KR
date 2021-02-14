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
description: 이 Exit-CcUpdate 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801768"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="c9bb3-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="c9bb3-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="c9bb3-104">이 Exit-CcUpdate 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb3-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="c9bb3-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb3-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="c9bb3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c9bb3-106">Parameters</span></span>

<span data-ttu-id="c9bb3-107">없음</span><span class="sxs-lookup"><span data-stu-id="c9bb3-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c9bb3-108">예</span><span class="sxs-lookup"><span data-stu-id="c9bb3-108">Examples</span></span>
<span data-ttu-id="c9bb3-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bb3-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c9bb3-110">예 1</span><span class="sxs-lookup"><span data-stu-id="c9bb3-110">Example 1</span></span>

<span data-ttu-id="c9bb3-111">다음 명령은 다시 실행되는 어플라이언스를 프로덕션 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb3-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="c9bb3-112">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c9bb3-112">Detailed Description</span></span>
<span data-ttu-id="c9bb3-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bb3-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c9bb3-114">Enter-CcUpdate cmdlet을 지정하여 유지 관리 모드를 설정한 어플라이언스가 있는 경우 Exit-CcUpdate cmdlet은 이러한 어플라이언스를 프로덕션 모드로 다시 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb3-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="c9bb3-115">어플라이언스를 유지 관리 모드로 설정하는 자세한 내용은 Enter-CcUpdate를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9bb3-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c9bb3-116">입력 형식</span><span class="sxs-lookup"><span data-stu-id="c9bb3-116">Input Types</span></span>
<span data-ttu-id="c9bb3-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bb3-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c9bb3-118">없음</span><span class="sxs-lookup"><span data-stu-id="c9bb3-118">None.</span></span> <span data-ttu-id="c9bb3-119">이 Exit-CcUpdate cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bb3-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c9bb3-120">반환 형식</span><span class="sxs-lookup"><span data-stu-id="c9bb3-120">Return Types</span></span>
<span data-ttu-id="c9bb3-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bb3-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c9bb3-122">없음</span><span class="sxs-lookup"><span data-stu-id="c9bb3-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c9bb3-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9bb3-123">See also</span></span>
<span data-ttu-id="c9bb3-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c9bb3-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c9bb3-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="c9bb3-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

