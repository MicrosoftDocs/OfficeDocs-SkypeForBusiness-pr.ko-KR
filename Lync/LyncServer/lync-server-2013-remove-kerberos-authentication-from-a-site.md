---
title: 'Lync Server 2013: 사이트에서 Kerberos 인증 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88f3de6f653354087d1abd0f7884ee09eda2f36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="47ede-102">Lync Server 2013의 사이트에서 Kerberos 인증 제거</span><span class="sxs-lookup"><span data-stu-id="47ede-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47ede-103">_**마지막으로 수정한 주제:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="47ede-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="47ede-104">이 절차를 성공적으로 완료 하려면 RTCUniversalServerAdmins 그룹의 구성원 인 사용자로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="47ede-105">사이트에서 Kerberos 인증을 제거 하거나 사이트를 중지 해야 하는 경우 **CsKerberosAccountAssignment** cmdlet을 사용 하 여 사이트에서 kerberos 인증 계정 할당을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="47ede-106">다음 절차를 사용 하 여 사이트의 모든 컴퓨터에서 할당을 제거 하는 Kerberos 인증 계정 할당을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="47ede-107">Kerberos 사용 계정을 영구적으로 사용 중지 하는 경우 할당을 제거한 후 active directory 사용자 및 컴퓨터에서 active directory 도메인 서비스를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="47ede-108">앞으로 개체를 사용 하려는 경우 Active Directory 개체를 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="47ede-109">사이트에서 Kerberos 인증을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="47ede-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="47ede-110">RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013를 실행 하는 도메인의 컴퓨터 또는 관리 도구가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="47ede-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="47ede-112">명령줄에서 다음 두 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="47ede-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="47ede-114">계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server Management Shell 명령 프롬프트에서 <STRONG>Enable-CsTopology</STRONG> 을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ede-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

