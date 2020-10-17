---
title: 'Lync Server 2013: 위치 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87bf9aff433b70bc50b3fcff209ecd14ea268e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516785"
---
# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="18d97-102">Lync Server 2013에서 위치 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="18d97-102">Creating or modifying a location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18d97-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="18d97-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="18d97-104">Lync Server 2013에서는 위치 정책을 사용 하 여 E9-1-1 (고급 9-1-1) 기능 및 사용자 또는 연락처의 위치 설정과 관련 된 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="18d97-105">위치 정책은 사용자가 E9-1-1을 사용하도록 설정되어 있는지 여부를 확인하고, 설정된 경우 긴급 통화에 대한 동작을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="18d97-106">예를 들어 위치 정책을 사용하여 긴급 통화 번호(예: 한국의 경우 119), 회사 보안 부서에 자동으로 알림을 제공할지 여부 및 통화를 라우팅할 방법을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="18d97-107">Lync Server 2013 제어판의 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="18d97-108">Lync Server 제어판에서 위치 정책을 보거나 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="18d97-109">이 섹션의 절차에 따라 위치 정책을 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-109">Use the procedures in this section to create or modify a location policy.</span></span> <span data-ttu-id="18d97-110">위치 정책을 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 삭제](lync-server-2013-deleting-a-location-policy.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18d97-110">For details on deleting location policies, see [Deleting a location policy in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).</span></span>

<span data-ttu-id="18d97-111">Lync Server 2013에서는 위치 정보 서비스에서 위치 업데이트에 대 한 클라이언트 요청 사이의 기본 시간을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-111">In Lync Server 2013, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="18d97-112">기본값은 4시간입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-112">The default value is 4 hours.</span></span> <span data-ttu-id="18d97-113">기본값을 재정의하려면 LocationRefreshInterval 매개 변수를 포함하여 **Set-CsLocationPolicy** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-113">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="18d97-114">Lync Server 제어판에서 새 위치 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="18d97-114">To create a new location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="18d97-115">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="18d97-116">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="18d97-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18d97-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="18d97-118">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **위치 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-118">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="18d97-119">**위치 정책** 페이지에서 **새로 만들기**를 클릭하고 만들려는 정책의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-119">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="18d97-p105">사이트 정책을 만들려면 **사이트 정책**을 클릭합니다. **사이트 선택**에서 정책을 적용할 사이트를 선택하고 **확인**을 클릭합니다. **새 위치 정책** 페이지의 **범위** 필드에는 **사이트** 값이 있고, **이름** 필드에는 선택한 사이트의 이름이 있습니다. 이러한 필드는 수정할 수 없습니다. 사이트 정책은 지정된 사이트의 모든 사용자에게 자동으로 적용되며 이러한 사용자에 대한 글로벌 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-p105">To create a site policy, click **Site policy**. In **Select a Site**, choose the site to which you want the policy applied and click **OK**. On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose. You cannot modify either of these fields. A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="18d97-p106">**사용자 정책**을 만들려면 **사용자 정책**을 클릭합니다. **새 위치 정책**의 **범위** 필드에는 **사용자** 값이 있습니다. 이 값은 수정할 수 없습니다. **이름** 필드에 이 정책의 이름을 입력합니다. 사용자 정책은 어떤 사용자에게도 자동으로 적용되지 않습니다. 사용자 정책을 만든 후 정책을 적용할 사용자 또는 네트워크 사이트에 정책을 수동으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-p106">To create a **User policy**, click **User policy**. In the **New Location Policy**, the **Scope** field contains the value **User**. You cannot modify this value. In the **Name** field, type the name you want to give this policy. A user policy does not automatically apply to any users. After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="18d97-131">나머지 필드를 다음과 같이 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-131">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="18d97-132">**향상 된 응급 서비스 사용**     이 정책에 연결 된 사용자가 E9-1-1에 대해 사용 하도록 설정 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-132">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="18d97-133">응급 서비스를 사용 하도록 설정 하면 Lync Server 클라이언트에서 등록에 대 한 위치 정보를 검색 하 고 긴급 통화를 수행할 때 해당 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-133">When emergency services are enabled, Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="18d97-134">**위치**     다음 값 중 하나를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-134">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="18d97-135">**필수**     클라이언트에서 새 위치에 등록할 때 위치 정보를 입력 하 라는 메시지가 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-135">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="18d97-136">사용자는 정보를 입력하지 않은 상태로 메시지를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-136">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="18d97-137">정보를 입력 하면 비상 서비스 공급자가 긴급 통화에 응답 하 여 공용 안전 응답 지점 (PSAP) 교환원에 게 라우팅되도록 (즉, 911 교환원) 전에 해당 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-137">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="18d97-138">**필요**     하지 않음 사용자에 게 위치를 입력 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-138">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="18d97-139">위치 정보 없이 통화를 수행 하면 응급 서비스 공급자가 통화에 응답 하 고 위치를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-139">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="18d97-140">고 **지**     사항 이 옵션은 사용자가 위치 정보를 입력 하지 않고 메시지를 해제할 수 없다는 점만 제외 하면 **필요한** 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-140">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="18d97-141">사용자는 여전히 긴급 통화를 완료할 수 있지만, 정보를 입력 하지 않으면 다른 전화를 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-141">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="18d97-142">또한 위치 정보 입력에 대 한 거부 결과를 알리는 고 지 사항 텍스트가 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-142">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="18d97-143">고 지 사항 텍스트를 설정 하려면 Lync Server 관리 셸을 사용 하 여 Microsoft.rtc.management.writableconfig.policy.location.enhancedemergencyservicedisclaimer 유형의 매개 변수를 통해 **설정 된 CsLocationPolicy** Cmdlet 또는 **새-cslocationpolicy** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-143">To set the disclaimer text, you must use Lync Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="18d97-144">자세한 내용은 Lync Server 관리 셸 설명서에서 [Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 또는 [New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18d97-144">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in the Lync Server Management Shell documentation.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="18d97-145">Lync Server 2013에서는 위치 정책을 사용 하 여 전체 조직에 대 한 전역 고 지만 지정할 수 있는 Lync Server 2010과는 달리, 여러 로캘 또는 다양 한 사용자 집합에 대해 서로 다른 부인를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-145">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users, unlike in Lync Server 2010 where you could specify only a global disclaimer for the entire organization.</span></span>

            
            </div>
    
      - <span data-ttu-id="18d97-146">**응급 서비스에만**     위치 사용 Lync에서는 다양 한 이유로 위치 정보를 사용할 수 있습니다 (예: 팀 구성원에 게 현재 위치를 알릴 때).</span><span class="sxs-lookup"><span data-stu-id="18d97-146">**Use location for emergency services only**   Lync can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="18d97-147">위치 정보를 긴급 통화에만 사용할 수 있도록 하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-147">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="18d97-148">**PSTN 사용**     이 프로필을 사용 하 여 클라이언트 로부터 긴급 통화를 라우팅하는 데 사용 되는 음성 경로를 결정 하는 데 사용 되는 PSTN (공중 전화망) 사용입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-148">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="18d97-149">이 사용과 연결 된 경로는 긴급 통화 전용 SIP 트렁크 또는 가장 가까운 PSAP (공개 안전 응답 지점)로 긴급 통화를 라우팅하는 비상 위치 Id 번호 (ELIN) 게이트웨이를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-149">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="18d97-150">**비상 전화 번호**     응급 서비스에 연락 하기 위해 전화를 걸 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-150">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="18d97-151">미국의 경우 이 값은 911입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-151">In the United States this value is 911.</span></span> <span data-ttu-id="18d97-152">이 문자열은 0에서 9 사이의 숫자로 구성되어야 하며 1자에서 10자 사이일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-152">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="18d97-153">**비상 다이얼 마스크**     전화를 걸 때 비상 전화 걸기 번호 값의 값으로 변환 하려는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-153">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="18d97-154">예를 들어이 필드에 212 값을 입력 하 고 긴급 전화 걸기 번호 필드의 값이 911 이면 사용자가 212 전화를 건 것이 911로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-154">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="18d97-155">이를 통해 대체 응급 번호에 전화를 걸고 여전히 통화 번호를 사용 하는 경우 (예: 다른 비상 번호가 있는 국가 또는 지역에서 현재 거주 하는 국가나 지역 번호 대신 해당 국가나 지역의 번호로 전화 걸기를 시도 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="18d97-155">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="18d97-156">예를 들어 응급 번호가 다른 국가의 사용자가 외국에서 그 나라의 번호 대신 자신의 국가에서 사용되는 번호로 전화를 거는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-156">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="18d97-157">예: 212; 414</span><span class="sxs-lookup"><span data-stu-id="18d97-157">For example, 212;414.</span></span> <span data-ttu-id="18d97-158">문자열의 최대 길이는 100자입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-158">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="18d97-159">각 문자는 0부터 9까지의 숫자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-159">Each character must be a digit 0 through 9.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="18d97-160">지정된 전화 마스크 값은 통화 대기 파킹된 통화 번호 범위와 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-160">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="18d97-161">통화 대기 라우팅은 긴급 전화 문자열 변환보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-161">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="18d97-162">기존 통화 대기 파킹된 통화 번호 범위를 보려면 왼쪽 탐색 모음에서 <STRONG>음성 기능</STRONG>을 클릭한 다음 <STRONG>통화 대기</STRONG>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-162">To see the existing call park orbit ranges, click <STRONG>Voice Features</STRONG> in the left navigation bar and then click <STRONG>Call Park</STRONG>.</span></span> <span data-ttu-id="18d97-163">자세한 내용은 <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18d97-163">For details, see <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure phone number extensions for parking calls in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="18d97-164">**알림 URI**     긴급 통화 시 알림을 받을 하나 이상의 SIP Uri (Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-164">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="18d97-165">예를 들어 회사의 보안 부서에서 응급 통화가 걸려 올 때마다 메신저 대화를 통해 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-165">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="18d97-166">발신자의 위치를 파악할 수 있는 경우 해당 위치가 알림에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-166">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="18d97-167">여러 SIP Uri를 쉼표로 구분 된 목록으로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-167">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="18d97-168">예를 들어, "sip: security@litwareinc .com", "sip: kmyer@litwareinc .com" 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-168">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="18d97-169">메일 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-169">Distribution lists are supported.</span></span> <span data-ttu-id="18d97-170">문자열의 길이는 1에서 256 자 사이 여야 하며 접두사 "sip:"로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-170">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="18d97-171">알림 URI 필드를 클릭 하기 전에 예제가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-171">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="18d97-172">**전화 회의 URI**     SIP URI (이 경우에는 비상 통화에 정책을 지 원하는 되는 타사 전화 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-172">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="18d97-173">예를 들어 **전화 회의 모드** 필드에 제공 된 값에 따라 전화를 통해 전화를 걸거나이 통화에 참가할 때 회사 보안 office에서 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-173">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="18d97-174">이 문자열은 1자에서 256자 사이여야 하며 접두사 sip:로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-174">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="18d97-175">이 필드의 내부를 클릭할 때까지 예가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-175">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="18d97-176">**전화 회의 모드**     **전화 회의 URI** 필드에 값을 지정 하면 **전화 회의 모드** 에서 타사가 통화에 참가할 수 있는지 또는 수신 대기만 하도록 할지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-176">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="18d97-177">다음 옵션 중 하나를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-177">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="18d97-178">**단방향**     제 3 자가 발신자와 PSAP 교환원 사이의 대화만 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-178">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="18d97-179">**양방향**     제 3 자가 발신자와 PSAP 교환원 간의 전화를 듣고 통화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-179">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="18d97-180">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-180">Click **Commit**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="18d97-p119">사용자 정책을 만든 경우 처음에는 이 정책이 사용자 또는 네트워크 사이트에 적용되지 않습니다. 정책을 사용자에게 적용하려면 왼쪽 탐색 모음에서 <STRONG>사용자</STRONG>를 클릭합니다. 그런 다음 정책을 적용할 사용자를 찾습니다. <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG>를 클릭합니다. <STRONG>Lync Server 사용자 편집</STRONG> 페이지의 <STRONG>위치 정책</STRONG> 드롭다운 목록에서 새 위치 정책을 선택한 다음 <STRONG>커밋</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-p119">When you create a user policy, initially that policy does not apply to any users or network sites. To apply the policy to a user, click <STRONG>Users</STRONG> in the left navigation bar. Find the user to which you want to apply the policy. On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>. On the <STRONG>Edit Lync Server User</STRONG> page, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span><BR><span data-ttu-id="18d97-p120">정책을 네트워크 사이트에 적용하려면 왼쪽 탐색 모음에서 <STRONG>네트워크 구성</STRONG>을 클릭한 다음 <STRONG>사이트</STRONG>를 클릭합니다. 그런 다음 정책을 적용할 네트워크 사이트를 찾습니다. <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG>를 클릭합니다. <STRONG>사이트 편집</STRONG>의 <STRONG>위치 정책</STRONG> 드롭다운 목록에서 새 위치 정책을 선택한 다음 <STRONG>커밋</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-p120">To apply the policy to a network site, click <STRONG>Network Configuration</STRONG> in the left navigation bar and then click <STRONG>Site</STRONG>. Find the network site to which you want to apply the policy. On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>. In <STRONG>Edit Site</STRONG>, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="18d97-190">Lync Server 제어판에서 위치 정책을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="18d97-190">To modify a location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="18d97-191">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-191">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="18d97-192">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-192">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="18d97-193">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18d97-193">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="18d97-194">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **위치 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-194">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="18d97-195">**위치 정책** 페이지에서 수정할 위치 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-195">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="18d97-196">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-196">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="18d97-197">**위치 정책 편집** 페이지에서 필요에 따라 필드를 수정합니다. 자세한 내용은 이 항목의 앞부분에 설명된 "새 위치 정책을 만들려면" 절차의 5단계를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18d97-197">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="18d97-198">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18d97-198">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18d97-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18d97-199">See Also</span></span>


[<span data-ttu-id="18d97-200">Lync Server 2013에서 위치 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="18d97-200">Deleting a location policy in Lync Server 2013</span></span>](lync-server-2013-deleting-a-location-policy.md)  


[<span data-ttu-id="18d97-201">Lync Server 2013에 대 한 위치 정책 정의</span><span class="sxs-lookup"><span data-stu-id="18d97-201">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)  


[<span data-ttu-id="18d97-202">Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성</span><span class="sxs-lookup"><span data-stu-id="18d97-202">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

