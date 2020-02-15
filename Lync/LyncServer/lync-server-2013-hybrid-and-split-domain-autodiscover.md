---
title: 'Lync Server 2013: 하이브리드 및 분할 도메인 자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e4adc6c0f8a3ffda53821c412e0efbda74bbebc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="341b6-102">Lync Server 2013의 하이브리드 및 분할 도메인 자동 검색</span><span class="sxs-lookup"><span data-stu-id="341b6-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="341b6-103">_**마지막으로 수정 된 항목:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="341b6-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="341b6-104">공유 SIP 주소 공간 ( *분할 도메인* 배포 라고도 함) 또는 *하이브리드* 배포는 사용자가 온-프레미스 배포와 온라인 환경 전체에 배포 되는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="341b6-105">원하는 결과는 홈 서버가 있는 위치 (온-프레미스 또는 온라인)에 관계 없이 사용자가 배포에 로그인 하 여 해당 홈 서버 위치로 리디렉션되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="341b6-106">이 작업을 수행 하기 위해 Lync Server 2013의 자동 검색 기능은 온라인 사용자를 온라인 토폴로지로 리디렉션하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="341b6-107">Lync Server 관리 셸, **get-help-CsHostingProvider** Cmdlet 및 **Set-cshostingprovider** cmdlet을 사용 하 여 자동 검색 URL (uniform resource locator)을 구성 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="341b6-108">분할 도메인 배포의 모바일 기능</span><span class="sxs-lookup"><span data-stu-id="341b6-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="341b6-109">수집 및 기록해야 하는 배포된 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="341b6-110">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="341b6-111">결과에서 **ProxyFQDN** 특성이 포함된 온라인 공급자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="341b6-112">예: sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="341b6-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="341b6-113">ProxyFQDN의 값을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="341b6-114">온라인 공급자와 페더레이션 할 수 있도록 온-프레미스 Lync Server 제어판에서 페더레이션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="341b6-115">온라인 공급자에 대한 페더레이션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-115">Enable federation for the online provider.</span></span> <span data-ttu-id="341b6-116">기본적으로 모든 온라인 사용자는 도메인 페더레이션에 대해 사용 하도록 설정 되며 모든 도메인과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="341b6-117">차단 된 도메인과 허용 도메인을 정의 하는 경우 명시적으로 허용 하거나 차단할 도메인을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="341b6-118">온라인 페더레이션의 경우 방화벽 예외, 인증서 및 DNS 호스트 (i p v 6을 사용 하는 경우 A 또는 AAAA) 레코드를 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="341b6-119">또한 페더레이션 정책도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="341b6-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="341b6-120">자세한 내용은 [Lync Server 2013 및 Office Communications Server Federation 계획](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="341b6-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

