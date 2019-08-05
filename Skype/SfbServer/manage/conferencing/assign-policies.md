---
title: 비즈니스용 Skype 서버에서 회의 정책 지정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 할당 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: acd74262b51000a3f4af5668fb3c9271a8c0978d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191274"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="446d7-103">비즈니스용 Skype 서버에서 회의 정책 지정</span><span class="sxs-lookup"><span data-stu-id="446d7-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="446d7-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 할당 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="446d7-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="446d7-105">비즈니스용 Skype Server Management Shell 및 **CsConferencingPolicy** cmdlet을 사용 하 여 사용자에 게 회의 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="446d7-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="446d7-106">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 지정</span><span class="sxs-lookup"><span data-stu-id="446d7-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="446d7-107">다음 예제에서는 ": 진구 Myer" Id를 사용 하 여 정책 SalesConferencingPolicy 사용자에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="446d7-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="446d7-108">다음 예제에서는 회의 정책 FinanceConferencingPolicy 재무 조직 단위에 계정이 있는 모든 사용자에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="446d7-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="446d7-109">지정 된 OU (조직 구성 단위)의 모든 사용자에 게 동일한 정책을 할당 하려면 Get-CsUser cmdlet을 사용 하 여 해당 OU의 모든 계정을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="446d7-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="446d7-110">사용자 계정이 검색 된 후에는 해당 정보를 CsConferencingPolicy cmdlet에 파이프 하 여 컬렉션의 각 사용자에 게 FinanceConferencingPolicy 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="446d7-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="446d7-111">전체 구문 및 매개 변수 목록을 비롯 한 자세한 내용은 [CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="446d7-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

