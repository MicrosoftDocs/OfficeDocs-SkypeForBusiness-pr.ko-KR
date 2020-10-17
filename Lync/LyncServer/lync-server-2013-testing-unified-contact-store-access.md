---
title: 'Lync Server 2013: 통합 연락처 저장소 액세스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5552c03ac18ddd373385674da03d872ce89eb585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503905"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="3831a-102">Lync Server 2013에서 통합 연락처 저장소 액세스 테스트</span><span class="sxs-lookup"><span data-stu-id="3831a-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3831a-103">_**마지막으로 수정 된 항목:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="3831a-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3831a-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="3831a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3831a-105">매일</span><span class="sxs-lookup"><span data-stu-id="3831a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3831a-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="3831a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3831a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3831a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3831a-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="3831a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3831a-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3831a-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csunifiedcontactstore</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="3831a-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3831a-112">설명</span><span class="sxs-lookup"><span data-stu-id="3831a-112">Description</span></span>

<span data-ttu-id="3831a-113">Lync Server 2013에 도입 된 통합 연락처 저장소는 관리자에 게 Lync Server 대신 Microsoft Exchange Server 2013의 사용자 연락처를 저장 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="3831a-114">이를 통해 사용자는 Lync 2013 외에도 Outlook Web Access에서 동일한 연락처 집합에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="3831a-115">Lync Server 에서도 계속 연락처를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="3831a-116">이 경우 사용자는 Outlook 및 Outlook Web Access와 함께 사용 하기 위한 두 가지 연락처 집합, 그리고 Lync 2013와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="3831a-117">**Test-csunifiedcontactstore** cmdlet을 실행 하 여 사용자의 연락처가 통합 연락처 저장소로 이동 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="3831a-118">**Test-csunifiedcontactstore** cmdlet은 지정 된 사용자 계정을 사용 하 여 통합 연락처 저장소에 연결한 다음 사용자의 대화 상대를 검색 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="3831a-119">검색할 수 있는 연락처가 없는 경우에는 명령이 "사용자에 대 한 연락처를 받지 못했습니다." 라는 메시지와 함께 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="3831a-120">사용자의 대화 상대가 있는지 확인하세요."라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="3831a-121">사용자가 통합 연락처 저장소로 마이그레이션 되었지만 해당 대화 상대 목록에 연락처가 없는 경우 **test-csunifiedcontactstore** cmdlet은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="3831a-122">지정한 사용자에 게 **test-csunifiedcontactstore** cmdlet에 대 한 대화 상대가 하나 이상 있어야 성공적으로 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3831a-123">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="3831a-123">Running the test</span></span>

<span data-ttu-id="3831a-124">다음 예에 나와 있는 명령은 \\ 통합 연락처 저장소에서 user litwareinc kenmyer 연락처를 찾을 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="3831a-125">이 작업을 수행 하기 위해 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 litwareinc kenmyer에 대 한 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="3831a-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="3831a-126">유효한 자격 증명 개체를 만들려면이 계정의 암호를 입력 하 고 **test-csunifiedcontactstore** cmdlet이 검사를 실행할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="3831a-127">예제의 두 번째 명령은 제공 된 자격 증명 개체 ($x)와 사용자 litwareinc kenmyer의 SIP 주소를 사용 하 여 해당 \\ 연락처를 통합 연락처 저장소에서 찾을 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3831a-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="3831a-128">Determining success or failure</span></span>

<span data-ttu-id="3831a-129">연락처 저장소에 대 한 액세스 권한이 올바르게 구성 된 경우 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="3831a-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3831a-130">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3831a-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3831a-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="3831a-131">Result : Success</span></span>

<span data-ttu-id="3831a-132">대기 시간: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="3831a-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="3831a-133">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="3831a-133">Error Message :</span></span>

<span data-ttu-id="3831a-134">진단을</span><span class="sxs-lookup"><span data-stu-id="3831a-134">Diagnosis :</span></span>

<span data-ttu-id="3831a-135">연락처 저장소에 대 한 액세스를 올바르게 구성 하지 않으면 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3831a-136">경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="3831a-137">FQDN (도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="3831a-137">domain name (FQDN).</span></span> <span data-ttu-id="3831a-138">기본 등록자 포트 번호 사용</span><span class="sxs-lookup"><span data-stu-id="3831a-138">Using default Registrar port number.</span></span> <span data-ttu-id="3831a-139">오류</span><span class="sxs-lookup"><span data-stu-id="3831a-139">Exception:</span></span>

<span data-ttu-id="3831a-140">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="3831a-141">구독자</span><span class="sxs-lookup"><span data-stu-id="3831a-141">at</span></span>

<span data-ttu-id="3831a-142">SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="3831a-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="3831a-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="3831a-144">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3831a-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3831a-145">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="3831a-145">Result : Failure</span></span>

<span data-ttu-id="3831a-146">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3831a-146">Latency : 00:00:00</span></span>

<span data-ttu-id="3831a-147">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="3831a-148">일정 시간 후에 올바르게 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="3831a-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="3831a-149">연결 된 호스트에서 연결이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-149">established connection failed because connected host has</span></span>

<span data-ttu-id="3831a-150">10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="3831a-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3831a-151">내부 예외:</span><span class="sxs-lookup"><span data-stu-id="3831a-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="3831a-152">일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음</span><span class="sxs-lookup"><span data-stu-id="3831a-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="3831a-153">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="3831a-154">에서 10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="3831a-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3831a-155">진단을</span><span class="sxs-lookup"><span data-stu-id="3831a-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3831a-156">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="3831a-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="3831a-157">다음은 **test-csunifiedcontactstore에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="3831a-158">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3831a-159">사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3831a-160">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3831a-161">통합 연락처 저장소에 연결 하지 못했으며 사용자에 대 한 대화 상대를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="3831a-162">네트워크 연결 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3831a-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3831a-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3831a-163">See Also</span></span>


[<span data-ttu-id="3831a-164">새-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="3831a-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="3831a-165">설정-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="3831a-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

