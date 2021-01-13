---
title: 비즈니스용 Skype 서버에서 전화 접속 회의를 사용 또는 사용하지 않도록 설정
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '요약: 제어판 또는 관리 셸을 사용하여 비즈니스용 Skype 서버에서 전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 99691540306ba0cccf9c63af2e2188e839367bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828128"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="0727e-103">비즈니스용 Skype 서버에서 전화 접속 회의를 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0727e-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="0727e-104">**요약:** 제어판 또는 관리 셸을 사용하여 비즈니스용 Skype 서버에서 전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="0727e-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0727e-106">비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 회의를 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0727e-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0727e-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0727e-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0727e-109">왼쪽 탐색 모음에서 회의를 클릭한 다음 회의 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0727e-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="0727e-110">회의 정책 목록에서 전화 접속 회의를 사용하도록 설정하려는 정책을 선택하고 **편집** 을 클릭한 다음 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="0727e-p101">사용자가 전화 접속을 사용해서 모임에 참가할 수 있도록 허용하려면 **PSTN 전화 접속 회의 사용** 확인란을 선택합니다. 기본적으로 사용자는 PSTN(공중 전화망)을 사용하여 모임에 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="0727e-113">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0727e-114">비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의를 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0727e-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0727e-115">전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음과 같이 EnableDialInConferencing 매개 변수와 함께 **Set-CsConferencingPolicy** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0727e-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="0727e-116">자세한 내용은 [Set-CsConferencingPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0727e-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

