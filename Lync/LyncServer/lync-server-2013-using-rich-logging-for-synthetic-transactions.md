---
title: 'Lync Server 2013: 가상 트랜잭션에 대 한 리치 로깅을 사용 합니다.'
description: 'Lync Server 2013: 가상 트랜잭션에 대 한 리치 로깅을 사용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fd984386985bced64265ebedfd57c56a84a4443
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580304"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="d419a-103">Lync Server 2013에서 가상 트랜잭션에 대 한 리치 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="d419a-103">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d419a-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d419a-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d419a-105">Microsoft Lync Server 2010에서 도입 된 가상 트랜잭션은 관리자가 사용자가 시스템에 로그온 하거나, 인스턴트 메시지를 교환 하거나, PSTN (공중 전화망)에 있는 전화기를 호출 하는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-105">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d419a-106">Lync Server Windows PowerShell cmdlet 집합으로 패키지 된 이러한 테스트는 관리자가 수동으로 수행 하거나 System Center Operations Manager와 같은 응용 프로그램에서 자동으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-106">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="d419a-107">Lync Server 2010에서는 관리자가 시스템 문제를 파악 하는 데 도움이 되는 가상 트랜잭션이 입증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-107">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="d419a-108">예를 들어, **테스트-CsRegistration** cmdlet은 사용자가 Lync Server에 등록 하는 데 어려움을 겪고 있다는 사실을 관리자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-108">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="d419a-109">그러나 가상 트랜잭션은 관리자가 Lync Server에 등록 하는 데 어려움이 있는 이유를 확인 하는 데 도움이 되는 다소 덜 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-109">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="d419a-110">이는 가상 트랜잭션에서 관리자가 Lync Server의 문제를 해결 하는 데 도움이 되는 자세한 로깅 정보를 제공 하지 않았기 때문 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-110">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="d419a-111">가상 트랜잭션의 자세한 정보 출력에서 제공하는 단계별 정보를 통해 관리자가 문제 발생 위치를 어느 정도 근접하게 추측할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-111">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="d419a-112">Microsoft Lync Server 2013에서 가상 트랜잭션은 풍부한 로깅을 제공 하도록 다시 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-112">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="d419a-113">"향상된 로깅"이란 가상 트랜잭션이 수행하는 각 활동에 대해 다음과 같은 정보가 기록된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-113">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="d419a-114">활동이 시작된 시간</span><span class="sxs-lookup"><span data-stu-id="d419a-114">The time that the activity started</span></span>

  - <span data-ttu-id="d419a-115">활동이 완료된 시간</span><span class="sxs-lookup"><span data-stu-id="d419a-115">The time that the activity finished</span></span>

  - <span data-ttu-id="d419a-116">수행 된 작업 (예: 회의 만들기, 참가, 탈퇴, Lync Server에 로그인, 인스턴트 메시지 보내기 등)</span><span class="sxs-lookup"><span data-stu-id="d419a-116">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="d419a-117">활동 실행 시 생성된 정보, 자세한 정보, 경고 또는 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="d419a-117">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="d419a-118">SIP 등록 메시지</span><span class="sxs-lookup"><span data-stu-id="d419a-118">SIP registration messages</span></span>

  - <span data-ttu-id="d419a-119">활동 실행 시 생성된 예외 레코드 또는 진단 코드</span><span class="sxs-lookup"><span data-stu-id="d419a-119">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="d419a-120">활동 실행의 순수 결과</span><span class="sxs-lookup"><span data-stu-id="d419a-120">The net result of running the activity</span></span>

<span data-ttu-id="d419a-121">이 정보는 가상 트랜잭션을 실행할 때마다 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-121">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="d419a-122">그러나 정보가 자동으로 표시되거나 로그 파일에 저장되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-122">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="d419a-123">대신, 가상 트랜잭션을 수동으로 실행 하는 관리자는 OutLoggerVariable 매개 변수를 사용 하 여 정보가 저장 될 Windows PowerShell 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-123">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="d419a-124">그러면 관리자는 두 가지 방법을 통해 향상된 로그를 XML 또는 HTML 형식으로 저장 및/또는 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-124">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="d419a-125">예를 들어 Lync Server 2010 관리자는 다음과 같은 명령을 사용 하 여 **테스트 CsRegistration** cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-125">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="d419a-126">관리자는 OutLoggerVariable 매개 변수 뒤에 선택한 변수 이름을 붙여 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-126">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="d419a-p105">변수 이름 앞에 $ 문자를 붙이지 마십시오. 즉, $RegistrationTest가 아닌 RegistrationTest를 변수 이름으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="d419a-129">위의 명령은 다음과 같은 콘텐츠를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-129">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="d419a-p106">그러나 이 오류에 대해 위에 나와 있는 오류 메시지뿐만 아니라 훨씬 자세한 정보를 확인할 수 있습니다. HTML 형식의 해당 정보에 액세스하려면 다음과 같은 명령을 사용하여 RegistrationTest 변수에 저장된 정보를 HTML 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="d419a-132">또는 ToXML() 메서드를 사용하여 데이터를 XML 파일에 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-132">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="d419a-133">이러한 파일은 Internet Explorer, Visual Studio 또는 HTML/XML 파일을 열 수 있는 다른 응용 프로그램을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-133">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="d419a-134">System Center Operations Manager 내부에서 실행 되는 가상 트랜잭션은 오류에 대 한 이러한 로그 파일을 자동으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-134">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="d419a-135">그러나 Windows PowerShell에서 가상 트랜잭션을 로드 하 고 실행할 수 있으려면 실행이 실패 하는 경우에는 이러한 로그가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-135">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="d419a-136">기본적으로 Lync Server 2013에서는 공유 되지 않는 폴더에 로그 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d419a-136">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="d419a-137">이러한 로그에 쉽게 액세스할 수 있도록 하려면이 폴더를 공유 해야 합니다 (예: \\ \\ litwareinc com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="d419a-137">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

