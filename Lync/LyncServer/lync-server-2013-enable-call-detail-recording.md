---
title: 'Lync Server 2013: 통화 정보 기록 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d9227c1b3486ea20d6a1dc9c82311bfd17633bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="c6455-102">Lync Server 2013에서 통화 정보 기록 사용</span><span class="sxs-lookup"><span data-stu-id="c6455-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6455-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c6455-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c6455-p101">CDR(통화 정보 기록)은 인스턴트 메시징, VoIP(Voice over Internet Protocol) 통화, 응용 프로그램 공유, 파일 전송, 모임 등의 피어 투 피어 활동에 대한 사용 및 진단 정보를 기록합니다. 이러한 사용 데이터는 ROI(투자 수익률)를 계산하는 데 사용하고, 진단 데이터는 피어-투-피어 활동 및 모임 관련 문제를 해결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="c6455-106">다음 절차에 따라 조직의 각 사이트 또는 조직 전체에 대해 CDR을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6455-107">CDR을 사용하도록 설정하려면 먼저 모니터링 및 모니터링 데이터베이스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="c6455-108">자세한 내용은 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6455-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="c6455-109">Lync Server 제어판에서 CDR을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="c6455-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c6455-110">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="c6455-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c6455-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6455-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c6455-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **통화 정보 기록**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="c6455-114">**통화 정보 기록** 페이지의 표에서 적절한 사이트를 클릭하고 **동작**을 클릭한 후에 **CDR 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6455-115">CDR은 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c6455-116">Windows PowerShell Cmdlet을 사용 하 여 CDR 사용</span><span class="sxs-lookup"><span data-stu-id="c6455-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c6455-117">Windows PowerShell 및 **get-cscdrconfiguration** cmdlet을 사용 하 여 CDR을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="c6455-118">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c6455-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6455-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="c6455-120">단일 위치에 대해 CDR을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c6455-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="c6455-121">CDR을 사용하도록 설정하려면 EnableCDR 매개 변수를 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="c6455-122">단일 위치에 대해 CDR을 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c6455-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="c6455-123">CDR을 사용하지 않도록 설정하려면 EnableCDR 매개 변수를 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="c6455-124">CDR를 사용 하지 않도록 설정 하면 모니터링이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="c6455-125">CDR 데이터의 수집 및 저장을 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="c6455-126">단일 명령을 사용하여 여러 위치에서 CDR을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c6455-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="c6455-127">다음 명령은 조직에서 현재 사용 중인 모든 CDR 구성 설정에 대해 CDR을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6455-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="c6455-128">자세한 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6455-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6455-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6455-129">See Also</span></span>


[<span data-ttu-id="c6455-130">Lync Server 2013의 모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="c6455-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="c6455-131">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="c6455-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

