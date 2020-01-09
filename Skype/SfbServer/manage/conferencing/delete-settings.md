---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: cbf63ba635077dd61599d4bc84a740906b662a6c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991863"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="09263-103">비즈니스용 Skype 서버에서 모임 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="09263-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="09263-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09263-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="09263-105">Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09263-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="09263-106">사이트 또는 사용자 구성을 삭제할 수 있지만 전역 구성은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09263-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="09263-107">전역 구성을 삭제 하려고 하면 자동으로 기본 값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09263-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="09263-108">비즈니스용 Skype 서버 제어판을 사용 하 여 모임 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="09263-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="09263-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="09263-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="09263-110">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09263-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="09263-111">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09263-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="09263-112">모임 구성 목록에서 삭제 하려는 사이트 또는 풀 구성을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09263-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="09263-113">비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="09263-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="09263-114">모임 설정을 삭제 하려면 **Remove-CsMeetingConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="09263-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="09263-115">다음 명령은 Redmond 사이트에 적용 된 모임 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="09263-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="09263-116">다음 명령을 실행 하면 사이트 범위에 적용 된 모든 모임 구성 설정이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09263-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="09263-117">전체 매개 변수 목록을 비롯 한 자세한 내용은 [제거-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09263-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

