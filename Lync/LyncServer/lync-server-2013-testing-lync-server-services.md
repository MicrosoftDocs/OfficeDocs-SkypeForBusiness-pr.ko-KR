---
title: 'Lync Server 2013: Lync Server 서비스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74a24818094d7de0edc4627f987464df048315f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519015"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="313ec-102">Lync Server 2013에서 Lync Server 서비스 테스트</span><span class="sxs-lookup"><span data-stu-id="313ec-102">Testing Lync Server services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="313ec-103">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="313ec-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="313ec-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="313ec-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="313ec-105">매일</span><span class="sxs-lookup"><span data-stu-id="313ec-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="313ec-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="313ec-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="313ec-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="313ec-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="313ec-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="313ec-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="313ec-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="313ec-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsComputer cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="313ec-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="313ec-112">설명</span><span class="sxs-lookup"><span data-stu-id="313ec-112">Description</span></span>

<span data-ttu-id="313ec-113">Test-CsComputer에서는 로컬 컴퓨터에서 실행 중인 모든 Lync Server 2013 서비스의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="313ec-114">(테스트 CsComputer는 로컬로만 실행할 수 있으며 Windows PowerShell의 원격 인스턴스에서는 실행할 수 없습니다.) 또한이 cmdlet은 컴퓨터에서 적절 한 방화벽 포트가 열려 있는지 여부를 확인 하 고, Lync Server 2013을 설치할 때 만든 Active Directory 그룹을 해당 로컬 그룹에 추가할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="313ec-115">예를 들어 Test-CsComputer에서는 Active Directory 그룹 RTCUniversalUserAdmins이 Administrators 그룹에 추가 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="313ec-116">자세한 내용은 [CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="313ec-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="313ec-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="313ec-117">Running the test</span></span>

<span data-ttu-id="313ec-118">Test-CsComputer cmdlet은 로컬 컴퓨터 에서만 실행할 수 있으며, Windows PowerShell의 원격 인스턴스에서는 Test-CsComputer를 호출 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="313ec-119">기본적으로 Test-CsComputer는 화면에 출력을 거의 표시 하지 않고, cmdlet에서 반환 되는 정보는 HTML 파일에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="313ec-120">따라서 테스트-CsComputer를 실행할 때마다 Verbose 매개 변수와 Report 매개 변수를 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="313ec-121">Verbose 매개 변수는 cmdlet이 실행 되는 동안 약간 더 자세한 출력을 화면에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="313ec-122">Report 매개 변수를 사용 하면 테스트-CsComputer에서 생성 되는 HTML 파일의 파일 경로와 파일 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="313ec-123">Report 매개 변수를 포함 하지 않으면 HTML 파일이 사용자 폴더에 자동으로 저장 되 고 ce84964a-c4da-4622-ad34-c54ff3ed361f.html과 같은 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="313ec-124">다음 예제 명령은 Test-CsComputer를 실행 하 고 출력을 C: \\ LogsComputerTest.html 이라는 파일에 저장 합니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="313ec-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="313ec-125">자세한 내용은 [CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="313ec-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="313ec-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="313ec-126">Determining success or failure</span></span>

<span data-ttu-id="313ec-127">확인이 수행 하는 검사의 수가 많기 때문에 Test-CsComputer 간단한 **예, 테스트 성공** 또는 아니요를 다시 보고 하지 않으므로 **테스트가 실패**합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="313ec-128">대신 Internet Explorer를 사용 하 여 각 테스트의 성공 또는 실패를 확인 하는 방법으로 생성 된 HTML 파일을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="313ec-129">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="313ec-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="313ec-130">Test-CsComputer 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="313ec-131">테스트 컴퓨터를 Lync Server에서 사용 하도록 설정 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="313ec-132">컴퓨터에서 Lync Server 서비스 또는 서버 역할이 변경 되 고 Enable-CsComputer cmdlet이 실행 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="313ec-133">이 문제를 해결하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="313ec-134">테스트 컴퓨터에서 복제가 최신 상태로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="313ec-135">Get-CsManagementStoreReplicationStatus cmdlet을 실행 하 여 컴퓨터의 현재 복제 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="313ec-136">복제 상태가 최신이 아니면 다음과 같은 명령을 사용 하 여 수동으로 복제를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="313ec-137">토폴로지를 사용 하도록 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-137">The topology might have to be enabled.</span></span> <span data-ttu-id="313ec-138">Lync Server 토폴로지를 변경 하는 경우 (로컬 컴퓨터에 영향을 줄 수 있는 변경 내용) 새 토폴로지를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="313ec-139">다음 명령을 실행 하 여 언제 든 지 토폴로지를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313ec-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

