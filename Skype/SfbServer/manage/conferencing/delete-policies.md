---
title: 비즈니스용 Skype 서버에서 회의 정책 삭제
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 삭제하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119507"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="ed9a6-103">비즈니스용 Skype 서버에서 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="ed9a6-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ed9a6-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 삭제하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9a6-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="ed9a6-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9a6-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ed9a6-106">비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="ed9a6-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ed9a6-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9a6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ed9a6-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="ed9a6-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ed9a6-109">왼쪽 탐색 모음에서 회의 를 클릭한 다음 회의 정책을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed9a6-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="ed9a6-110">회의 정책 목록에서 삭제할 사이트 또는 사용자 정책을 클릭하고 편집, 삭제를 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="ed9a6-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ed9a6-111">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="ed9a6-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ed9a6-112">회의 정책을 삭제하려면 **Remove-CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9a6-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="ed9a6-113">다음 명령은 ID RedmondConferencingPolicy가 포함된 회의 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9a6-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="ed9a6-114">다음 명령은 외부 사용자가 회의를 기록할 수 있도록 허용하는 모든 회의 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9a6-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="ed9a6-115">전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Remove-CsConferencingPolicy 를 참조하십시오.](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ed9a6-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
