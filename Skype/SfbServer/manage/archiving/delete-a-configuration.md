---
title: 비즈니스용 Skype 서버에서 보관 구성 삭제
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '요약: 비즈니스용 Skype 서버에서 보관 구성을 삭제하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817628"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="bfb10-103">비즈니스용 Skype 서버에서 보관 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="bfb10-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="bfb10-104">**요약:** 비즈니스용 Skype 서버에서 보관 구성을 삭제하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="bfb10-105">사이트 구성 또는 풀 구성은 삭제할 수 있지만 전역 구성은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="bfb10-106">전역 구성을 삭제하는 경우 자동으로 구성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="bfb10-107">제어판을 사용하여 보관 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="bfb10-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="bfb10-108">제어판을 사용하여 보관 구성을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="bfb10-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="bfb10-109">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="bfb10-110">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bfb10-111">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="bfb10-112">보관 구성 목록에서 삭제할 사이트 또는 풀 구성을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bfb10-113">전역 구성을 클릭할 수도 있지만 전역 구성을 기본값으로 다시 설정하려는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="bfb10-114">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="bfb10-115">보관 구성을 사용하여 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfb10-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="bfb10-116">**Remove-CsArchivingConfiguration** cmdlet을 사용하여 보관 구성을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="bfb10-117">예를 들어 다음 명령은 Redmond 사이트에 적용된 보관 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="bfb10-118">사이트 범위에서 구성된 정책이 삭제되면 이전에 사이트 정책에 의해 관리된 사용자는 자동으로 전역 보관 정책에 의해 자동으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="bfb10-119">다음 명령은 서비스 범위에 적용된 모든 보관 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="bfb10-120">다음 명령은 Exchange 보관을 사용하지 않도록 설정한 모든 보관 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="bfb10-121">**Remove-CsArchivingConfiguration** cmdlet을 사용하여 전역 설정을 기본값으로 다시 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="bfb10-122">예를 들어 IM 세션 보관을 전역 수준에서 사용하도록 설정했다고 가정해 보겠습니다. 다음 명령은 값을 기본값 None으로 다시 설정하여 전역 수준에서 보관을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb10-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="bfb10-123">자세한 내용은 [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfb10-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
