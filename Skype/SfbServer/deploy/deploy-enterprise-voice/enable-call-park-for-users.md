---
title: 비즈니스용 Skype에서 사용자에 게 통화 공원 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 공원에 사용자를 설정 합니다.
ms.openlocfilehash: 797b17cb3d9482d9059bedcbbc347c3dd592e478
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240638"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="fff70-103">비즈니스용 Skype에서 사용자에 게 통화 공원 사용</span><span class="sxs-lookup"><span data-stu-id="fff70-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="fff70-104">비즈니스용 Skype Server Enterprise Voice에서 통화 공원에 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fff70-105">기본적으로 모든 사용자에 대해 통화 대기를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="fff70-106">음성 정책에서 통화 대기를 사용할 수 있을 때까지 사용자는 통화를 대기 시 키 지 않거나 파킹 된 통화를 검색 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="fff70-107">전역 범위 또는 사이트 범위 또는 사용자 범위에서 통화 파킹 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="fff70-108">사용자 범위는 사이트 범위 보다 우선 하며 사이트 범위는 전역 범위 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="fff70-109">음성 정책이 여러 개 있는 경우 모든 정책을 검토 하 여 전역 정책만이 아닌 통화 대기 기능을 사용 하도록 설정 하세요.</span><span class="sxs-lookup"><span data-stu-id="fff70-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="fff70-110">비즈니스용 Skype Server 제어판을 사용 하 여 사용자에 게 전화를 걸 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fff70-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="fff70-111">**RTCUniversalServerAdmins** 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="fff70-112">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fff70-113">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="fff70-114">**음성 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="fff70-115">기존 음성 정책을 두 번 클릭 하 여 **음성 정책 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="fff70-116">**호출 기능**에서 **통화 공원 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="fff70-117">**확인** 을 클릭 하 여 음성 정책 저장</span><span class="sxs-lookup"><span data-stu-id="fff70-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="fff70-118">Cmdlet을 사용 하 여 사용자를 위한 통화 파킹 사용</span><span class="sxs-lookup"><span data-stu-id="fff70-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="fff70-119">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="fff70-120">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fff70-121">런</span><span class="sxs-lookup"><span data-stu-id="fff70-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="fff70-122">예를 들어 기본 전역 음성 정책에 대 한 통화 파킹 기능을 사용 하도록 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff70-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="fff70-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fff70-123">See also</span></span>



[<span data-ttu-id="fff70-124">비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="fff70-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

