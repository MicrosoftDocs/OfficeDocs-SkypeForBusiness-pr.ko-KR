---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 삭제
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제하는 방법을 확인합니다.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119497"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="98f00-103">비즈니스용 Skype 서버에서 모임 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="98f00-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="98f00-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="98f00-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="98f00-106">사이트 또는 사용자 구성을 삭제할 수는 있지만 전역 구성은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="98f00-107">전역 구성을 삭제하려고 시도하면 자동으로 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="98f00-108">비즈니스용 Skype 서버 제어판을 사용하여 모임 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="98f00-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="98f00-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="98f00-110">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="98f00-111">왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98f00-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="98f00-112">모임 구성 목록에서 삭제할 사이트 또는 풀 구성을 클릭하고 **편집,** 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98f00-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="98f00-113">비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="98f00-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="98f00-114">모임 설정을 삭제하려면 **Remove-CsMeetingConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="98f00-115">다음 명령은 Redmond 사이트에 적용된 모임 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="98f00-116">다음 명령은 사이트 범위에 적용된 모든 모임 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="98f00-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="98f00-117">전체 매개 변수 목록을 포함하여 자세한 내용은 [Remove-CsMeetingConfiguration을 참조하십시오.](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="98f00-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
