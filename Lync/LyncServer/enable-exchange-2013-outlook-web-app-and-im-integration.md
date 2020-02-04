---
title: Exchange 2013 Outlook Web App 및 IM 통합 기능 사용
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
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="25c84-102">Exchange 2013 Outlook Web App 및 IM 통합 기능 사용</span><span class="sxs-lookup"><span data-stu-id="25c84-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25c84-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="25c84-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="25c84-104">Lync Server 2013와 함께 Exchange 2013 OWA (Outlook Web Access) 및 IM (인스턴트 메시징) 통합을 사용 하도록 설정 하려면 2013 Exchange 클라이언트 액세스 서버 (CAS) 서버를 Lync Server 2013 토폴로지에 신뢰할 수 있는 응용 프로그램 서버로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="25c84-105">신뢰할 수 있는 응용 프로그램 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="25c84-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="25c84-106">Lync Server 2013 관리 셸을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="25c84-107">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="25c84-108">이는 풀을 만들고 있는 siteName에 대 한 siteID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="25c84-109">자세한 내용은 Lync Server 2013 관리 셸 설명서에서 [Get CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25c84-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="25c84-110">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="25c84-111">자세한 내용은 Lync Server 2013 관리 셸 설명서의 [CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25c84-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="25c84-112">Exchange Server FQDN은 Exchange OWA 인증서 주체 이름 (SN) 또는 주체 대체 이름 (SAN)으로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="25c84-113">Exchange OWA에서 풀의 FQDN도 신뢰할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="25c84-114">CAS 서버가 Exchange 2013 UM (통합 메시징)를 실행 하는 동일한 서버에 collocated <EM>되지 않은</EM> 경우이 절차의 나머지 단계를 건너뛰고이 항목의 뒷부분에 나오는 "EXCHANGE 2013 CAS 서버용 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="25c84-115">CAS 서버가 Exchange 2013 UM (통합 메시징)를 실행 하는 동일한 서버에 collocated이 절차의 단계를 완료 하 고이 항목의 뒷부분에 나오는 "Exchange 2013 CAS 서버용 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="25c84-116">**Enable-CsTopology**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="25c84-117">토폴로지 작성기를 열고 기존 토폴로지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="25c84-118">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**에 도달할 때까지 트리를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="25c84-119">**신뢰할 수 있는 응용 프로그램 서버** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="25c84-120">이제 신뢰할 수 있는 응용 프로그램 서버로 나열 된 Exchange 2013 CAS 서버가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="25c84-121">Exchange 2013 CAS 서버에 대 한 신뢰할 수 있는 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="25c84-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="25c84-122">Lync Server 2013 관리 셸을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="25c84-123">CAS 서버가 Exchange 2013 UM (통합 메시징)를 실행 하는 동일한 서버에 collocated *있지 않은* 경우 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="25c84-124">자세한 내용은 Lync Server 2013 관리 셸 설명서의 [New CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25c84-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="25c84-125">**Enable-CsTopology**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="25c84-126">토폴로지 작성기의 왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**에 도달할 때까지 트리를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="25c84-127">**신뢰할 수 있는 응용 프로그램 서버** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="25c84-128">이제 신뢰할 수 있는 응용 프로그램 서버로 나열 된 Exchange 2013 CAS 서버가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25c84-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

