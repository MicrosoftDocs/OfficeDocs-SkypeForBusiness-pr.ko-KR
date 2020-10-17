---
title: 'Lync Server 2013: 장치 업데이트 로그 파일 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 576daa823dfd5bb8e6e7eb8c6bedeaa689780dbe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514465"
---
# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="e3db4-102">Lync Server 2013에서 장치 업데이트 로그 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="e3db4-102">Delete Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3db4-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e3db4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e3db4-104">장치 업데이트 웹 서비스는 광범위 한 로그 파일 모음을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="e3db4-105">이 컬렉션에는 서비스 자체 및 클라이언트 장치에서 업로드 된 로그 파일에서 수행한 감사 로그가 모두 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="e3db4-106">서버가 장치 업데이트 웹 서비스 로그에 가득 차지 않도록 하는 것을 방지 하기 위해 특정 일 수 동안 발생 한 로그 파일을 지워야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="e3db4-107">업데이트 작업 및 조직의 클라이언트 장치 수와 Lync server 제어판 또는 Lync Server 관리 셸을 사용 하 여이 날짜 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="e3db4-108">Lync Server 제어판을 사용 하 여 장치 업데이트 로그를 지우려면</span><span class="sxs-lookup"><span data-stu-id="e3db4-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e3db4-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e3db4-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3db4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e3db4-111">왼쪽 탐색 표시줄에서 **클라이언트**, **장치 로그 구성**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="e3db4-112">**장치 로그 구성** 페이지에서 변경할 구성을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="e3db4-113">**로그 설정 편집** 대화 상자에서 **로그 파일 보존 기간 1-365 (일) (** 일 수)</span><span class="sxs-lookup"><span data-stu-id="e3db4-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="e3db4-114">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-114">Click **Commit**.</span></span> <span data-ttu-id="e3db4-115">서버에 있는 모든 파일이 지정 된 일 수를 초과 하 여 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="e3db4-116">이 설정은 사용자가 변경할 때까지이 구성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="e3db4-117">Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 로그 지우기</span><span class="sxs-lookup"><span data-stu-id="e3db4-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e3db4-118">Windows PowerShell 및 **일반-CsDeviceUpdateLog** cmdlet을 사용 하 여 장치 업데이트 로그를 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="e3db4-119">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3db4-120">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3db4-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="e3db4-121">한 서버에서 장치 업데이트 로그를 지우려면</span><span class="sxs-lookup"><span data-stu-id="e3db4-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="e3db4-122">다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 장치 업데이트 로그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e3db4-123">10 일이 지난 모든 로그 항목 (DaysBack 매개 변수로 지정 된 값)이 로그에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="e3db4-124">모든 장치 업데이트 로그를 지우려면</span><span class="sxs-lookup"><span data-stu-id="e3db4-124">To clear all device update logs</span></span>

  - <span data-ttu-id="e3db4-125">이 명령은 조직에서 현재 사용 중인 모든 장치 업데이트 로그에서 오래 된 항목 (이 예에서 10 일이 지난 항목)을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3db4-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="e3db4-126">자세한 내용은 [일반-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3db4-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

