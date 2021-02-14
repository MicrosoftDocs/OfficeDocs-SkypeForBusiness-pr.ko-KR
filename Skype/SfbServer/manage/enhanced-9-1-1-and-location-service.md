---
title: 향상된 9-1-1 및 위치 서비스 관리
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
description: 비즈니스용 Skype 서버는 비즈니스용 Skype 클라이언트의 E9-1-1(고급 9-1-1) 통화를 지원합니다. E9-1-1에 대해 비즈니스용 Skype 서버를 구성할 때 비즈니스용 Skype에서 걸려 오는 긴급 통화에는 위치 정보 서비스 데이터베이스의 ERL(응급 응답 위치) 정보가 포함됩니다.
ms.openlocfilehash: c5b626763de78495a2feaa5ecb1ba77e367bd77d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817478"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a><span data-ttu-id="a00b1-104">부산용 Skype 서버에서 향상된 9-1-1 및 위치 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="a00b1-104">Manage enhanced 9-1-1 and the Location service in Skype for Busines Server</span></span>

<span data-ttu-id="a00b1-105">비즈니스용 Skype 서버는 비즈니스용 Skype 클라이언트의 E9-1-1(고급 9-1-1) 통화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-105">Skype for Business Server supports Enhanced 9-1-1 (E9-1-1) calling from Skype for Business clients.</span></span> <span data-ttu-id="a00b1-106">E9-1-1에 대해 비즈니스용 Skype 서버를 구성할 때 비즈니스용 Skype에서 걸려 오는 긴급 통화에는 위치 정보 서비스 데이터베이스의 ERL(응급 응답 위치) 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-106">When you configure Skype for Business Server for E9-1-1, emergency calls placed from Skype for Business include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="a00b1-107">이 문서의 절차에 따라 위치 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-107">Use the procedures in this article to manage location policy.</span></span>

> [!Note]
> <span data-ttu-id="a00b1-108">E9-1-1 Enterprise Voice 위치 정보 서비스 등의 고급 Enterprise Voice 배포에 대한 자세한 내용은 고급 Enterprise Voice [기능을 참조하십시오.](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="a00b1-108">For details on deploying advanced Enterprise Voice features, such as E9-1-1 and the Location Information service, see [Deploy advanced Enterprise Voice features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).</span></span>

<span data-ttu-id="a00b1-109">비즈니스용 Skype 서버에서 위치 정책을 사용하여 E9-1-1(고급 9-1-1) 기능과 관련된 설정과 사용자 또는 연락처의 위치 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-109">In Skype for Business Server, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="a00b1-110">위치 정책은 사용자가 E9-1-1을 사용하도록 설정되어 있는지 여부를 확인하고, 설정된 경우 긴급 통화에 대한 동작을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-110">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="a00b1-111">예를 들어 위치 정책을 사용하여 긴급 통화 번호(예: 한국의 경우 119), 회사 보안 부서에 자동으로 알림을 제공할지 여부 및 통화를 라우팅할 방법을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-111">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="a00b1-112">비즈니스용 Skype 서버  제어판의 네트워크 구성 그룹에서 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-112">You can configure location policies from the **Network Configuration** group in the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="a00b1-113">비즈니스용 Skype 서버 제어판에서 위치 정책을 보거나 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-113">From the Skype for Business Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="a00b1-114">다음 절차에 따라 위치 정책에 대한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-114">Use the following procedure to view information about location policies.</span></span> 


## <a name="view-location-policy-information"></a><span data-ttu-id="a00b1-115">위치 정책 정보 보기</span><span class="sxs-lookup"><span data-stu-id="a00b1-115">View location policy information</span></span> 

1.  <span data-ttu-id="a00b1-116">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-116">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a00b1-117">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-117">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a00b1-118">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 **위치 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a00b1-118">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="a00b1-119">**위치 정책** 페이지에서 수정할 위치 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-119">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="a00b1-120">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-120">On the **Edit** menu, click **Show details**.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="a00b1-121">한 번에 한 위치 정책에 대한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-121">You can only view information about one location policy at a time.</span></span>

<span data-ttu-id="a00b1-p105">글로벌이라는 단일 정책은 기본적으로 존재하며, 삭제하거나 이름을 바꿀 수 없습니다. 그러나 글로벌 정책을 수정할 수는 있습니다. 이 정책은 사이트 정책 또는 사용자별 정책을 만들지 않은 경우 모든 사용자 및 대화 상대에 적용됩니다. 사용자별 정책은 특정 사용자에게 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-p105">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>


## <a name="create-or-modify-a-location-policy"></a><span data-ttu-id="a00b1-126">위치 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="a00b1-126">Create or modify a location policy</span></span> 

<span data-ttu-id="a00b1-127">비즈니스용 Skype 서버에서 위치 정보 서비스의 위치 업데이트에 대한 클라이언트 요청 간의 기본 시간을 다시 정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-127">In Skype for Business Server, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="a00b1-128">기본값은 4시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-128">The default value is 4 hours.</span></span> <span data-ttu-id="a00b1-129">기본값을 재정의하려면 LocationRefreshInterval 매개 변수를 포함하여 **Set-CsLocationPolicy** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-129">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a><span data-ttu-id="a00b1-130">비즈니스용 Skype 서버 제어판에서 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-130">To create a new location policy in the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a00b1-131">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-131">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a00b1-132">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-132">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a00b1-133">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 **위치 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a00b1-133">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="a00b1-134">**위치 정책** 페이지에서 **새로 만들기** 를 클릭하고 만들려는 정책의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-134">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="a00b1-p107">사이트 정책을 만들려면 **사이트 정책** 을 클릭합니다. **사이트 선택** 에서 정책을 적용할 사이트를 선택하고 **확인** 을 클릭합니다. **새 위치 정책** 페이지의 **범위** 필드에는 **사이트** 값이 있고, **이름** 필드에는 선택한 사이트의 이름이 있습니다. 이러한 필드는 수정할 수 없습니다. 사이트 정책은 지정된 사이트의 모든 사용자에게 자동으로 적용되며 이러한 사용자에 대한 글로벌 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-p107">To create a site policy, click **Site policy**. In **Select a Site**, choose the site to which you want the policy applied and click **OK**. On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose. You cannot modify either of these fields. A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="a00b1-p108">**사용자 정책** 을 만들려면 **사용자 정책** 을 클릭합니다. **새 위치 정책** 의 **범위** 필드에는 **사용자** 값이 있습니다. 이 값은 수정할 수 없습니다. **이름** 필드에 이 정책의 이름을 입력합니다. 사용자 정책은 어떤 사용자에게도 자동으로 적용되지 않습니다. 사용자 정책을 만든 후 정책을 적용할 사용자 또는 네트워크 사이트에 정책을 수동으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-p108">To create a **User policy**, click **User policy**. In the **New Location Policy**, the **Scope** field contains the value **User**. You cannot modify this value. In the **Name** field, type the name you want to give this policy. A user policy does not automatically apply to any users. After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="a00b1-146">나머지 필드를 다음과 같이 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-146">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="a00b1-147">**향상된 응급 서비스 사용**   이 정책과 연결된 사용자가 E9-1-1에 대해 사용하도록 설정하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-147">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="a00b1-148">응급 서비스를 사용하도록 설정하면 비즈니스용 Skype 서버 클라이언트는 등록에 대한 위치 정보를 검색하고 긴급 통화가 걸려 오면 해당 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-148">When emergency services are enabled, Skype for Business Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="a00b1-149">**위치**   다음 값 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-149">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="a00b1-150">**필수**   클라이언트가 새 위치에 등록하면 사용자에게 위치 정보를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-150">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="a00b1-151">사용자는 정보를 입력하지 않은 상태로 메시지를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-151">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="a00b1-152">정보를 입력하면 응급 서비스 공급자가 응급 통화에 응답하여 위치를 확인한 후 PSAP(Public Safety Answering Point) 운영자(즉, 911 운영자)로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-152">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="a00b1-153">**필요하지 않습니다.**   사용자에게 위치를 묻는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-153">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="a00b1-154">위치 정보가 없는 전화가 걸려오면 응급 서비스 공급자가 통화에 응답하고 위치를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-154">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="a00b1-155">**고지 조항**   이 옵션은 필수  옵션과 동일합니다. 단, 사용자가 위치 정보를 입력하지 않고는 메시지를 지울 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-155">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="a00b1-156">사용자는 긴급 통화를 완료할 수 있지만 정보를 입력하지 않고는 다른 통화를 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-156">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="a00b1-157">또한 위치 정보 입력이 감소할 경우의 결과를 사용자에게 경고할 수 있는 고지 사항은 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-157">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="a00b1-158">고지 조항 텍스트를 설정하려면 비즈니스용 Skype 서버 관리 셸을 사용하여 **Set-CsLocationPolicy** cmdlet 또는 **New-CsLocationPolicy** cmdlet을 EnhancedEmergencyServiceDisclaimer 매개 변수와 함께 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-158">To set the disclaimer text, you must use the Skype for Business Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="a00b1-159">자세한 내용은 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 또는 [New-CsLocationPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)</span><span class="sxs-lookup"><span data-stu-id="a00b1-159">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).</span></span>
          
    
      - <span data-ttu-id="a00b1-160">**응급 서비스에만 위치 사용** 비즈니스용 Skype는 다양한 이유로 위치 정보를 사용할 수 있습니다(예: 팀원에게 현재 위치를 알리기 위해).</span><span class="sxs-lookup"><span data-stu-id="a00b1-160">**Use location for emergency services only** Skype for Business can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="a00b1-161">위치 정보를 긴급 통화에만 사용할 수 있도록 하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-161">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="a00b1-162">**PSTN 사용**   이 프로필을 사용하여 클라이언트의 긴급 통화를 라우팅하는 데 사용할 음성 경로를 결정하는 데 사용할 PSTN(공용 전화망) 사용입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-162">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="a00b1-163">이 사용법과 연결된 경로는 긴급 통화 전용 SIP 트렁크 또는 긴급 통화를 가장 가까운 PSAP(Public Safety Answering Point)로 라우팅하는 ELIN(Emergency Location Identification Number) 게이트웨이를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-163">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="a00b1-164">**긴급 전화 번호**   응급 서비스에 연결하기 위해 전화를 걸 수 있는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-164">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="a00b1-165">미국의 경우 이 값은 911입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-165">In the United States this value is 911.</span></span> <span data-ttu-id="a00b1-166">이 문자열은 0에서 9 사이의 숫자로 구성되어야 하며 1자에서 10자 사이일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-166">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="a00b1-167">**긴급 다이얼 마스크**   전화를 걸 때 긴급 전화 번호 값으로 변환할 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-167">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="a00b1-168">예를 들어 이 필드에 212 값을 입력하고 긴급 전화 번호 필드의 값이 911인 경우 사용자가 212로 전화를 걸면 911로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-168">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="a00b1-169">이렇게 하면 대체 긴급 번호로 전화를 걸 수 있으며 통화가 긴급 서비스에 연결될 수 있습니다(예: 다른 긴급 번호가 있는 국가나 지역의 누군가가 현재 있는 국가나 지역의 번호가 아닌 해당 국가나 지역의 번호로 전화를 걸려 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="a00b1-169">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="a00b1-170">예를 들어 응급 번호가 다른 국가의 사용자가 외국에서 그 나라의 번호 대신 자신의 국가에서 사용되는 번호로 전화를 거는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-170">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="a00b1-171">예를 들어 212;414입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-171">For example, 212;414.</span></span> <span data-ttu-id="a00b1-172">문자열의 최대 길이는 100자입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-172">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="a00b1-173">각 문자는 0부터 9까지의 숫자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-173">Each character must be a digit 0 through 9.</span></span>
      

        > [!IMPORTANT]  
        > <span data-ttu-id="a00b1-174">지정된 전화 마스크 값은 통화 대기 파킹된 통화 번호 범위와 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-174">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="a00b1-175">통화 대기 라우팅은 긴급 전화 문자열 변환보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-175">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="a00b1-176">기존 통화 대기 파킹된 통화 번호 범위를 보려면 왼쪽 탐색 모음에서 **음성 기능** 을 클릭한 다음 **통화 대기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-176">To see the existing call park orbit ranges, click **Voice Features** in the left navigation bar and then click **Call Park**.</span></span> 

    
      - <span data-ttu-id="a00b1-177">**알림 URI**   긴급 통화가 걸려 오면 알림을 하게 될 하나 이상의 SIP UR(Uniform Resource Identifiers)입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-177">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="a00b1-178">예를 들어 회사의 보안 부서에서 응급 통화가 걸려 올 때마다 메신저 대화를 통해 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-178">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="a00b1-179">발신자의 위치를 파악할 수 있는 경우 해당 위치가 알림에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-179">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="a00b1-180">여러 SIP URIS를 콤보로 구분된 목록으로 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-180">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="a00b1-181">예를 들어 "sip:security@litwareinc.com","sip:kmyer@litwareinc.com"입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-181">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="a00b1-182">메일 목록이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-182">Distribution lists are supported.</span></span> <span data-ttu-id="a00b1-183">문자열은 1자에서 256자까지의 길이를 요구하며 "sip:"</span><span class="sxs-lookup"><span data-stu-id="a00b1-183">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="a00b1-184">알림 URI 필드를 클릭하기 전에 예제가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-184">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="a00b1-185">**회의 URI**   이 경우 전화를 걸 수 있는 긴급 통화에 전화 회의할 제3자에 대한 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-185">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="a00b1-186">예를 들어 회사 보안 사무소는 긴급 통화가 걸려 올 때 전화를 받고 전화 회의 모드 필드에 제공된 값에 따라 해당 통화를 듣거나 통화에 참가할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-186">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="a00b1-187">이 문자열은 1자에서 256자 사이여야 하며 접두사 sip:로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-187">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="a00b1-188">이 필드 내부를 클릭할 때까지 예제가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-188">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="a00b1-189">**회의 모드**   전화 회의 **URI** 필드에 값을 지정하면 전화 회의 모드는 제3자만 통화에 참가할 수 있는지 또는 들을 수만 있는지를 판정합니다. </span><span class="sxs-lookup"><span data-stu-id="a00b1-189">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="a00b1-190">다음 옵션 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-190">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="a00b1-191">**단방향**   제3자가 발신자와 PSAP 교환원 사이의 대화를 들을 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-191">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="a00b1-192">**양방향**   제3자가 발신자와 PSAP 교환원 사이의 대화를 듣고 통화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-192">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="a00b1-193">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-193">Click **Commit**.</span></span>


    > [!IMPORTANT]  
    > <span data-ttu-id="a00b1-194">사용자 정책을 만든 경우 처음에는 이 정책이 사용자 또는 네트워크 사이트에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-194">When you create a user policy, initially that policy does not apply to any users or network sites.</span></span> <span data-ttu-id="a00b1-195">정책을 사용자에게 적용하려면 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-195">To apply the policy to a user, click **Users** in the left navigation bar.</span></span> <span data-ttu-id="a00b1-196">그런 다음 정책을 적용할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-196">Find the user to which you want to apply the policy.</span></span> <span data-ttu-id="a00b1-197">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-197">On the **Edit** menu, click **Show details**.</span></span> <span data-ttu-id="a00b1-198">서버 사용자 **편집 페이지에서** 위치 정책 드롭다운  목록에서 새 위치 정책을 선택하고 커밋을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a00b1-198">On the **Edit Server User** page, select the new location policy from the **Location policy** drop-down list and then click **Commit**.</span></span><BR><span data-ttu-id="a00b1-p122">정책을 네트워크 사이트에 적용하려면 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭한 다음 **사이트** 를 클릭합니다. 그런 다음 정책을 적용할 네트워크 사이트를 찾습니다. **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다. **사이트 편집** 의 **위치 정책** 드롭다운 목록에서 새 위치 정책을 선택한 다음 **커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-p122">To apply the policy to a network site, click **Network Configuration** in the left navigation bar and then click **Site**. Find the network site to which you want to apply the policy. On the **Edit** menu, click **Show details**. In **Edit Site**, select the new location policy from the **Location policy** drop-down list and then click **Commit**.</span></span>


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a><span data-ttu-id="a00b1-203">비즈니스용 Skype 서버 제어판에서 위치 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="a00b1-203">To modify a location policy in the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a00b1-204">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-204">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a00b1-205">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-205">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a00b1-206">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 **위치 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a00b1-206">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="a00b1-207">**위치 정책** 페이지에서 수정할 위치 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-207">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="a00b1-208">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-208">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a00b1-209">**위치 정책 편집** 페이지에서 필요에 따라 필드를 수정합니다. 자세한 내용은 이 항목의 앞부분에 설명된 "새 위치 정책을 만들려면" 절차의 5단계를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a00b1-209">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="a00b1-210">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-210">Click **Commit**.</span></span>

        
## <a name="delete-a-location-policy"></a><span data-ttu-id="a00b1-211">위치 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="a00b1-211">Delete a location policy</span></span>


1.  <span data-ttu-id="a00b1-212">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-212">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a00b1-213">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-213">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a00b1-214">왼쪽 탐색 모음에서 네트워크 구성을 **클릭한** 다음 **위치 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a00b1-214">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="a00b1-215">**위치 정책** 페이지에서 삭제할 위치 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-215">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="a00b1-p123">한 번에 둘 이상의 위치 정책을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 채 여러 정책을 선택합니다. 또는 모든 정책을 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-p123">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click **Select all** on the **Edit** menu.</span></span>


5.  <span data-ttu-id="a00b1-219">**편집** 메뉴에서 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-219">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="a00b1-220">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-220">Click **OK**.</span></span>

    > [!IMPORTANT]  
    > <span data-ttu-id="a00b1-p124">전역 위치 정책은 삭제할 수 없습니다. 글로벌 정책을 삭제하려고 하면 경고 메시지가 나타나고 해당 정책이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00b1-p124">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>


## <a name="see-also"></a><span data-ttu-id="a00b1-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a00b1-223">See Also</span></span>

[<span data-ttu-id="a00b1-224">네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="a00b1-224">Create or modify network sites</span></span>](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[<span data-ttu-id="a00b1-225">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="a00b1-225">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[<span data-ttu-id="a00b1-226">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="a00b1-226">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[<span data-ttu-id="a00b1-227">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="a00b1-227">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[<span data-ttu-id="a00b1-228">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="a00b1-228">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
