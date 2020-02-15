---
title: 하이브리드 배포를 사용 하 여 모바일 기능에 대 한 자동 검색 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 027357579ff9ff90d82a78994696a5a2fb656188
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="73a05-102">하이브리드 배포를 사용한 이동성을 Lync Server 2013에서 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="73a05-102">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73a05-103">_**마지막으로 수정 된 항목:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="73a05-103">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="73a05-104">하이브리드 배포는 Microsoft Lync Online 클라우드 서비스와 온-프레미스 배포를 모두 사용 하는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="73a05-105">이 성 유형에서 자동 검색 서비스는 사용자가 실제로 있는 위치를 찾을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="73a05-106">즉, 자동 검색 기능은 사용자 계정 및 사용자 계정을 호스트 하는 서버가 온-프레미스 배포에 있는지, 아니면 Lync Online 배포에 있든 관계 없이 검색 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="73a05-107">예를 들어 사용자의 계정이 Lync Online의 서버에서 호스팅되는 경우 검색 기능 이라고 하는 프로세스에서 사용자를 찾기 위한 *시도가 다음과 같이 수행 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="73a05-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="73a05-108">사용자가 **contoso.com**이라는 온 프레미스 배포와의 연결 시도를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="73a05-109">시도가 자동 검색 서비스와 연결된 DNS 이름인 lyncdiscover.contoso.com으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="73a05-110">자동 검색은 contoso.com 온-프레미스 배포의 가정 된 등록자 풀을 의미 하며 Lync Online에 호스트 되는 사용자의 실제 홈 서버에 대 한 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="73a05-111">그러면 자동 검색에서 사용자에게 **lync.com** 온라인 자동 검색 서비스 조회를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="73a05-112">사용자가 lync.com 온라인 자동 검색 서비스와의 연결 시도를 시작하고 사용자의 계정과 사용자의 홈 서버를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="73a05-p103">모바일 클라이언트에서 사용자 홈 서버가 위치한 배포를 찾을 수 있도록 하려면 새로운 URL(Uniform Resource Locator)로 자동 검색 서비스를 구성해야 합니다. 다음을 수행하여 자동 검색 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-p103">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL). Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="73a05-115">하이브리드 배포용 자동 검색 구성</span><span class="sxs-lookup"><span data-stu-id="73a05-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="73a05-116">Get-CsHostingProvider를 사용 하 여 ProxyFQDN 특성의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-116">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="73a05-117">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="73a05-118">여기서 \[identity\] 는 공유 SIP 주소 공간의 도메인 이름으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a05-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73a05-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73a05-119">See Also</span></span>


<span data-ttu-id="73a05-120">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="73a05-120">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="73a05-121">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="73a05-121">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

