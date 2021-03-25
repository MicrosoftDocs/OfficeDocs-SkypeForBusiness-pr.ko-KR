---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 수정
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 수정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119417"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="06176-103">비즈니스용 Skype 서버에서 모임 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="06176-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="06176-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 수정하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06176-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="06176-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06176-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="06176-106">비즈니스용 Skype 서버 제어판을 사용하여 모임 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="06176-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="06176-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="06176-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="06176-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="06176-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="06176-109">왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06176-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="06176-110">모임 구성 목록에서 변경할 구성을 클릭하고 편집을 **클릭한** 다음 자세한 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06176-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="06176-111">모임 **구성 편집에서** 수정할 수 없는 구성 이름을 제외하고 모든 구성 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="06176-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="06176-112">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06176-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="06176-113">비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="06176-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="06176-114">모임 구성 설정을 수정하려면 **Set-CsMeetingConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06176-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="06176-115">다음 예제에 표시된 명령은 Redmond 사이트(-Identity site:Redmond)에 할당된 모임 구성 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="06176-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="06176-116">이 경우 DesignateAsPresenter 속성 값은 Everyone로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06176-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="06176-117">전체 매개 변수 목록을 포함하여 자세한 내용은 [Set-CsMeetingConfiguration을 참조하십시오.](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="06176-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
