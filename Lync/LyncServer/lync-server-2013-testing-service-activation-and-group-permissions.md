---
title: 'Lync Server 2013: 서비스 활성화 및 그룹 권한 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef22928f9506c4ec67acd3de6bad80274f8c0f12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="fbb6c-102">Lync Server 2013에서 서비스 활성화 및 그룹 권한 테스트</span><span class="sxs-lookup"><span data-stu-id="fbb6c-102">Testing service activation and group permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbb6c-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="fbb6c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbb6c-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="fbb6c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fbb6c-105">Daily</span><span class="sxs-lookup"><span data-stu-id="fbb6c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbb6c-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="fbb6c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fbb6c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbb6c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbb6c-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="fbb6c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fbb6c-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fbb6c-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsTopology cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="fbb6c-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fbb6c-112">설명</span><span class="sxs-lookup"><span data-stu-id="fbb6c-112">Description</span></span>

<span data-ttu-id="fbb6c-113">CsTopology cmdlet을 사용 하 여 Lync Server 2013이 전역 범위에서 올바르게 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="fbb6c-114">기본적으로 cmdlet은 전체 Lync Server 인프라를 검사 하 여 필요한 서비스가 실행 되 고 있는지 확인 하 고 해당 서비스에 대 한 적절 한 사용 권한이 설정 되어 있으며 Lync Server를 설치할 때 생성 되는 유니버설 보안 그룹을 확인 합니다. .</span><span class="sxs-lookup"><span data-stu-id="fbb6c-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="fbb6c-115">Lync Server 설치의 유효성을 확인 하는 것 외에도 CsTopology 테스트를 통해 특정 서비스의 유효성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="fbb6c-116">예를 들어이 명령은 풀 atl-cs-001.litwareinc.com에서 A/V 회의 서버의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fbb6c-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="fbb6c-117">Running the test</span></span>

<span data-ttu-id="fbb6c-118">기본적으로 CsTopology 테스트는 화면에 매우 적은 출력을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="fbb6c-119">대신 cmdlet에서 반환 되는 정보가 HTML 파일에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="fbb6c-120">Report 매개 변수를 사용 하면 CsTopology에서 생성 되는 HTML 파일의 파일 경로와 파일 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="fbb6c-121">보고서 매개 변수를 포함 하지 않는 경우 HTML 파일은 사용자 폴더에 자동으로 저장 되 고 다음과 비슷한 이름이 지정 됩니다. ce84964a-c4da-4622-ad34-c54ff3ed36-1.html.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="fbb6c-122">다음 샘플 명령은 Test-CsTopology를 실행 하 고 출력을 C:\\로그\\컴퓨터에 있는 파일에 저장 합니다. html:</span><span class="sxs-lookup"><span data-stu-id="fbb6c-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="fbb6c-123">자세한 내용은 [테스트 CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fbb6c-124">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="fbb6c-124">Determining success or failure</span></span>

<span data-ttu-id="fbb6c-125">대부분의 테스트 cmdlet과 달리 테스트-CsTopology는 성공 또는 실패를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="fbb6c-126">그 이유는 많은 수의 확인 검사로 인해 cmdlet이 실행 될 때마다 수행 해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="fbb6c-127">대신 Internet Explorer를 사용 하 여 볼 수 있는 데이터를 HTML 보고서에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fbb6c-128">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="fbb6c-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="fbb6c-129">테스트 CsTopology가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="fbb6c-130">테스트 컴퓨터에서 복제가 최신 상태가 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="fbb6c-131">Get-CsManagementStoreReplicationStatus cmdlet을 실행 하 여 컴퓨터에 대 한 현재 복제 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="fbb6c-132">복제 상태를 최신 상태가 아닌 경우 다음과 같은 명령을 사용 하 여 복제를 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="fbb6c-133">토폴로지를 사용 하도록 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-133">The topology might have to be enabled.</span></span> <span data-ttu-id="fbb6c-134">Lync Server 토폴로지 (로컬 컴퓨터에 영향을 줄 수 있는 변경 내용)를 변경 하는 경우 새 토폴로지를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="fbb6c-135">다음 명령을 실행 하 여 언제 든 지 토폴로지를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb6c-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

