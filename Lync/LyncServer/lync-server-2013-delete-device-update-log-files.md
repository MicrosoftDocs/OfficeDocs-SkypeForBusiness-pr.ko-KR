---
title: 'Lync Server 2013: 장치 업데이트 로그 파일 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fb9e6109c6f27e2985de18c2fcdf804dd184c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="514f5-102">Lync Server 2013에서 장치 업데이트 로그 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="514f5-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="514f5-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="514f5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="514f5-104">장치 업데이트 웹 서비스는 광범위 한 로그 파일 모음을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="514f5-105">이 컬렉션에는 서비스 자체에서 수행 된 감사 로그와 클라이언트 장치에서 업로드 한 로그 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="514f5-106">서버가 장치 업데이트 웹 서비스 로그를 채우지 못하도록 하려면 특정 일 수 동안 발생 한 로그 파일의 선택을 취소 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="514f5-107">업데이트 활동과 조직의 클라이언트 장치 수, Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여이 일 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="514f5-108">Lync Server 제어판을 사용 하 여 장치 업데이트 로그 지우기</span><span class="sxs-lookup"><span data-stu-id="514f5-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="514f5-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="514f5-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="514f5-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="514f5-111">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 로그 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="514f5-112">**장치 로그 구성** 페이지에서 변경 하려는 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="514f5-113">**로그 설정 편집** 대화 상자의 **로그 파일 유지 기간 (1-365)** 에 일 수를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="514f5-114">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-114">Click **Commit**.</span></span> <span data-ttu-id="514f5-115">서버에 있는 모든 파일이 지정 된 일 수를 초과 하 여 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="514f5-116">이 설정은 변경 될 때까지이 구성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="514f5-117">Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 로그 지우기</span><span class="sxs-lookup"><span data-stu-id="514f5-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="514f5-118">Windows PowerShell을 사용 하 여 장치 업데이트 로그를 지울 수 있으며, **일반-CsDeviceUpdateLog** cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="514f5-119">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="514f5-120">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="514f5-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="514f5-121">한 서버에서 장치 업데이트 로그를 지우려면</span><span class="sxs-lookup"><span data-stu-id="514f5-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="514f5-122">다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 장치 업데이트 로그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="514f5-123">10 일이 지난 모든 로그 항목 (DaysBack 매개 변수로 지정 된 값)이 로그에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="514f5-124">모든 장치 업데이트 로그를 지우려면</span><span class="sxs-lookup"><span data-stu-id="514f5-124">To clear all device update logs</span></span>

  - <span data-ttu-id="514f5-125">이 명령은 조직에서 현재 사용 중인 모든 장치 업데이트 로그의 오래 된 항목 (이 예에서는 10 일이 지난 항목)을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="514f5-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="514f5-126">자세한 내용은 [일반 CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="514f5-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

