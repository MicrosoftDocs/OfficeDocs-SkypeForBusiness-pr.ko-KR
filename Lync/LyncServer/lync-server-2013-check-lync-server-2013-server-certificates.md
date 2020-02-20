---
title: 'Lync Server 2013: Lync Server 2013 서버 인증서 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b874c83adb2a1ddb511d8c6980cb12f01e0ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="6fe12-102">Lync Server 2013 서버 인증서 확인</span><span class="sxs-lookup"><span data-stu-id="6fe12-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fe12-103">_**마지막으로 수정 된 항목:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="6fe12-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fe12-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="6fe12-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6fe12-105">월간</span><span class="sxs-lookup"><span data-stu-id="6fe12-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fe12-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="6fe12-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6fe12-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fe12-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fe12-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="6fe12-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6fe12-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6fe12-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Set-cscertificate cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="6fe12-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6fe12-112">설명</span><span class="sxs-lookup"><span data-stu-id="6fe12-112">Description</span></span>

<span data-ttu-id="6fe12-113">Set-cscertificate cmdlet을 사용 하면 각 Lync Server 인증서에 대 한 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="6fe12-114">인증서에는 기본 제공 만료 날짜가 있으므로 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="6fe12-115">예를 들어 개인적으로 발급 된 인증서는 일반적으로 12 개월 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="6fe12-116">Lync Server 인증서가 만료 되 면 해당 인증서를 갱신 하거나 대체할 때까지 해당 기능이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6fe12-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="6fe12-117">Running the test</span></span>

<span data-ttu-id="6fe12-118">각 Lync Server 인증서에 대 한 정보를 반환 하려면 다음 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="6fe12-119">만료 날짜를 기준으로 반품 인증서 정보를 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="6fe12-120">예를 들어이 명령은 반환 된 데이터를 만료 된 인증서 (이후에는 사용할 수 없음)로 제한 합니다. 2014:</span><span class="sxs-lookup"><span data-stu-id="6fe12-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="6fe12-121">자세한 내용은 Set-cscertificate cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fe12-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="6fe12-122">Test-cscertificateconfiguration cmdlet이 존재 하더라도 관리자에 게는 그다지 유용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="6fe12-123">대신이 cmdlet은 인증서 마법사에서 주로 사용 됩니다. 이 cmdlet은 작동 하지만 다음 출력 예제에 표시 된 것 처럼 반환 되는 정보는 최소 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="6fe12-124">지문 사용</span><span class="sxs-lookup"><span data-stu-id="6fe12-124">Thumbprint Use</span></span>

<span data-ttu-id="6fe12-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="6fe12-125">\---------- ---</span></span>

<span data-ttu-id="6fe12-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 기본값</span><span class="sxs-lookup"><span data-stu-id="6fe12-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="6fe12-127">출력 검토</span><span class="sxs-lookup"><span data-stu-id="6fe12-127">Reviewing the output</span></span>

<span data-ttu-id="6fe12-128">Set-cscertificate cmdlet은 각 Lync Server 인증서에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="6fe12-129">발급자: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="6fe12-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="6fe12-130">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="6fe12-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="6fe12-131">NotBefore: 오후 1/2/2014 12:49:37</span><span class="sxs-lookup"><span data-stu-id="6fe12-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="6fe12-132">일련 번호: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="6fe12-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="6fe12-133">제목: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6fe12-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="6fe12-134">AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="6fe12-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="6fe12-135">meet.fabrikam.com, admin.fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="6fe12-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="6fe12-136">지문: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="6fe12-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="6fe12-137">사용: 기본값</span><span class="sxs-lookup"><span data-stu-id="6fe12-137">Use : Default</span></span>

<span data-ttu-id="6fe12-138">일반적으로 Lync Server 인증서와 관련 된 주요 문제에는 인증서가 적용 되는 경우 (NotBefore) 또는 만료 되는 경우 (예: NotAfter)와 같은 날짜 및 시간이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="6fe12-139">이러한 날짜와 시간은 매우 중요 하기 때문에, 반환 된 데이터를 인증서 사용, 인증서 일련 번호, 인증서 만료 날짜 등의 정보로 제한할 수 있습니다. 그런 다음 모든 인증서를 신속 하 게 검토 하 고 만료 되는 경우를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="6fe12-140">해당 정보만 반환 하려면 다음과 같이 명령을 옵션과 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="6fe12-141">이 명령은 다음과 비슷한 데이터를 반환 하 고 만료 날짜 순서 대로 인증서를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="6fe12-142">다음 이후 번호 사이 사용</span><span class="sxs-lookup"><span data-stu-id="6fe12-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="6fe12-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="6fe12-143">\--- ------------ --------</span></span>

<span data-ttu-id="6fe12-144">기본값 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="6fe12-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="6fe12-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="6fe12-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="6fe12-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="6fe12-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="6fe12-147">인증서 문제가 있는 경우 인증서에 대해 구성 된 AlternativeNames를 검토 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="6fe12-148">언뜻 보면 이것이 문제가 되는 것 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="6fe12-149">기본적으로 콘솔 창의 크기에 따라 Set-cscertificate에서 모든 이름을 표시 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="6fe12-150">AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="6fe12-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="6fe12-151">meet.fabrikam.com, fabrika</span><span class="sxs-lookup"><span data-stu-id="6fe12-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="6fe12-152">인증서에 할당 된 대체 이름을 모두 보려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="6fe12-153">이를 통해 인증서의 모든 대체 이름을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="6fe12-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6fe12-154">sip.fabrikam.com</span></span>

<span data-ttu-id="6fe12-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6fe12-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="6fe12-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6fe12-156">meet.fabrikam.com</span></span>

<span data-ttu-id="6fe12-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6fe12-157">admin.fabrikam.com</span></span>

<span data-ttu-id="6fe12-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6fe12-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="6fe12-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6fe12-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fe12-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fe12-160">See Also</span></span>


[<span data-ttu-id="6fe12-161">Set-cscertificate</span><span class="sxs-lookup"><span data-stu-id="6fe12-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

