---
title: 비즈니스용 Skype 서버에서 회의 정책 수정
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 수정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: eafeb56dd9b0c36afffab07830a9efb71bde18fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828008"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="ab636-103">비즈니스용 Skype 서버에서 회의 정책 수정</span><span class="sxs-lookup"><span data-stu-id="ab636-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ab636-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 수정하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="ab636-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ab636-106">비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 수정</span><span class="sxs-lookup"><span data-stu-id="ab636-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ab636-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ab636-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ab636-109">왼쪽 탐색 모음에서 회의를 클릭한 다음 회의 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ab636-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="ab636-110">회의 정책 목록에서 변경할 정책을 클릭하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ab636-111">**회의 정책 편집** 에서 수정이 불가능한 정책 이름을 제외한 정책 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="ab636-112">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ab636-113">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 수정</span><span class="sxs-lookup"><span data-stu-id="ab636-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ab636-114">회의 정책을 수정하려면 **Set-CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="ab636-115">다음 예에서는 회의 정책 SalesConferencingPolicy의 속성 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="ab636-116">이 명령은 AllowConferenceRecording 속성의 값을 False로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab636-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="ab636-117">전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Set-CsConferencingPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ab636-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

