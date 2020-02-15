---
title: 'Lync Server 2013: 감시자 노드 구성 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d0fe8500bd676ef1a9a33c9197dfeac7783c10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="c241f-102">Lync Server 2013에서 감시자 노드 구성 테스트</span><span class="sxs-lookup"><span data-stu-id="c241f-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c241f-103">_**마지막으로 수정 된 항목:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c241f-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c241f-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="c241f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c241f-105">매일</span><span class="sxs-lookup"><span data-stu-id="c241f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c241f-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="c241f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c241f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c241f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c241f-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="c241f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c241f-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c241f-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>get-cswatchernodeconfiguration</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="c241f-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c241f-112">설명</span><span class="sxs-lookup"><span data-stu-id="c241f-112">Description</span></span>

<span data-ttu-id="c241f-113">Microsoft System Center Operations Manager를 사용 하 여 Lync Server 2013을 모니터링 하는 경우 "감시자 노드"를 설정 하는 옵션을 사용할 수 있습니다 (주기적으로, 자동으로 실행 되는 컴퓨터). 하지만.</span><span class="sxs-lookup"><span data-stu-id="c241f-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="c241f-114">감시자 노드는 풀에 할당 되며 **get-cswatchernodeconfiguration** cmdlet을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="c241f-115">System Center Operations Manager를 사용 중이라면 감시자 노드를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="c241f-116">감시자 노드를 사용 하지 않고도 시스템을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="c241f-117">유일한 차이점은 실행 하려는 가상 트랜잭션은 Operations Manager에서 자동으로 호출 하지 않고 수동으로 호출 해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="c241f-118">**Get-cswatchernodeconfiguration** cmdlet을 사용 하면 감시자 노드가 올바르게 구성 되어 있고 유효한 Lync Server 2013 풀에 할당 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="c241f-119">**Get-cswatchernodeconfiguration** cmdlet은 감시자 노드 자체에서 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="c241f-120">원격 컴퓨터에 대해 cmdlet을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c241f-121">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="c241f-121">Running the test</span></span>

<span data-ttu-id="c241f-122">다음 명령은 조직에서 사용 중인 각 감시자 노드에 대 한 구성 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c241f-123">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="c241f-123">Determining success or failure</span></span>

<span data-ttu-id="c241f-124">다음과 같은 성공적인 샘플 출력에서는에 지 서버가 4 대 인 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="c241f-125">토폴로지에 대해 대상 풀 atl-cs-001.litwareinc.com 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c241f-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="c241f-126">성공: 대상 풀 atl-cs-001.litwareinc.com가 토폴로지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="c241f-127">성공: 대상 풀 atl-cs-001.litwareinc.com에 등록자 역할이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="c241f-128">성공: 대상 풀 atl-cs-001.litwareinc.com가 지원 되는 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="c241f-129">성공: 5061 대상 풀 atl-cs-001.litwareinc.com의 포트 번호가 올바릅니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="c241f-130">감시자 노드 구성에서 누락 된 풀에 대 한 검사가 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="c241f-131">검색 된 오류가 있으면 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c241f-132">감시자 노드 구성에서 누락 된 풀에 대 한 확인이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="c241f-133">감시자 노드 설치에서 만든 감시자 노드 레지스트리 키에 대 한 확인이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="c241f-134">검색 된 오류가 있으면 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c241f-135">감시자 노드 설치에서 만든 감시자 노드 레지스트리 키에 대 한 확인이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="c241f-136">인증 유형이 협상 됨을 감지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="c241f-137">테스트 사용자의 자격 증명 sip: user1@ atl-cs-001.litwareinc.com이 자격 증명 관리 저장소에 있는지 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="c241f-138">테스트 사용자의 자격 증명 sip: user2@ atl-cs-001.litwareinc.com이 자격 증명 관리 저장소에 있는지 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="c241f-139">감시자 노드 구성에서 누락 된 풀에 대 한 검사가 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="c241f-140">검색 된 오류가 있으면 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c241f-141">경고: atl-cs-001.litwareinc.com의 풀에 등록 자가 있음</span><span class="sxs-lookup"><span data-stu-id="c241f-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="c241f-142">역할이 설치 되었지만 해당 역할에 대해 구성 된 테스트 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="c241f-143">감시자 노드 구성에서 누락 된 풀에 대 한 확인이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="c241f-144">감시자 노드 설치에서 만든 감시자 노드 레지스트리 키에 대 한 확인은</span><span class="sxs-lookup"><span data-stu-id="c241f-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="c241f-145">먼저.</span><span class="sxs-lookup"><span data-stu-id="c241f-145">started.</span></span> <span data-ttu-id="c241f-146">검색 된 오류가 있으면 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c241f-147">Get-cswatchernodeconfiguration:에서 Health 레지스트리 키를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="c241f-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="c241f-148">소프트웨어\\Microsoft\\실시간 통신</span><span class="sxs-lookup"><span data-stu-id="c241f-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="c241f-149">감시자 노드가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c241f-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="c241f-150">올바르게 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c241f-151">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="c241f-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="c241f-152">다음은 **get-cswatchernodeconfiguration에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="c241f-153">감시자 노드가 올바르게 설치 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="c241f-154">구성 된 테스트 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c241f-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c241f-155">See Also</span></span>


[<span data-ttu-id="c241f-156">Get-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="c241f-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="c241f-157">Get-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="c241f-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="c241f-158">Get-cswatchernodeconfiguration을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c241f-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="c241f-159">Get-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="c241f-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

