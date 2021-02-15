---
title: 비즈니스용 Skype에서 사용자에 대해 통화 파크 사용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 사용자가 비즈니스용 Skype 서버에서 통화 파크를 사용할 수 있도록 Enterprise Voice.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830958"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="224d5-103">비즈니스용 Skype에서 사용자에 대해 통화 파크 사용</span><span class="sxs-lookup"><span data-stu-id="224d5-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="224d5-104">사용자가 비즈니스용 Skype 서버에서 통화 파크를 사용할 수 있도록 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="224d5-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="224d5-105">기본적으로 모든 사용자에 대해 통화 파크는 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="224d5-106">사용자는 음성 정책에서 통화 파크를 사용하도록 설정해야 통화를 파기하거나 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="224d5-107">전역 범위 또는 사이트 범위 또는 사용자 범위에서 통화 파크를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="224d5-108">사용자 범위는 사이트 범위보다 우선하고 사이트 범위는 전역 범위보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="224d5-109">음성 정책이 여러 개 있는 경우 전역 정책이 아닌 모든 정책을 검토하여 통화 파크를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="224d5-110">비즈니스용 Skype 서버 제어판을 사용하여 사용자에 대해 통화 파크를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="224d5-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="224d5-111">**RTCUniversalServerAdmins** 그룹의 구성원이나 **CsVoiceAdministrator**, **CsServerAdministrator** 또는 **CsAdministrator** 관리 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="224d5-112">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="224d5-113">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="224d5-114">**음성 정책** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="224d5-115">기존 음성 정책을 두 번 클릭하여 **음성 정책 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="224d5-116">**전화 걸기 기능** 에서 **통화 대기 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="224d5-117">**확인** 을 클릭하여 음성 정책을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="224d5-118">Cmdlet을 사용하여 사용자에 대해 통화 파킹을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="224d5-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="224d5-119">RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="224d5-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="224d5-120">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="224d5-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="224d5-121">실행:</span><span class="sxs-lookup"><span data-stu-id="224d5-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="224d5-122">예를 들어 기본 전역 음성 정책에 대해 통화 파크를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="224d5-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="224d5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="224d5-123">See also</span></span>



[<span data-ttu-id="224d5-124">음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="224d5-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

