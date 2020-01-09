---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 사용 또는 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '요약: 제어판 또는 관리 셸을 사용 하 여 비즈니스용 Skype 서버에서 전화 접속 회의를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: aed5f82678dce89190ba5449ada8eb988e1a1864
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991843"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="7e08a-103">비즈니스용 Skype 서버에서 전화 접속 회의 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="7e08a-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="7e08a-104">**요약:** 비즈니스용 Skype 서버에서 제어판 또는 관리 셸을 사용 하 여 전화 접속 회의를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="7e08a-105">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 회의를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7e08a-106">비즈니스용 Skype 서버 제어판을 사용 하 여 전화 접속 회의 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="7e08a-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7e08a-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7e08a-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7e08a-109">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="7e08a-110">회의 정책 목록에서 전화 접속 회의를 사용할 정책을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="7e08a-111">사용자가 전화를 걸어 모임에 참가할 수 있도록 허용 하려면 **PSTN 전화 접속 회의 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-111">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="7e08a-112">기본적으로 사용자는 PSTN (공개 교환 전화 네트워크)을 사용 하 여 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-112">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="7e08a-113">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7e08a-114">비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 회의 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="7e08a-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7e08a-115">전화 접속 회의를 사용 하거나 사용 하지 않도록 설정 하려면 다음과 같이 EnableDialInConferencing 매개 변수와 함께 **CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e08a-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="7e08a-116">자세한 내용은 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e08a-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

