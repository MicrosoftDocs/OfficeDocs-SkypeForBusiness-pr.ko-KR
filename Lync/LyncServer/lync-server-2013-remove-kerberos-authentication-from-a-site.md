---
title: 'Lync Server 2013: 사이트에서 Kerberos 인증을 제거 합니다.'
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
ms.openlocfilehash: a4f7fa1160e7ff0afbbc4d8d4cc5ec96ab08e0f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="1fa7b-102">Lync Server 2013에서 사이트에서 Kerberos 인증 제거</span><span class="sxs-lookup"><span data-stu-id="1fa7b-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fa7b-103">_**마지막으로 수정 된 항목:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="1fa7b-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="1fa7b-104">이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="1fa7b-105">사이트에서 Kerberos 인증을 제거하거나 사이트를 폐기해야 하는 경우 **Remove-CsKerberosAccountAssignment** cmdlet을 사용하여 사이트에서 Kerberos 인증 계정 할당을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="1fa7b-106">다음 절차를 사용하여 Kerberos 인증 계정 할당을 제거하면 사이트의 모든 컴퓨터에서 할당이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="1fa7b-107">Kerberos 사용 가능 계정을 영구적으로 해제 하는 경우에는 할당을 제거한 후 Active Directory 사용자 및 컴퓨터를 사용 하 여 Active Directory 도메인 서비스에서이를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="1fa7b-108">나중에 개체를 사용하려는 경우 Active Directory 개체를 유지하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="1fa7b-109">사이트에서 Kerberos 인증을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="1fa7b-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="1fa7b-110">RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="1fa7b-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1fa7b-112">명령줄에서 다음의 두 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="1fa7b-113">예:</span><span class="sxs-lookup"><span data-stu-id="1fa7b-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1fa7b-114">계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server 관리 셸 명령 프롬프트에서 <STRONG>Enable-enable-cstopology</STRONG> 을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

