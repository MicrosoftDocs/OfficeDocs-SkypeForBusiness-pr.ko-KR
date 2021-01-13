---
title: 비즈니스용 Skype 서버에서 기존 보관 정책 삭제
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '요약: 비즈니스용 Skype 서버에 대한 보관 정책을 삭제하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817618"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="cad9e-103">비즈니스용 Skype 서버에서 기존 보관 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="cad9e-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="cad9e-104">**요약:** 비즈니스용 Skype 서버의 보관 정책을 삭제하는 방법을 자세히 알아보는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="cad9e-105">사용자 정책 또는 사이트 정책은 삭제할 수 있지만 글로벌 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="cad9e-106">글로벌 정책을 삭제하면 비즈니스용 Skype 서버가 자동으로 정책을 기본값으로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="cad9e-107">제어판을 사용하여 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="cad9e-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="cad9e-108">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="cad9e-109">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cad9e-110">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="cad9e-111">보관 정책 목록에서 삭제하려는 사용자 또는 사이트 정책을 클릭하고, **편집** 을 클릭한 후 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="cad9e-112">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="cad9e-113">정책을 사용하여 정책 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cad9e-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="cad9e-114">**Remove-CsArchivingPolicy** cmdlet을 사용하여 보관 정책을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="cad9e-115">예를 들어 다음 명령은 ID가 site:Redmond인 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="cad9e-116">사이트 수준에서 구성된 정책이 삭제되면 이전에 사이트 정책에 의해 관리된 사용자는 자동으로 전역 보관 정책에 의해 자동으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="cad9e-117">이 명령은 사용자 수준에 적용된 모든 보관 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="cad9e-118">이 명령은 내부 보관이 해제된 모든 보관 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cad9e-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="cad9e-119">자세한 내용은 [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cad9e-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
