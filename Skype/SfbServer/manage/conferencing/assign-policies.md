---
title: 비즈니스용 Skype 서버에서 회의 정책 할당
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 할당하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099164"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="1898e-103">비즈니스용 Skype 서버에서 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1898e-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="1898e-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 할당하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1898e-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="1898e-105">비즈니스용 Skype 서버 관리 셸 및 **Grant-CsConferencingPolicy** cmdlet을 사용하여 사용자에게 회의 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1898e-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1898e-106">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1898e-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1898e-107">다음 예제에서는 ID가 "Ken Myer"인 사용자에게 SalesConferencingPolicy 정책이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1898e-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="1898e-108">다음 예제에서는 Finance 조직 구성 단위에 계정이 있는 모든 사용자에게 회의 정책 FinanceConferencingPolicy가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1898e-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="1898e-109">지정된 OU(조직 구성 단위)의 모든 사용자에게 동일한 정책을 할당하기 위해 Get-CsUser cmdlet을 사용하여 해당 OU의 모든 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1898e-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="1898e-110">사용자 계정을 검색한 후 해당 정보는 컬렉션의 각 사용자에게 FinanceConferencingPolicy 정책을 할당하는 Grant-CsConferencingPolicy cmdlet에 파이프됩니다.</span><span class="sxs-lookup"><span data-stu-id="1898e-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="1898e-111">전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Grant-CsConferencingPolicy를 참조하십시오.](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1898e-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
