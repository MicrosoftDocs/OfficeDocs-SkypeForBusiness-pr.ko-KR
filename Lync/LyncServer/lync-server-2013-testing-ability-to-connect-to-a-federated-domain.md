---
title: 'Lync Server 2013: 페더레이션 도메인에 연결 하는 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2176008e3e941068f61a2fb385fa6230df6b25dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="71637-102">Lync Server 2013에서 페더레이션 도메인에 연결 하는 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="71637-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71637-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="71637-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71637-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="71637-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="71637-105">Daily</span><span class="sxs-lookup"><span data-stu-id="71637-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71637-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="71637-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="71637-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71637-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71637-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="71637-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="71637-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="71637-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsFederatedPartner cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="71637-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="71637-112">설명</span><span class="sxs-lookup"><span data-stu-id="71637-112">Description</span></span>

<span data-ttu-id="71637-113">CsFederatedPartner는 페더레이션 파트너의 도메인에 연결 하는 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="71637-114">도메인에 대 한 연결을 확인 하려면 해당 도메인이 허용 (페더레이션된) 도메인 모음에 나열 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="71637-115">다음 명령을 사용 하 여 허용 된 도메인 목록에 있는 도메인 목록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="71637-116">자세한 내용은 [테스트 CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="71637-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="71637-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="71637-117">Running the test</span></span>

<span data-ttu-id="71637-118">FederatedPartner cmdlet에는 두 가지 정보, 즉 Edge 서버의 FQDN과 페더레이션 파트너의 FQDN이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="71637-119">예를 들어이 명령은 도메인 contoso.com에 연결 하는 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="71637-120">이 명령을 사용 하면 현재 허용 된 도메인 목록에 있는 모든 도메인에 대 한 연결을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="71637-121">자세한 내용은 [테스트 CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="71637-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="71637-122">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="71637-122">Determining success or failure</span></span>

<span data-ttu-id="71637-123">지정 된 도메인에 연결할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="71637-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="71637-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="71637-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="71637-125">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="71637-125">Result : Success</span></span>

<span data-ttu-id="71637-126">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="71637-126">Latency : 00:00:00</span></span>

<span data-ttu-id="71637-127">오류</span><span class="sxs-lookup"><span data-stu-id="71637-127">Error :</span></span>

<span data-ttu-id="71637-128">있게</span><span class="sxs-lookup"><span data-stu-id="71637-128">Diagnosis :</span></span>

<span data-ttu-id="71637-129">지정 된 도메인에 연결할 수 없는 경우에는 결과가 실패로 표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71637-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="71637-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="71637-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="71637-131">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="71637-131">Result : Failure</span></span>

<span data-ttu-id="71637-132">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="71637-132">Latency : 00:00:00</span></span>

<span data-ttu-id="71637-133">오류: 504, 서버 시간 초과</span><span class="sxs-lookup"><span data-stu-id="71637-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="71637-134">진단: ErrorCode = 2, 원본 = atl-cs-001. litwareinc, Reason = 참조</span><span class="sxs-lookup"><span data-stu-id="71637-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="71637-135">응답 코드 및 이유 구.</span><span class="sxs-lookup"><span data-stu-id="71637-135">response code and reason phrase.</span></span>

<span data-ttu-id="71637-136">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="71637-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="71637-137">예를 들어 이전 출력은 서버 시간 초과 오류로 인해 테스트가 실패 했다는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71637-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="71637-138">이는 일반적으로 네트워크 연결 문제나 Edge 서버에 연결 하는 데 문제가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71637-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="71637-139">테스트-CsFederatedPartner 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="71637-140">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="71637-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="71637-141">테스트 CsFederatedPartner가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="71637-142">Edge 서버를 사용할 수 없는 경우일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-142">The Edge Server might not be available.</span></span> <span data-ttu-id="71637-143">다음 명령을 사용 하 여 Edge 서버의 Fqdn을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="71637-144">그런 다음 각 Edge 서버에 ping을 수행 하 여 네트워크를 통해 액세스할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="71637-145">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="71637-146">지정 된 도메인이 허용 된 도메인 목록에 나열 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71637-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="71637-147">허용 되는 도메인 목록에 추가 된 도메인을 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="71637-148">사용자가 통신을 차단 하는 도메인 목록을 보려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71637-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

