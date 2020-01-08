---
title: 'Lync Server 2013: Lync Server 서비스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="3d449-102">Lync server 2013에서 Lync Server 서비스 테스트</span><span class="sxs-lookup"><span data-stu-id="3d449-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d449-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3d449-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d449-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="3d449-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3d449-105">Daily</span><span class="sxs-lookup"><span data-stu-id="3d449-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d449-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="3d449-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3d449-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d449-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d449-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="3d449-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3d449-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3d449-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트 CsComputer cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="3d449-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3d449-112">설명</span><span class="sxs-lookup"><span data-stu-id="3d449-112">Description</span></span>

<span data-ttu-id="3d449-113">테스트-CsComputer는 로컬 컴퓨터에서 실행 중인 모든 Lync Server 2013 서비스의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="3d449-114">(테스트 CsComputer는 로컬 에서만 실행할 수 있으며, Windows PowerShell의 원격 인스턴스에서는 실행할 수 없습니다.) 또한 cmdlet은 컴퓨터에서 적절 한 방화벽 포트가 열려 있는지 확인 하 고 Lync Server 2013을 설치할 때 만든 Active Directory 그룹이 해당 로컬 그룹에 추가 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="3d449-115">예를 들어 테스트-CsComputer는 Active Directory 그룹 RTCUniversalUserAdmins 관리자 그룹에 추가 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="3d449-116">자세한 내용은 [CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d449-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3d449-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="3d449-117">Running the test</span></span>

<span data-ttu-id="3d449-118">로컬 컴퓨터 에서만 테스트 CsComputer cmdlet을 실행할 수 있으며, Windows PowerShell의 원격 인스턴스에서는 테스트 CsComputer를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="3d449-119">기본적으로 테스트 CsComputer는 화면에 매우 적은 양의 출력을 표시 하며,이 경우 cmdlet에서 반환 되는 정보는 HTML 파일에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="3d449-120">이 때문에 테스트-CsComputer를 실행할 때마다 Verbose 매개 변수와 Report 매개 변수를 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="3d449-121">Verbose 매개 변수는 cmdlet이 실행 되는 동안 약간 더 자세한 출력을 화면에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="3d449-122">Report 매개 변수를 사용 하면 테스트-CsComputer에서 생성 된 HTML 파일의 파일 경로와 파일 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="3d449-123">보고서 매개 변수를 포함 하지 않는 경우 HTML 파일은 사용자 폴더에 자동으로 저장 되 고 다음과 비슷한 이름이 지정 됩니다. ce84964a-c4da-4622-ad34-c54ff3ed36-1.html.</span><span class="sxs-lookup"><span data-stu-id="3d449-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="3d449-124">다음 샘플 명령은 테스트 CsComputer를 실행 하 고 출력을 C:\\Logs\\computertest. l l l: 이라는 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="3d449-125">자세한 내용은 [CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d449-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3d449-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="3d449-126">Determining success or failure</span></span>

<span data-ttu-id="3d449-127">확인 검사의 수가 다르기 때문에 테스트-CsComputer가 간단한 **예, 테스트 성공** 또는 아니요를 다시 보고 하지 않으므로 **테스트가 실패**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="3d449-128">대신 Internet Explorer를 사용 하 여 각 테스트의 성공 또는 실패 여부를 확인 하 여 생성 된 HTML 파일을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3d449-129">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="3d449-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="3d449-130">테스트 CsComputer가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="3d449-131">테스트 컴퓨터를 Lync Server에서 사용할 수 있도록 설정 하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="3d449-132">이 문제는 컴퓨터의 Lync Server 서비스 또는 서버 역할이 변경 되었고 CsComputer cmdlet을 실행 하지 않은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="3d449-133">이 문제를 해결 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="3d449-134">테스트 컴퓨터에서 복제가 최신 상태가 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="3d449-135">Get-CsManagementStoreReplicationStatus cmdlet을 실행 하 여 컴퓨터에 대 한 현재 복제 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="3d449-136">복제 상태가 최신이 아닌 경우 다음과 같은 명령을 사용 하 여 복제를 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="3d449-137">토폴로지를 사용 하도록 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-137">The topology might have to be enabled.</span></span> <span data-ttu-id="3d449-138">Lync Server 토폴로지 (로컬 컴퓨터에 영향을 줄 수 있는 변경 내용)를 변경 하는 경우 새 토폴로지를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="3d449-139">다음 명령을 실행 하 여 언제 든 지 토폴로지를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d449-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

