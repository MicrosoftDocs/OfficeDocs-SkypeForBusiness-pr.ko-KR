---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 수정
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 893e3fb8c9c441f8dc515eaf3a8a4aaa1ff04620
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818499"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c2c10-103">비즈니스용 Skype 서버에서 모임 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="c2c10-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c2c10-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 수정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c2c10-105">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c2c10-106">비즈니스용 Skype Server 제어판을 사용 하 여 모임 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="c2c10-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c2c10-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="c2c10-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c2c10-109">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="c2c10-110">모임 구성 목록에서 변경 하려는 구성을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c2c10-111">**모임 구성 편집**에서 수정할 수 없는 구성 이름을 제외한 모든 구성 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="c2c10-112">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c2c10-113">비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="c2c10-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c2c10-114">모임 구성 설정을 수정 하려면 **Set-CsMeetingConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="c2c10-115">다음 예제에 표시 된 명령은 Redmond 사이트 (-Id 사이트: Redmond)에 할당 된 모임 구성 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="c2c10-116">이 경우 DesignateAsPresenter 속성의 값은 모든 사용자로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2c10-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="c2c10-117">전체 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2c10-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

