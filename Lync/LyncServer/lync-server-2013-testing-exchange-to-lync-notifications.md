---
title: 'Lync Server 2013: Exchange를 Lync 알림으로 테스트'
description: 'Lync Server 2013: Exchange를 Lync 알림으로 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdf453bfdaab7e7b6bdaae8b67ac7759c0d55af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560624"
---
# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="208ef-103">Lync Server 2013에서 Lync 알림 Exchange 테스트</span><span class="sxs-lookup"><span data-stu-id="208ef-103">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="208ef-104">_**마지막으로 수정 된 항목:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="208ef-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="208ef-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="208ef-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="208ef-106">매일</span><span class="sxs-lookup"><span data-stu-id="208ef-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="208ef-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="208ef-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="208ef-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="208ef-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="208ef-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="208ef-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="208ef-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="208ef-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csexstoragenotification</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="208ef-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="208ef-113">설명</span><span class="sxs-lookup"><span data-stu-id="208ef-113">Description</span></span>

<span data-ttu-id="208ef-114">**Test-csexstoragenotification** Cmdlet은 Microsoft Exchange Server 2013 알림 서비스가 사용자의 대화 상대 목록에 업데이트를 적용할 때마다 Lync Server 2013에 알릴 수 있는지를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-114">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="208ef-115">이 cmdlet은 통합 연락처 저장소를 사용 중인 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-115">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="208ef-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="208ef-116">Running the test</span></span>

<span data-ttu-id="208ef-117">예제 1에 표시 된 명령은 Lync Server 저장소 서비스가 사용자 sip:kenmyer@litwareinc.com에 대해 Microsoft Exchange Server 사서함 알림 서비스에 연결할 수 있는지 여부를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-117">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="208ef-118">이 예제에서는 NetNamedPipe가 WCF 바인딩으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-118">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="208ef-119">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="208ef-119">Determining success or failure</span></span>

<span data-ttu-id="208ef-120">Exchange 통합이 올바르게 구성 된 경우 결과 속성이 **Success**로 표시 된 것과 비슷한 출력을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-120">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="208ef-121">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="208ef-121">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="208ef-122">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="208ef-122">Result : Success</span></span>

<span data-ttu-id="208ef-123">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="208ef-123">Latency : 00:00:00</span></span>

<span data-ttu-id="208ef-124">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="208ef-124">Error Message :</span></span>

<span data-ttu-id="208ef-125">진단을</span><span class="sxs-lookup"><span data-stu-id="208ef-125">Diagnosis :</span></span>

<span data-ttu-id="208ef-126">지정 된 사용자가 알림을 받을 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-126">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="208ef-127">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="208ef-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="208ef-128">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="208ef-128">Result : Failure</span></span>

<span data-ttu-id="208ef-129">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="208ef-129">Latency : 00:00:00</span></span>

<span data-ttu-id="208ef-130">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-130">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="208ef-131">일정 시간 후에 올바르게 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="208ef-131">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="208ef-132">연결 된 호스트에서 연결이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-132">established connection failed because connected host has</span></span>

<span data-ttu-id="208ef-133">10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="208ef-133">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="208ef-134">내부 예외:</span><span class="sxs-lookup"><span data-stu-id="208ef-134">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="208ef-135">일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음</span><span class="sxs-lookup"><span data-stu-id="208ef-135">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="208ef-136">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-136">time, or established connection failed because connected host</span></span>

<span data-ttu-id="208ef-137">에서 10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="208ef-137">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="208ef-138">진단을</span><span class="sxs-lookup"><span data-stu-id="208ef-138">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="208ef-139">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="208ef-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="208ef-140">다음은 **test-csexstoragenotification에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-140">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="208ef-141">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-141">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="208ef-142">사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-142">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="208ef-143">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-143">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="208ef-144">Microsoft Exchange Server가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="208ef-144">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="208ef-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="208ef-145">See Also</span></span>


[<span data-ttu-id="208ef-146">Test-csexstorageconnectivity</span><span class="sxs-lookup"><span data-stu-id="208ef-146">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

