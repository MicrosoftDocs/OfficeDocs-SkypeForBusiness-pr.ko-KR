---
title: Exchange 2013 Outlook Web App 및 IM 통합 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a67dd3c18525d7a39678b5871d087ea79c502fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="4b99e-102">Exchange 2013 Outlook Web App 및 IM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="4b99e-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b99e-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4b99e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4b99e-104">Lync Server 2013과의 Exchange 2013 OWA (Outlook Web Access) 및 IM (인스턴트 메시징) 통합을 사용 하도록 설정 하려면 2013 Exchange 클라이언트 액세스 서버 (CAS) 서버를 Lync Server 2013 topology에 트러스트 된 응용 프로그램 서버로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="4b99e-105">트러스트된 응용 프로그램 풀을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4b99e-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="4b99e-106">Lync Server 2013 관리 셸을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="4b99e-107">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="4b99e-108">그러면 풀을 만들려는 siteName의 siteID가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="4b99e-109">자세한 내용은 Lync Server 2013 관리 셸 설명서의 [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b99e-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="4b99e-110">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="4b99e-111">자세한 내용은 Lync Server 2013 관리 셸 설명서의 [new-cstrustedapplicationpool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b99e-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="4b99e-112">Exchange Server FQDN은 Exchange OWA 인증서 SN(주체 이름) 또는 SAN(주체 대체 이름)으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="4b99e-113">Exchange OWA에서 풀의 FQDN도 신뢰할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b99e-114">CAS 서버가 Exchange 2013 UM (통합 메시징)을 실행 하는 동일한 서버에 배치 된 <EM>되지 않은</EM> 경우이 절차의 나머지 단계를 건너뛰고이 항목 뒷부분에 나오는 "EXCHANGE 2013 CAS 서버에 대 한 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="4b99e-115">CAS 서버가 Exchange 2013 UM (통합 메시징)을 실행 하는 동일한 서버에 배치 된 경우이 절차의 단계를 완료 하 고이 항목 뒷부분에 나오는 "Exchange 2013 CAS 서버에 대해 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4b99e-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="4b99e-116">**Enable-CsTopology**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="4b99e-117">토폴로지 작성기를 열고 기존 토폴로지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="4b99e-118">왼쪽 창에서 **트러스트된 응용 프로그램 서버**가 표시될 때까지 트리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="4b99e-119">**신뢰할 수 있는 응용 프로그램 서버** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="4b99e-120">이제 Exchange 2013 CAS 서버가 신뢰할 수 있는 응용 프로그램 서버로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="4b99e-121">Exchange 2013 CAS 서버에 대해 신뢰할 수 있는 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4b99e-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="4b99e-122">Lync Server 2013 관리 셸을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="4b99e-123">CAS 서버가 Exchange 2013 UM (통합 메시징)을 실행 하는 동일한 서버에 배치 된 *되지 않은* 경우 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="4b99e-124">자세한 내용은 Lync Server 2013 관리 셸 설명서의 [new-cstrustedapplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b99e-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="4b99e-125">**Enable-CsTopology**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="4b99e-126">토폴로지 작성기의 왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**가 표시될 때까지 트리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="4b99e-127">**신뢰할 수 있는 응용 프로그램 서버** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="4b99e-128">이제 Exchange 2013 CAS 서버가 신뢰할 수 있는 응용 프로그램 서버로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

