---
title: 'Lync Server 2013: 하이브리드 배포에 대 한 자동 검색 구성'
description: 'Lync Server 2013: 하이브리드 배포에 대 한 자동 검색 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6797e3f6b77e3016f6cef87f2a930f5a7c1fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562494"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="25a06-103">Lync Server 2013에서 하이브리드 배포에 대 한 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="25a06-103">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25a06-104">_**마지막으로 수정 된 항목:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="25a06-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="25a06-105">하이브리드 배포는 Microsoft Lync Online 클라우드 서비스와 온-프레미스 배포를 모두 사용 하는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="25a06-106">이 성 유형에서 자동 검색 서비스는 사용자가 실제로 있는 위치를 찾을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="25a06-107">즉, 자동 검색 기능은 사용자 계정 및 사용자 계정을 호스트 하는 서버가 온-프레미스 배포에 있는지, 아니면 Lync Online 배포에 있든 관계 없이 검색 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="25a06-108">예를 들어 사용자의 계정이 Lync Online의 서버에서 호스팅되는 경우 검색 기능 이라고 하는 프로세스에서 사용자를 찾기 위한 *시도가 다음과 같이 수행 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="25a06-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="25a06-109">사용자가 **contoso.com**이라는 온 프레미스 배포와의 연결 시도를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="25a06-110">시도가 자동 검색 서비스와 연결된 DNS 이름인 lyncdiscover.contoso.com으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="25a06-111">자동 검색은 contoso.com 온-프레미스 배포의 가정 된 등록자 풀을 의미 하며 Lync Online에 호스트 되는 사용자의 실제 홈 서버에 대 한 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="25a06-112">그러면 자동 검색에서 사용자에게 **lync.com** 온라인 자동 검색 서비스 조회를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="25a06-113">사용자가 lync.com 온라인 자동 검색 서비스와의 연결 시도를 시작하고 사용자의 계정과 사용자의 홈 서버를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="25a06-114">클라이언트에서 사용자 홈 서버가 있는 배포를 검색할 수 있도록 하려면 새 URL (uniform resource locator)을 사용 하 여 자동 검색 서비스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-114">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="25a06-115">다음을 수행하여 자동 검색 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-115">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="25a06-116">하이브리드 배포용 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="25a06-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="25a06-117">[Lync Server 2013의 자동 검색 서비스 요구 사항](lync-server-2013-autodiscover-service-requirements.md)항목에서 Get-CsHostingProvider를 사용 하 여 proxyfqdn 특성 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-117">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="25a06-118">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="25a06-119">여기서 \[ identity \] 는 공유 SIP 주소 공간의 도메인 이름으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a06-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="25a06-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25a06-120">See Also</span></span>


[<span data-ttu-id="25a06-121">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="25a06-121">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="25a06-122">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="25a06-122">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

