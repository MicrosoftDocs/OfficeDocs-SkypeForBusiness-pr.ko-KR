---
title: 비즈니스용 Skype 서버에서 기존 보관 정책 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 정책을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188235"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="793a6-103">비즈니스용 Skype 서버에서 기존 보관 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="793a6-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="793a6-104">**요약:** 비즈니스용 Skype 서버에 대 한 보관 정책을 삭제 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="793a6-105">사용자 정책 또는 사이트 정책을 삭제할 수 있지만, 전역 정책이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="793a6-106">전역 정책을 삭제 하면 비즈니스용 Skype 서버가 자동으로 정책을 기본값으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="793a6-107">제어판을 사용 하 여 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="793a6-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="793a6-108">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="793a6-109">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="793a6-110">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="793a6-111">보관 정책 목록에서 삭제 하려는 사용자 또는 사이트 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="793a6-112">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="793a6-113">Windows PowerShell을 사용 하 여 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="793a6-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="793a6-114">**CsArchivingPolicy** cmdlet을 사용 하 여 보관 정책을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="793a6-115">예를 들어 다음 명령은 Id 사이트: Redmond를 사용 하 여 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="793a6-116">사이트 수준에서 구성 된 정책을 삭제 하는 경우 이전에 사이트 정책에서 관리 하는 사용자는 전역 보관 정책에 의해 자동으로 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="793a6-117">이 명령은 사용자 당 수준에 적용 된 모든 보관 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="793a6-118">이 명령은 내부 보관을 사용 하지 않도록 설정한 모든 보관 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="793a6-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="793a6-119">자세한 내용은 [제거 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="793a6-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
