---
title: 영구 채팅 서버에 대 한 이전 버전과의 호환성을 실행 합니다.
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52d107c13d281001196dcad17604d0bfbbb9e522
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="480b3-102">영구 채팅 서버에 대 한 이전 버전과의 호환성을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="480b3-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="480b3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="480b3-104">Lync Server 2013, 영구 채팅 서버 끝점은 영구 채팅 서버 풀을 가리키는 간단한 URL을 만드는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="480b3-105">이 기능은 레거시 클라이언트를 Lync 2013을 실행 하는 컴퓨터에 연결 하려고 할 때 수동 구성에 사용자가 단순 URL을 입력할 수 있기 때문에 (Microsoft Office Communications Server 2007 R2 그룹 채팅 서버 또는 Lync Server 2010, 그룹 채팅)에 유용 합니다. 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="480b3-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="480b3-106">이 끝점은 영구 채팅에서 사용 되지 않으며 레거시 클라이언트에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="480b3-107">이 기능은 대화방을 마이그레이션할 수 있지만 조직 전체에 Lync 2013 클라이언트를 배포 하지 않은 중간 기간에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="480b3-108">Lync 2010 그룹 채팅 (클라이언트)을 실행 하는 사용자는 계속 해 서 영구 채팅 서버 백 엔드 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="480b3-109">여러 영구 채팅 서버 끝점을 만들 필요는 없습니다. 각 영구 채팅 서버 풀에 대해 하나만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="480b3-110">관리자는 여러 끝점 (풀 당 하나)을 만들 수 있지만 레거시 클라이언트는 한 번에 하나의 풀에만 연결 되도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="480b3-111">일반 또는 메인스트림 시나리오에서는 레거시 배포가 하나의 풀에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="480b3-112">일반적으로 새 배포는 해당 풀을 새 Lync Server 2013로 마이그레이션하고 새로운 영구 채팅 서버 풀을 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="480b3-113">주요 시나리오에서는 일반적으로 다음 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="480b3-114">Lync Server 2010, 그룹 채팅 풀을 하나씩 사용 하 여 사용자를 관리 하 고, Lync 2010 그룹 채팅 클라이언트는 잘 알려진 사용자 (기본 sip: ocschat@\<domainName\>) 또는 이와 유사한 것 중 하나를 통해 해당 풀에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="480b3-115">사용자가 SIP 사용이 가능한 Active Directory 도메인 서비스이 고 조회 서비스에서 들어오는 요청을 받을 수 있도록 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="480b3-116">이후에 Lync Server 2013 영구 채팅 서버와 영구 채팅 서버 풀을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="480b3-117">사용자가 일반적으로 오프라인인 시간 중에는(예: 주말) 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="480b3-118">Lync Server 2010, 그룹 채팅을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="480b3-119">Lync Server 2010, 그룹 채팅 풀의 데이터를 Lync Server 2013 영구 채팅 서버 풀로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="480b3-120">Active Directory 도메인 서비스에서 잘 알려진 사용자를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="480b3-121">이전에 삭제한 잘 알려진 사용자와 동일한 SIP URI를 사용하여 새로운 *레거시 끝점*을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="480b3-122">Lync Server 2013, 영구 채팅 서버를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="480b3-123">사용자는 Lync 2010 그룹 채팅 (클라이언트)을 사용 하 여 다시 로그온 하 고 구성을 변경할 필요 없이 자신의 데이터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="480b3-124">나중에 Lync Server 2010, 그룹 채팅을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="480b3-125">따라서 Lync Server 2013, 영구 채팅 서버를 배포 하 고 새 Lync Server 2013 영구 채팅 서버 풀을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="480b3-126">Lync Server 2010, 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하는 방법에 대 한 자세한 내용은 [Lync server 2010, 그룹 채팅 또는 Office Communications server 2007 R2 그룹 채팅에서 Lync server 2013, 영구 채팅 서버로 마이그레이션을](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="480b3-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="480b3-127">이전 버전과의 호환성을 실행 하려면 레거시 그룹 채팅 풀 클라이언트에서 사용할 수 있는 영구 채팅 서버 풀을 가리키는 영구 채팅 서버 끝점을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="480b3-128">다음으로, 해당 SIP 주소를 대화 상대 개체로 사용 하도록 영구 채팅 클라이언트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="480b3-129">특정 영구 채팅 서버 풀에 대 한 **get-cspersistentchatendpoint** cmdlet을 사용 하 여 SIP 주소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="480b3-130">Windows PowerShell 명령줄 인터페이스를 사용 하 여 영구 채팅 서버 끝점을 추가 하려면 다음 예를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="480b3-131">여기에서는 풀의 FQDN(정규화된 도메인 이름)이 "pcpool.contoso.com"인 "contoso.com" 토폴로지에서 연락처 개체의 이름이 "persistentchat"로 지정되도록 연락처 개체를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="480b3-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="480b3-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="480b3-132">See Also</span></span>


[<span data-ttu-id="480b3-133">Lync Server 2013, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에서 Lync Server 2013, 영구 채팅 서버로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="480b3-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

