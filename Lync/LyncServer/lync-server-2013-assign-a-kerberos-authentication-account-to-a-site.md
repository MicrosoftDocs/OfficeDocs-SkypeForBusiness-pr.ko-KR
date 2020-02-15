---
title: 'Lync Server 2013: 사이트에 Kerberos 인증 계정 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf69e71dd66337551557bddd3bfb7700257a7f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="7bd68-102">Lync Server 2013에서 사이트에 Kerberos 인증 계정 할당</span><span class="sxs-lookup"><span data-stu-id="7bd68-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bd68-103">_**마지막으로 수정 된 항목:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="7bd68-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="7bd68-104">이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="7bd68-105">Kerberos 계정을 만든 후 이를 사이트에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="7bd68-106">Active Directory 사이트가 아니라 Lync Server 2013 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="7bd68-107">배포별로 여러 개의 Kerberos 인증 계정을 만들 수 있지만 사이트에는 계정을 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="7bd68-108">다음 절차에 따라 이전에 만든 Kerberos 인증 계정을 사이트에 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bd68-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="7bd68-109">Kerberos 계정을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 kerberos 인증 계정 만들기](lync-server-2013-create-a-kerberos-authentication-account.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bd68-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="7bd68-110">Kerberos 인증 계정을 사이트에 지정하려면</span><span class="sxs-lookup"><span data-stu-id="7bd68-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="7bd68-111">RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="7bd68-112">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7bd68-113">명령줄에서 다음의 두 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="7bd68-114">예:</span><span class="sxs-lookup"><span data-stu-id="7bd68-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="7bd68-p102">도메인\사용자 형식을 사용하여 UserAccount 매개 변수를 지정해야 합니다. User@Domain.extension 형식은 Kerberos 인증 용도로 만든 컴퓨터 개체를 나타내는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="7bd68-117">**선택**: [Lync Server 2013에서 웹 서비스 URL을 변경 하는](lync-server-2013-change-the-web-services-url.md)경우 WebServices에 대 한 재정의 FQDN (정규화 된 도메인 이름)을 구성 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="7bd68-118">이러한 경우에는이 FQDN에 대 한 SPN도 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="7bd68-119">예를 들어 FQDN이 webservices 인 경우 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7bd68-120">계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server 관리 셸 명령 프롬프트에서 <STRONG>Enable-enable-cstopology</STRONG> 을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd68-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

