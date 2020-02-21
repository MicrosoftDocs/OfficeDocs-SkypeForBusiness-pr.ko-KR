---
title: 'Lync Server 2013: 아웃 바운드 통화에 대 한 음성 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a697dae1be3d59692746303f230968782db4f38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="a5e94-102">Lync Server 2013에서 아웃 바운드 통화에 대 한 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="a5e94-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5e94-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a5e94-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a5e94-104">Lync Server 2013 음성 경로는 대상 전화 번호를 하나 이상의 PSTN (공중 전화망) 게이트웨이 또는 SIP 트렁크와 하나 이상의 PSTN 사용 레코드와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="a5e94-105">**Lync Server 제어판을 사용 하 여 음성 경로를 보려면**</span><span class="sxs-lookup"><span data-stu-id="a5e94-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="a5e94-106">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a5e94-107">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5e94-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a5e94-108">**음성 라우팅**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="a5e94-109">**경로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-109">Click **Route**.</span></span>

4.  <span data-ttu-id="a5e94-p102">음성 경로를 두 번 클릭하여 음성 경로 목록에서 추가 속성을 보거나 경로를 선택하고 **편집**을 클릭한 후 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5e94-112">한 번에 하나씩 단일 경로에 대한 자세한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="a5e94-113">**Windows PowerShell을 사용 하 여 음성 경로를 보려면**</span><span class="sxs-lookup"><span data-stu-id="a5e94-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="a5e94-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="a5e94-115">음성 경로는 Windows PowerShell 및 **get-csvoiceroute** cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="a5e94-116">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a5e94-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5e94-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="a5e94-118">모든 음성 경로에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="a5e94-119">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e94-119">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="a5e94-120">자세한 내용은 계획 설명서에서 <A href="lync-server-2013-voice-routes.md">Lync Server 2013의 음성 경로</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5e94-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5e94-121">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a5e94-121">In This Section</span></span>

  - [<span data-ttu-id="a5e94-122">Lync Server 2013에서 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="a5e94-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="a5e94-123">Lync Server 2013에서 음성 경로 수정</span><span class="sxs-lookup"><span data-stu-id="a5e94-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5e94-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5e94-124">See Also</span></span>


[<span data-ttu-id="a5e94-125">Lync Server 2013에서 음성 라우팅 관리</span><span class="sxs-lookup"><span data-stu-id="a5e94-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

