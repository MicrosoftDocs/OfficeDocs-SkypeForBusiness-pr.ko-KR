---
title: 'Lync Server 2013: 컴퓨터에서 실행 중인 서비스의 상태를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2745263bc4a179c9d99bf525aebe72b0cf299e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="7aedd-102">Lync Server 2013에서 컴퓨터에서 실행 되는 서비스의 상태 보기</span><span class="sxs-lookup"><span data-stu-id="7aedd-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aedd-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7aedd-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7aedd-104">Lync Server 2013 제어판을 사용 하 여 Lync Server 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 확인 하 고 각 서비스의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="7aedd-105">컴퓨터에서 실행되는 서비스 상태를 보려면</span><span class="sxs-lookup"><span data-stu-id="7aedd-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="7aedd-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7aedd-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7aedd-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7aedd-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7aedd-109">왼쪽 탐색 표시줄에서 **토폴로지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="7aedd-110">**상태** 페이지에서 필요에 따라 목록을 정렬하거나 검색하여 원하는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="7aedd-111">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="7aedd-112">컴퓨터에서 실행되는 서비스의 최신 상태를 보려면 **서비스 상태 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="7aedd-113">컴퓨터에서 실행되는 특정 서비스 목록 및 각 서비스의 상태를 보려면 **속성**을 클릭합니다. 목록으로 돌아오려면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7aedd-114">Windows PowerShell Cmdlet을 사용 하 여 서비스 상태 보기</span><span class="sxs-lookup"><span data-stu-id="7aedd-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7aedd-115">Windows PowerShell 및 **Get-CsWindowsService** cmdlet을 사용 하 여 서비스 상태를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="7aedd-116">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7aedd-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7aedd-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="7aedd-118">서비스 상태를 보려면</span><span class="sxs-lookup"><span data-stu-id="7aedd-118">To view service status</span></span>

  - <span data-ttu-id="7aedd-119">컴퓨터에서 서비스 상태를 확인 하려면 Lync Server 관리 셸에서 다음과 같은 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="7aedd-120">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7aedd-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="7aedd-121">자세한 내용은 [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7aedd-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7aedd-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aedd-122">See Also</span></span>


[<span data-ttu-id="7aedd-123">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="7aedd-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

