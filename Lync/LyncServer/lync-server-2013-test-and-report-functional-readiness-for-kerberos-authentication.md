---
title: Kerberos 인증에 대 한 기능 준비 상태 테스트 및 보고
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3c5a2c83d664182226decb88ab6bd1c34d6d3a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="f1943-102">Lync Server 2013에서 Kerberos 인증에 대 한 기능 준비 상태 테스트 및 보고</span><span class="sxs-lookup"><span data-stu-id="f1943-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1943-103">_**마지막으로 수정 된 항목:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="f1943-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="f1943-104">이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="f1943-105">**Get-cskerberosaccountassignment** Windows PowerShell cmdlet을 사용 하 여 Kerberos 인증에 대 한 사이트 할당의 기능 준비 상태를 테스트 하 고 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="f1943-106">이 명령은 필수 Identity 매개 변수에서 지정된 사이트를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="f1943-107">Optional Report 매개 변수를 지정 하면 cmdlet이 명령이 실행 되는 컴퓨터의\\C: 로그에 HTML 보고서를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="f1943-108">선택적 Verbose 매개 변수는 작업 정보를 화면에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="f1943-109">사이트에 대한 Kerberos 인증을 위해 기능 준비를 테스트 및 보고하려면</span><span class="sxs-lookup"><span data-stu-id="f1943-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="f1943-110">RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="f1943-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1943-112">명령줄에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="f1943-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1943-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

