---
title: 'Lync Server 2013: 외부 사용자 액세스를 위한 새 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="5d292-102">Lync Server 2013의 외부 사용자 액세스를 위한 새 기능</span><span class="sxs-lookup"><span data-stu-id="5d292-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d292-103">_**마지막으로 수정한 주제:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="5d292-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="5d292-104">Lync Server 2013는 사용자의 기능 및 통신 방법을 확장 하는 새로운 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="5d292-105">또한 Lync Server 2013는 조직에서 사용할 수 있는 서비스를 더욱 효율적으로 통합 하 고 확장 하기 위해 기존 서비스에 대 한 변경 사항을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="5d292-106">다음은 Lync Server 2013 Edge 서버 서비스의 계획 및 배포에 영향을 줄 수 있는 변경 내용에 대 한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="5d292-107">**Ipv6 주소 지정**   Lync server 2013는 모든 Edge 서버 서비스에 대 한 ipv6 주소 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="5d292-108">Windows Server의 구성을 통해 인터페이스에 대 한 IPv6 주소를 제공한 경우 토폴로지 작성기의 IP 주소 구성을 통해 Edge 서버 구성에서 IPv6 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5d292-109">Lync Server 2013에서 IPv6 주소를 사용 하는 경우 조직에서 배포 하는 라우터 및 방화벽의 IPv6 지원 및 인터넷 서비스 공급자의 지원에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="5d292-110">**Xmpp (확장할 수 있는 메시징 및 현재 상태 프로토콜)**   Lync Server 2013에는 Edge 서버에 배포 된 완전히 통합 된 xmpp 프록시와 프런트 엔드 서버에 배포 된 xmpp 게이트웨이가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="5d292-111">XMPP 페더레이션은 선택적 구성 요소로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="5d292-112">XMPP 프록시와 XMPP 게이트웨이를 추가 하 고 구성 하면 사용자는 Microsoft Lync 2013 사용자가 인스턴트 메시지 (IM) 및 현재 상태에 대 한 XMPP 기반 파트너의 연락처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d292-113">현재 Lync Server 2013의 XMPP 서비스는 Lync 클라이언트와 XMPP 기반 연락처 간에 인스턴트 메시지와 현재 상태를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="5d292-114">**모바일 클라이언트**   의 이동성 서비스는 lync server 2010의 고객 업데이트에 도입 되었으며, lync server 2013의 모바일 서비스는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 Microsoft lync mobile 클라이언트에서 인스턴트 메시지 보내기 및 받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="5d292-115">또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일, 부재 중 전화 알림 등 일부 엔터프라이즈 음성 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d292-116">모바일 서비스는 프런트 엔드 서버에 배포 되는 리버스 프록시 및 게시 된 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="5d292-117">Edge 서버를 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="5d292-118">**디렉터는 선택적 역할**   입니다. Lync server 2013 토폴로지에서 디렉터 서버의 역할은 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="5d292-119">웹 서비스를 호스팅하고, 들어오는 사용자 요청을 사전 인증 하 고, 외부 사용자를 홈 풀로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="5d292-120">디렉터를 권장 역할에서 선택적 역할로 변경 해도 디렉터 값이 감소 되는 것이 아니라 서버 수 및 기타 하드웨어 요구 사항 줄이기 (예: 디렉터의 하드웨어 로드 균형 조정기) 요구 사항이 강조 되어 있지 않은 경우 기능 및 기능 손상.</span><span class="sxs-lookup"><span data-stu-id="5d292-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="5d292-121">프런트 엔드 서버는 제공 되는 서비스에 영향을 주지 않고 디렉터와 동일한 작업을 수행할 수 있으므로 선택 하는 경우에는 선택적으로 디렉터를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="5d292-122">프런트 엔드 서버가 해당 위치에 동일한 서비스를 제공 한다는 확신 없이 디렉터를 안전 하 게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d292-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5d292-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d292-123">See Also</span></span>


[<span data-ttu-id="5d292-124">Lync Server 2013에서 IPv6 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="5d292-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="5d292-125">Lync Server 2013의 외부 사용자 액세스 계획</span><span class="sxs-lookup"><span data-stu-id="5d292-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="5d292-126">Lync Server 2013에서 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션 계획</span><span class="sxs-lookup"><span data-stu-id="5d292-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

