---
title: 'Lync Server 2013: 통화 정보 기록 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12359e331e9abd2767285a5ef8c32d56433731e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="fbeb1-102">Lync Server 2013에서 통화 정보 기록 사용</span><span class="sxs-lookup"><span data-stu-id="fbeb1-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbeb1-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fbeb1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fbeb1-104">CDR (통화 정보 기록)는 인스턴스 메시징, VoIP (Voice over 인터넷 프로토콜) 통화, 응용 프로그램 공유, 파일 전송, 모임 등 피어 투 피어 활동에 대 한 사용 및 진단 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-104">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="fbeb1-105">사용 현황 데이터는 ROI (투자 수익률)를 계산 하는 데 사용할 수 있으며, 진단 데이터를 사용 하 여 피어 투 피어 활동 및 모임 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-105">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="fbeb1-106">조직의 전체 조직 또는 각 사이트에 대해 CDR를 사용 하도록 설정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fbeb1-107">CDR를 사용 하려면 모니터링과 모니터링 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="fbeb1-108">자세한 내용은 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="fbeb1-109">Lync Server 제어판에서 CDR를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fbeb1-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fbeb1-110">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fbeb1-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbeb1-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbeb1-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="fbeb1-114">**통화 정보 기록** 페이지의 표에서 해당 사이트를 클릭 하 고 **작업**을 클릭 한 다음 **CDR 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbeb1-115">CDR는 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fbeb1-116">Windows PowerShell Cmdlet을 사용 하 여 CDR 사용</span><span class="sxs-lookup"><span data-stu-id="fbeb1-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fbeb1-117">Windows PowerShell 및 **Set-CsCdrConfiguration** cmdlet을 사용 하 여 CDR를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="fbeb1-118">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fbeb1-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="fbeb1-120">단일 위치에 대해 CDR를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fbeb1-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="fbeb1-121">CDR를 사용 하지 않으려면 EnableCDR 매개 변수를 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="fbeb1-122">단일 위치에 대해 CDR를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fbeb1-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="fbeb1-123">CDR를 사용 하지 않으려면 EnableCDR 매개 변수를 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="fbeb1-124">CDR를 사용 하지 않도록 설정 하면 모니터링이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="fbeb1-125">이 메서드는 CDR 데이터의 수집 및 저장소를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="fbeb1-126">단일 명령을 사용 하 여 여러 위치에서 CDR를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fbeb1-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="fbeb1-127">이 명령은 현재 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="fbeb1-128">자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbeb1-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbeb1-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbeb1-129">See Also</span></span>


[<span data-ttu-id="fbeb1-130">Lync Server 2013의 모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="fbeb1-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="fbeb1-131">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="fbeb1-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

