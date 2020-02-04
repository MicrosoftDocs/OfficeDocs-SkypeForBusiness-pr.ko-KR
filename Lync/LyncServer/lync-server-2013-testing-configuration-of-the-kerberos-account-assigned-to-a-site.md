---
title: 사이트에 할당 된 Kerberos 계정의 구성 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c096edc0267501bb17870a5c018e4b6b0c513422
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="5e925-102">Lync Server 2013에서 사이트에 할당 된 Kerberos 계정의 구성 테스트</span><span class="sxs-lookup"><span data-stu-id="5e925-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e925-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5e925-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e925-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="5e925-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5e925-105">Daily</span><span class="sxs-lookup"><span data-stu-id="5e925-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e925-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="5e925-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5e925-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e925-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e925-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="5e925-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5e925-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5e925-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsKerberosAccountAssignment cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="5e925-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5e925-112">설명</span><span class="sxs-lookup"><span data-stu-id="5e925-112">Description</span></span>

<span data-ttu-id="5e925-113">CsKerberosAccountAssignment cmdlet을 사용 하면 Kerberos 계정이 지정 된 사이트와 연결 되어 있고,이 계정이 올바르게 구성 되어 있으며, 계정이 예상 대로 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="5e925-114">Kerberos 계정은 IIS (인터넷 정보 서비스)를 실행 하는 사이트의 모든 컴퓨터에 대 한 인증 보안 주체의 역할을 할 수 있는 컴퓨터 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="5e925-115">이러한 계정은 Kerberos 인증 프로토콜을 사용 하므로 계정이 Kerberos 계정 이라고 하 고 새 인증 프로세스를 Kerberos 웹 인증 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="5e925-116">이렇게 하면 단일 계정을 사용 하 여 모든 IIS 서버를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="5e925-117">자세한 내용은 [테스트 CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e925-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5e925-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="5e925-118">Running the Test</span></span>

<span data-ttu-id="5e925-119">기본적으로 CsKerberosAccountAssignment 테스트는 화면에 매우 적은 출력을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="5e925-120">대신 cmdlet에서 반환 되는 정보가 HTML 파일에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="5e925-121">따라서 Test-CsKerberosAccountAssignment를 실행할 때마다 Verbose 매개 변수와 Report 매개 변수를 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="5e925-122">Verbose 매개 변수는 cmdlet이 실행 되는 동안 약간 더 자세한 출력을 화면에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="5e925-123">Report 매개 변수를 사용 하면 CsKerberosAccountAssignment에서 생성 되는 HTML 파일의 파일 경로와 파일 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="5e925-124">보고서 매개 변수를 포함 하지 않는 경우 HTML 파일은 사용자 폴더에 자동으로 저장 되 고 다음과 비슷한 이름이 지정 됩니다. ce84964a-c4da-4622-ad34-c54ff3ed36-1.html.</span><span class="sxs-lookup"><span data-stu-id="5e925-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="5e925-125">또한 테스트를 실행할 때 사이트 Id를 지정 CsKerberosAccountAssignment 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="5e925-126">사이트 범위에서 Kerberos 계정이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="5e925-127">다음 명령은 Test-CsKerberosAccountAssignment를 실행 하 고 출력을 C:\\Logs\\KerberosTest 라는 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="5e925-128">자세한 내용은 [테스트 CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e925-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5e925-129">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="5e925-129">Determining Success or Failure</span></span>

<span data-ttu-id="5e925-130">CsKerberosAccountAssignment cmdlet은 성공 또는 실패를 나타내는 간단한 표시를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="5e925-131">대신 Internet Explorer를 사용 하 여 생성 된 HTML 파일을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5e925-132">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="5e925-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="5e925-133">테스트 CsKerberosAccountAssignment가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="5e925-134">잘못 된 사이트 Id를 지정 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="5e925-135">유효한 사이트 Id 목록을 반환 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="5e925-136">사이트 Id는 일반적으로 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="5e925-137">사이트: Redmond</span><span class="sxs-lookup"><span data-stu-id="5e925-137">site:Redmond</span></span>

  - <span data-ttu-id="5e925-138">지정 된 사이트에 Kerberos 계정이 할당 되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="5e925-139">다음과 같은 명령을 실행 하 여 Kerberos 계정이 사이트에 할당 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="5e925-140">Kerberos 계정에 유효 하지 않은 암호가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="5e925-141">보고서에 다음과 같은 오류 메시지가 표시 되는 경우 Kerberos 계정 암호를 다시 설정 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="5e925-142">InvalidKerberosConfiguration: Kerberos 구성이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="5e925-143">InvalidKerberosConfiguration: atl-cs001.litwareinc.com의 Kerberos 구성이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="5e925-144">Litwareinc\\kerberostest에 지정 된 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="5e925-145">계정이 만료 되지 않았는지, 컴퓨터의 구성 된 암호가 계정의 Active Directory 암호와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="5e925-146">[Set-Cccercosaccountpassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet을 사용 하 여 암호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e925-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

