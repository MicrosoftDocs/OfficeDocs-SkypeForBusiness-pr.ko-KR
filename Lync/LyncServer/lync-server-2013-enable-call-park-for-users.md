---
title: 'Lync Server 2013: 사용자에 대해 통화 대기를 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8d739c9987c0a17c29997fad8ac47b2d886fbea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="829fe-102">Lync Server 2013의 사용자에 대해 통화 대기를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="829fe-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="829fe-103">_**마지막으로 수정 된 항목:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="829fe-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="829fe-104">음성 정책에서 통화 대기를 사용 하도록 설정 하기 전까지 사용자는 통화를 대기 시키거나 대기 중인 통화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="829fe-105">기본적으로 모든 사용자에 대해 통화 대기를 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="829fe-106">전역 범위나 사이트 범위 또는 사용자 범위에서 통화 대기를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="829fe-107">사용자 범위는 사이트 범위보다 우선하고 사이트 범위는 전역 범위보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="829fe-108">음성 정책이 여러 개인 경우에는 모든 정책을 검토 하 여 전역 정책 뿐 아니라 통화 대기를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="829fe-109">Lync Server 제어판을 사용 하 여 사용자에 대해 통화 대기를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="829fe-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="829fe-110">**RTCUniversalServerAdmins** 그룹의 구성원이나 **CsVoiceAdministrator**, **CsServerAdministrator** 또는 **CsAdministrator** 관리 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="829fe-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="829fe-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="829fe-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="829fe-113">왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="829fe-114">**음성 정책** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="829fe-115">기존 음성 정책을 두 번 클릭하여 **음성 정책 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="829fe-116">**전화 걸기 기능**에서 **통화 대기 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="829fe-117">**확인**을 클릭하여 음성 정책을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="829fe-118">Cmdlet을 사용 하 여 사용자에 대 한 통화 대기를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="829fe-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="829fe-119">RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="829fe-120">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="829fe-121">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="829fe-122">예를 들어 기본 전역 음성 정책에 대해 통화 대기를 사용 하도록 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="829fe-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="829fe-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="829fe-123">See Also</span></span>


[<span data-ttu-id="829fe-124">Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="829fe-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

