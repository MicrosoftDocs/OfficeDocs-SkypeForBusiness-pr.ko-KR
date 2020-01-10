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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Cc-Credentials 복원 cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 모든 자격 증명을 복원 합니다.
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003248"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="91229-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="91229-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="91229-104">Cc-Credentials 복원 cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 모든 자격 증명을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="91229-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="91229-105">이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 2.1에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91229-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="91229-106">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="91229-106">Detailed Description</span></span>

<span data-ttu-id="91229-107">Restore-CcCredentials cmdlet은 모든 자격 증명을 정리 하 고 현재 비즈니스용 Skype 클라우드 커넥터 배포에 사용 되는 모든 자격 증명을 다시 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="91229-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="91229-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91229-108">Parameters</span></span>

<span data-ttu-id="91229-109">없음</span><span class="sxs-lookup"><span data-stu-id="91229-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="91229-110">입력 형식</span><span class="sxs-lookup"><span data-stu-id="91229-110">Input Types</span></span>

<span data-ttu-id="91229-111">없음.</span><span class="sxs-lookup"><span data-stu-id="91229-111">None.</span></span> <span data-ttu-id="91229-112">Restore-CcCredentials cmdlet은 파이프라인 입력을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91229-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="91229-113">반환 형식</span><span class="sxs-lookup"><span data-stu-id="91229-113">Return Types</span></span>

<span data-ttu-id="91229-114">없음.</span><span class="sxs-lookup"><span data-stu-id="91229-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="91229-115">예</span><span class="sxs-lookup"><span data-stu-id="91229-115">Example</span></span>

<span data-ttu-id="91229-116">다음 예제에서는 현재 클라우드 커넥터 배포의 모든 자격 증명을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="91229-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="91229-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91229-117">See also</span></span>

[<span data-ttu-id="91229-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="91229-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="91229-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="91229-119">Set-CcCredential</span></span>](set-cccredential.md)
  

