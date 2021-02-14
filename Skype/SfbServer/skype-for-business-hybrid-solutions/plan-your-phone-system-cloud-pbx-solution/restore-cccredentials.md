---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-Credentials cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 버전 배포의 모든 자격 증명을 복원합니다.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824244"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="4e55c-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="4e55c-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="4e55c-104">Restore Cc-Credentials cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 버전 배포의 모든 자격 증명을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="4e55c-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="4e55c-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 2.1에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e55c-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="4e55c-106">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4e55c-106">Detailed Description</span></span>

<span data-ttu-id="4e55c-107">이 Restore-CcCredentials cmdlet은 모든 자격 증명을 정리하고 현재 비즈니스용 Skype 클라우드 커넥터 배포에 사용되는 모든 자격 증명을 다시 입력하라는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e55c-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4e55c-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e55c-108">Parameters</span></span>

<span data-ttu-id="4e55c-109">없음</span><span class="sxs-lookup"><span data-stu-id="4e55c-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4e55c-110">입력 형식</span><span class="sxs-lookup"><span data-stu-id="4e55c-110">Input Types</span></span>

<span data-ttu-id="4e55c-111">없음</span><span class="sxs-lookup"><span data-stu-id="4e55c-111">None.</span></span> <span data-ttu-id="4e55c-112">이 Restore-CcCredentials cmdlet은 파이프라인된 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e55c-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4e55c-113">반환 형식</span><span class="sxs-lookup"><span data-stu-id="4e55c-113">Return Types</span></span>

<span data-ttu-id="4e55c-114">없음</span><span class="sxs-lookup"><span data-stu-id="4e55c-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="4e55c-115">예시</span><span class="sxs-lookup"><span data-stu-id="4e55c-115">Example</span></span>

<span data-ttu-id="4e55c-116">다음 예에서는 현재 클라우드 커넥터 배포의 모든 자격 증명을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="4e55c-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="4e55c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e55c-117">See also</span></span>

[<span data-ttu-id="4e55c-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="4e55c-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="4e55c-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="4e55c-119">Set-CcCredential</span></span>](set-cccredential.md)
  

