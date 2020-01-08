---
title: 'Lync Server 2013: Edge 서버 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5c743cb229adb6f1ed8298d51713da181750cea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="be540-102">Lync Server 2013의 Edge 서버 cmdlet</span><span class="sxs-lookup"><span data-stu-id="be540-102">Edge Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be540-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="be540-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="be540-104">Edge 서버는 내부 네트워크에 로그인 하지 않은 사용자에 게 Microsoft Lync Server 2013의 기능을 확장할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be540-104">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="be540-105">예를 들어 내부 네트워크를 통하지 않고 인터넷을 통해 Lync Server 2013에 로그온 하는 원격 사용자가 인증 된 사용자가 있는 경우, Lync Server 액세스 Edge 서비스를 실행 하는 Edge 서버를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be540-105">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="be540-106">또한 다른 조직과의 페더레이션을 설정 하려는 경우 또는 사용자에 게 Yahoo\!, AOL, MSN 등의 공공 인스턴트 메시징 서비스와 계정이 있는 사용자에 게 통신 하는 권한을 부여 하려는 경우에는 Edge 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="be540-106">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="be540-107">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be540-107">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="be540-108">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be540-108">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="be540-109">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="be540-109">Messenger until the service shut down date.</span></span> <span data-ttu-id="be540-110">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="be540-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="be540-111">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="be540-111">has been announced.</span></span> <span data-ttu-id="be540-112">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be540-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="be540-113">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="be540-113">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="be540-114">받으려면.</span><span class="sxs-lookup"><span data-stu-id="be540-114">Messenger.</span></span> <span data-ttu-id="be540-115">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be540-115">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="be540-116">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="be540-116">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="be540-117">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be540-117">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="be540-118">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="be540-118">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="be540-119">Edge 서버 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="be540-119">Edge Server Cmdlets</span></span>

<span data-ttu-id="be540-120">다음은 Edge 서버 관리와 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="be540-120">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="be540-121">**Edge 서버**</span><span class="sxs-lookup"><span data-stu-id="be540-121">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="be540-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="be540-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="be540-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="be540-125">[새로운 CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="be540-126">[제거-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="be540-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="be540-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="be540-129">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="be540-129">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="be540-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be540-130">See Also</span></span>


[<span data-ttu-id="be540-131">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="be540-131">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

