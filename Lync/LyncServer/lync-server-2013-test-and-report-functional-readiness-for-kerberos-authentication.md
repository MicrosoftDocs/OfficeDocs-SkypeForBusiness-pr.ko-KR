---
title: Kerberos 인증에 대한 기능 준비 상태 테스트 및 보고
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
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="105a8-102">Lync Server 2013에서 Kerberos 인증에 대한 기능 준비 상태 테스트 및 보고</span><span class="sxs-lookup"><span data-stu-id="105a8-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="105a8-103">_**마지막으로 수정한 주제:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="105a8-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="105a8-104">이 절차를 성공적으로 완료 하려면 RTCUniversalServerAdmins 그룹의 구성원 인 사용자로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="105a8-105">**CsKerberosAccountAssignment** Windows PowerShell cmdlet을 사용 하 여 Kerberos 인증에 대 한 사이트 할당의 기능적 준비 상태를 테스트 하 고 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="105a8-106">이 명령은 필수 Id 매개 변수에 지정 된 사이트를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="105a8-107">선택적 보고서 매개 변수는 명령이 실행 되는 컴퓨터의 C:\\로그에 HTML 보고서를 작성 하도록 cmdlet에 게 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="105a8-108">선택 사항인 Verbose 매개 변수는 화면에 활동 정보를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="105a8-109">사이트의 Kerberos 인증에 대 한 기능 준비를 테스트 하 고 보고 하려면</span><span class="sxs-lookup"><span data-stu-id="105a8-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="105a8-110">RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013를 실행 하는 도메인의 컴퓨터 또는 관리 도구가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="105a8-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="105a8-112">명령줄에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="105a8-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="105a8-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

