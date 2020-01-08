---
title: 'Lync Server 2013: 중앙 로깅 서비스에서 캡처 로그 읽기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="378ca-102">Lync Server 2013의 중앙 로깅 서비스에서 캡처 로그 읽기</span><span class="sxs-lookup"><span data-stu-id="378ca-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="378ca-103">_**마지막으로 수정한 주제:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="378ca-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="378ca-104">검색을 실행 한 후 보고 된 문제를 추적 하는 데 사용할 수 있는 파일을가지고 있는 경우 중앙 로깅 서비스의 실질적인 이점을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="378ca-105">파일을 읽을 수 있는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="378ca-106">출력 파일은 표준 텍스트 형식으로 되어 있으며, Notepad.exe 또는 텍스트 파일을 열고 읽는 데 사용할 수 있는 다른 프로그램을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="378ca-107">대용량 파일과 복잡 한 문제가 발생 하는 경우 중앙 로깅 서비스에서 로깅 출력을 읽고 구문 분석 하도록 디자인 된 Snooper 같은 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="378ca-108">Snooper는 별도의 다운로드로 제공 되는 Lync Server 2013 디버그 도구에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="378ca-109">다음과 같은 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)Lync Server 2013 디버그 도구를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="378ca-110">Lync Server 2013 디버그 도구를 설치 하면 짧은 잘라내기 및 메뉴 항목이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="378ca-111">Lync Server 2013 디버그 도구를 설치한 후 Windows 탐색기, 명령줄 창 또는 Lync Server Management Shell을 열고 디렉터리로 이동 합니다 (기본 위치) C:\\프로그램 파일\\Microsoft Lync Server 2013\\디버깅 도구.</span><span class="sxs-lookup"><span data-stu-id="378ca-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="378ca-112">Snooper를 두 번 클릭 하거나 Snooper를 입력 하 고 명령줄 또는 Lync Server 관리 셸을 사용 하는 경우 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="378ca-113">이 항목의 목적은 문제 해결 기법을 자세히 설명 하 고 논의 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="378ca-114">문제 해결 및 관련 프로세스는 복잡 한 주제입니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="378ca-115">해결 방법에 대 한 자세한 내용과 특정 작업 부하 문제 해결에 대 한 자세한 내용은의 <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Microsoft Lync Server 2010 Resource Kit 책을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="378ca-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="378ca-116">프로세스와 절차는 여전히 Lync Server 2013에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="378ca-117">Lync Server 2013는 몇 가지 새로운 기능을 포함 하는 업데이트 된 버전의 Snooper을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="378ca-118">다음 스크린샷은 Office Communications Server 2007의 Snooper 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="378ca-119">![Snooper의 Office 통신 2007 버전.] (images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Snooper의 Office 통신 2007 버전.")</span><span class="sxs-lookup"><span data-stu-id="378ca-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="378ca-120">다음 스크린샷은 Lync Server 2013 디버그 도구에 포함 된 새 버전의 Snooper를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="378ca-121">![Lync Server 2013 버전의 Snooper.] (images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 버전의 Snooper.")</span><span class="sxs-lookup"><span data-stu-id="378ca-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="378ca-122">다음 스크린샷은 자주 사용 하는 함수가 있는 도구 모음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="378ca-123">![Snooper 2013 도구 모음] (images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 도구 모음")</span><span class="sxs-lookup"><span data-stu-id="378ca-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="378ca-124">값을 추가 하는 최신 기능은 흐름 차트 (호출 흐름) 다이어그램 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="378ca-125">**메시지** 탭에서 메시지 흐름을 선택 하 고 **호출 흐름** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="378ca-126">메시지를 진행할 때 통화 흐름 다이어그램이 새 데이터로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="378ca-127">![Snooper 2013 호출 흐름 다이어그램.] (images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 호출 흐름 다이어그램.")</span><span class="sxs-lookup"><span data-stu-id="378ca-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="378ca-128">다이어그램 보기를 마우스로 가리키고 흐름 및 메시지의 메시지와 내용, 서버 요소에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="378ca-129">통화 흐름 화살표를 클릭 하 여 메시지 보기의 메시지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="378ca-130">![통화 흐름 다이어그램 메시지 세부 정보입니다.] (images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "통화 흐름 다이어그램 메시지 세부 정보입니다.")</span><span class="sxs-lookup"><span data-stu-id="378ca-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="378ca-131">Snooper에서 로그 파일을 열려면</span><span class="sxs-lookup"><span data-stu-id="378ca-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="378ca-132">Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-132">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="378ca-133">Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-133">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="378ca-134">Lync Server 디버깅 도구 (LSnooper Cdebugtools)를 설치한 후에 Windows 탐색기 또는 명령줄에서 디렉터리를의 위치로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="378ca-135">기본적으로 디버깅 도구는 C:\\프로그램 파일\\Microsoft Lync Server 2013\\디버깅 도구에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="378ca-136">Snooper를 두 번 클릭 하거나 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="378ca-137">Snooper가 열리면 **파일**을 마우스 오른쪽 단추로 클릭 하 고 **OpenFile**을 클릭 하 고 로그 파일을 찾은 다음 **열기** 대화 상자에서 파일을 선택 하 고 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="378ca-138">**추적** 탭에 로그 파일의 **추적** 메시지가 표시 됩니다. 수집 된 추적의 메시지 내용을 보려면 **메시지** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="378ca-139">통화 흐름 다이어그램을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="378ca-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="378ca-140">Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-140">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="378ca-141">Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-141">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="378ca-142">로그 파일을 열고 **메시지** 탭을 클릭 하 고 메시지 보기에서 대화를 선택 하거나 **추적** 탭에서 추적 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="378ca-143">**통화 흐름**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="378ca-144">호출 흐름의 일부가 아닌 메시지 또는 추적을 클릭 하면 다이어그램이 나타나지 않으며 "이 메시지는 callSnooper에 적합 하지 않습니다." 라는 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-144">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="378ca-145">다른 메시지 또는 추적을 선택 하면 메시지 또는 추적이 호출 흐름의 일부인 경우 호출 흐름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-145">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="378ca-146">메시지 또는 추적 선을 이동 하 고 새 다이어그램을 표시 하기 위해 호출 흐름 다이어그램이 업데이트 또는 변경 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="378ca-147">요소 위에 커서를 올리면 호출 메시지, 끝점 및 기타 구성 요소에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ca-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

