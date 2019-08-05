---
title: 비즈니스용 Skype 서버에서 회의 정책 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 삭제 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: 2d02fa580acbc11c1b41643ab25cecba618ed09a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196471"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="848da-103">비즈니스용 Skype 서버에서 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="848da-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="848da-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 삭제 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="848da-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="848da-105">Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype 서버 관리 셸을 사용 하 여 회의 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="848da-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="848da-106">비즈니스용 Skype 서버 제어판을 사용 하 여 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="848da-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="848da-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="848da-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="848da-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="848da-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="848da-109">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="848da-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="848da-110">회의 정책 목록에서 삭제 하려는 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="848da-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="848da-111">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="848da-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="848da-112">회의 정책을 삭제 하려면 **Remove-CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="848da-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="848da-113">다음 명령은 Id RedmondConferencingPolicy를 사용 하 여 회의 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="848da-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="848da-114">다음 명령은 외부 사용자가 회의를 녹화할 수 있도록 하는 회의 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="848da-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="848da-115">전체 구문 및 매개 변수 목록을 비롯 한 자세한 내용은 [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="848da-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

