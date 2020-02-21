---
title: 'Lync Server 2013: Kerberos 계정 할당 보고'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f44f187b751ec9baa78df8890e64332070d8b33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="16697-102">Lync Server 2013에서 Kerberos 계정 할당 보고</span><span class="sxs-lookup"><span data-stu-id="16697-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16697-103">_**마지막으로 수정 된 항목:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="16697-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="16697-104">이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16697-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="16697-105">**Get-CsKerberosAccountAssignment** cmdlet을 사용하여 Kerberos 인증 계정 지정에 대한 정보를 쿼리하고 배포의 현재 지정에 대한 정보를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16697-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="16697-106">사이트에 대한 Kerberos 인증 계정 지정을 쿼리하려면</span><span class="sxs-lookup"><span data-stu-id="16697-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="16697-107">RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="16697-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="16697-108">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="16697-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="16697-109">명령줄에서 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16697-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="16697-110">조직의 모든 Kerberos 인증 계정 지정을 쿼리하고 각 계정에 대한 지정 정보를 반환하려면 매개 변수 없이 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16697-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="16697-111">배포의 모든 Kerberos 인증 계정 지정을 쿼리하고 각 계정에 대한 사이트 지정 정보를 반환하려면 ID 매개 변수를 사용하여 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16697-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="16697-112">예:</span><span class="sxs-lookup"><span data-stu-id="16697-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="16697-113">단일 사이트의 모든 Kerberos 인증 계정 지정을 쿼리하고 각 계정에 대한 지정 정보를 반환하려면 필터 매개 변수를 사용하여 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16697-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="16697-114">예:</span><span class="sxs-lookup"><span data-stu-id="16697-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="16697-115">필터 매개 변수에 대해 \*SiteName을 지정하면 사이트 식별자에서 임의의 위치에 지정한 사이트 이름이 포함된 모든 사이트(예: 사이트 식별자에 Redmond 문자열이 포함된 모든 사이트)에 대한 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="16697-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

