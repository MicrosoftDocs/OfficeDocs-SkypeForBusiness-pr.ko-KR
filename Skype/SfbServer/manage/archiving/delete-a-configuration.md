---
title: 비즈니스용 Skype 서버에서 보관 구성 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '요약: 비즈니스용 Skype 서버에서 보관 구성을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 82415e2cac7293d991280c3fcee6e64d684f5c26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818940"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="9a1e1-103">비즈니스용 Skype 서버에서 보관 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="9a1e1-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="9a1e1-104">**요약:** 비즈니스용 Skype 서버에서 보관 구성을 삭제 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="9a1e1-105">사이트 구성 또는 풀 구성을 삭제할 수 있지만, 전역 구성은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="9a1e1-106">전역 구성을 삭제 하면 자동으로 기본 값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="9a1e1-107">제어판을 사용 하 여 보관 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="9a1e1-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="9a1e1-108">제어판을 사용 하 여 보관 구성을 삭제 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="9a1e1-109">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9a1e1-110">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9a1e1-111">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="9a1e1-112">보관 구성 목록에서 삭제 하려는 사이트 또는 풀 구성을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9a1e1-113">전역 구성을 클릭 해도 되지만 전역 구성을 기본값으로 다시 설정 하려는 경우에만이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="9a1e1-114">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="9a1e1-115">Windows PowerShell을 사용 하 여 보관 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="9a1e1-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="9a1e1-116">**CsArchivingConfiguration** cmdlet을 사용 하 여 보관 구성을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="9a1e1-117">예를 들어 다음 명령은 Redmond 사이트에 적용 된 보관 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="9a1e1-118">사이트 범위에서 구성 된 정책을 삭제 하는 경우 이전에 사이트 정책에서 관리 하는 사용자는 전역 보관 정책에 의해 자동으로 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="9a1e1-119">다음 명령은 서비스 범위에 적용 된 모든 보관 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="9a1e1-120">다음 명령은 Exchange 보관을 사용 하지 않도록 설정한 모든 보관 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="9a1e1-121">또한 **Remove-CsArchivingConfiguration** cmdlet을 사용 하 여 전역 설정을 기본값으로 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="9a1e1-122">예를 들어 전역 수준에서 IM 세션 보관을 사용 하도록 설정한 경우 다음 명령은 전역 수준에서 보관을 해제 하는 기본값을 없음 값으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="9a1e1-123">자세한 내용은 [제거 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a1e1-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
