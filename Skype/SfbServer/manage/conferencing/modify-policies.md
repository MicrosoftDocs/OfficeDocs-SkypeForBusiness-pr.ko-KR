---
title: 비즈니스용 Skype 서버에서 회의 정책 수정
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 4f78a956754e4375ac1dfa7460222b1fb1bbf9ef
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818509"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="5a1b9-103">비즈니스용 Skype 서버에서 회의 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5a1b9-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="5a1b9-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 수정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="5a1b9-105">Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype 서버 관리 셸을 사용 하 여 회의 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5a1b9-106">비즈니스용 Skype Server 제어판을 사용 하 여 회의 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5a1b9-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5a1b9-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="5a1b9-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5a1b9-109">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="5a1b9-110">회의 정책 목록에서 변경 하려는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5a1b9-111">**회의 편집 정책**에서 수정할 수 없는 정책 이름을 제외한 모든 정책 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="5a1b9-112">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5a1b9-113">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5a1b9-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5a1b9-114">회의 정책을 수정 하려면 **Set-CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5a1b9-115">다음 예제에서는 회의 정책 SalesConferencingPolicy의 속성 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="5a1b9-116">명령에서 AllowConferenceRecording 속성 값을 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="5a1b9-117">전체 구문 및 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b9-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

