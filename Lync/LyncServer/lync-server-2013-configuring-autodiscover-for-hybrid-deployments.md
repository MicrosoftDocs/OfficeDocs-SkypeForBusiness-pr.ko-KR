---
title: 'Lync Server 2013: 하이브리드 배포에 대 한 자동 검색 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc2c28d42569d2f52b55dd04a90f5a788969c3ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="f085e-102">Lync Server 2013에서 하이브리드 배포에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="f085e-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f085e-103">_**마지막으로 수정한 주제:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="f085e-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="f085e-104">하이브리드 배포는 Microsoft Lync Online 클라우드 서비스와 온-프레미스 배포를 모두 사용 하는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="f085e-105">이런 종류의 구성에서는 자동 검색 서비스가 사용자가 실제로 어디에 있는지 찾을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="f085e-106">즉, 자동 검색을 사용 하면 사용자 계정을 찾는 데 도움이 되며 사용자 계정을 호스트 하는 서버가 온-프레미스 배포 인지 Lync Online 배포에 있는지 여부에 관계 없이 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="f085e-107">예를 들어 사용자의 계정이 Lync Online의 서버에서 호스팅되는 경우 검색 기능 이라고 하는 프로세스 *에서 다음과 같이*사용자를 찾으려고 시도 하는 것이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="f085e-108">사용자가 온-프레미스 배포 ( **contoso.com**)에 대 한 연결 시도를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="f085e-109">Lyncdiscover.contoso.com에서 자동 검색 서비스와 연결 된 DNS 이름으로 시도를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="f085e-110">자동 검색은 contoso.com 온-프레미스 배포의 가정 된 등록자 풀을 나타내며 Lync Online에서 호스팅되는 사용자의 실제 홈 서버에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="f085e-111">다시 검색 하면 사용자가 **lync.com** Online 자동 검색 서비스에 대 한 조회를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="f085e-112">사용자가 lync.com 온라인 자동 검색 서비스에 대 한 연결 시도를 시작 하 고 사용자의 계정 및 사용자의 홈 서버를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="f085e-113">클라이언트가 사용자 홈 서버가 있는 배포를 검색할 수 있도록 하려면 새 URL (uniform resource locator)을 사용 하 여 자동 검색 서비스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="f085e-114">자동 검색 서비스를 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="f085e-115">하이브리드 배포에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="f085e-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="f085e-116">[Lync Server 2013에 대 한 자동 검색 서비스 요구 사항](lync-server-2013-autodiscover-service-requirements.md)항목에서 Get-CsHostingProvider를 사용 하 여 proxyfqdn 특성의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="f085e-117">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="f085e-118">\[Id\] 가 공유 SIP 주소 공간의 도메인 이름으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f085e-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f085e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f085e-119">See Also</span></span>


[<span data-ttu-id="f085e-120">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="f085e-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="f085e-121">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="f085e-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

