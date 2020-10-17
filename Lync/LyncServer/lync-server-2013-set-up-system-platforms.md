---
title: 'Lync Server 2013: 시스템 플랫폼 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bd5bff0b215060b1d352d5cc5798b114140c15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509785"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="f0c20-102">Lync Server 2013에서 시스템 플랫폼 설정</span><span class="sxs-lookup"><span data-stu-id="f0c20-102">Set up system platforms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c20-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f0c20-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f0c20-104">영구 채팅 서버 배포를 시작 하기 전에 서버에 대 한 시스템 요구 사항을 충족 하는 하드웨어에 필요한 운영 체제를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="f0c20-105">Lync Server 2013, 데이터베이스 서버 및 파일 서버를 실행 하는 서버에 대해 지원 되는 하드웨어에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013에](lync-server-2013-supported-hardware.md) 사용할 수 있는 하드웨어를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0c20-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="f0c20-106">지원 되는 운영 체제 및 데이터베이스 소프트웨어에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 서버 소프트웨어 및 인프라 지원을](lync-server-2013-server-software-and-infrastructure-support.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0c20-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="f0c20-107">Windows 업데이트 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c20-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f0c20-108">영구 채팅 서버 프런트 엔드 서버 **PersistentChatService**는 Lync Server 2013 Enterprise Edition 풀에 있는 하나 이상의 독립 실행형 컴퓨터에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="f0c20-109">Lync Server Enterprise Edition 프런트 엔드 서버에서는 배치 된를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="f0c20-110">영구 채팅 서버는 다른 Lync Server 역할과 마찬가지로 부트스트래퍼에서 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="f0c20-111">**파일 업로드/다운로드를 위한 영구 채팅 웹 서비스**와 대화방 **용 영구 채팅 웹 서비스** 는 Lync Server 2013 프런트 엔드 서버에 배포 된 웹 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="f0c20-112">단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="f0c20-113">총 8만 동시 사용자를 지 원하는 최대 4 개의 활성 프런트 엔드와 함께 영구 채팅 서버 풀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="f0c20-114">영구 채팅 백 엔드 서버인 **PersistentChatStore**에는 대화방 및 범주가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="f0c20-115">**PersistentChatStore** 는 Enterprise Edition 풀의 전용 SQL Server 백 엔드 서버에 설치 하는 것이 좋습니다. 배치 Lync Server 2013 백 엔드 서버와 **PersistentChatStore** 는 동일한 SQL Server 인스턴스에서 지원 되지만</span><span class="sxs-lookup"><span data-stu-id="f0c20-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="f0c20-116">조직에서 준수 지원이 필요한 경우 토폴로지 작성기를 사용 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="f0c20-117">영구 채팅 서버 준수 서비스가 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="f0c20-118">준수용으로 별도의 데이터베이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-118">A separate database is required for compliance.</span></span> <span data-ttu-id="f0c20-119">영구 채팅 서버에 대 한 준수 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0c20-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="f0c20-120">적어도 각 토폴로지에는 Lync Server 2013이 설치 된 서버와 SQL Server 데이터베이스 소프트웨어가 설치 된 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="f0c20-121">토폴로지 작성기는 여러 영구 채팅 서버 풀을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="f0c20-122">배포 설명서의 모든 풀에서 [Lync server 2013을 배포](lync-server-2013-deploying-lync-server.md) 하는 것과 동일한 배포 지침을 수행 하 여 여러 영구 채팅 서버 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f0c20-123">Lync Server 2013 Standard Edition과 함께 영구 채팅 서버를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="f0c20-124">이 경우 **PersistentChatService** 프런트 엔드 서버가 Standard Edition 서버에서 배치 된 되며, 로컬 SQL Server Express 인스턴스에 **PersistentChatStore** 백 엔드 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f0c20-125">고가용성을 위한 영구 채팅 서버 &nbsp; Standard Edition은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="f0c20-126">성능 및 확장 기능은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-126">Performance and scale will be limited.</span></span> <span data-ttu-id="f0c20-127">또한 새 영구 채팅 서버 &nbsp; Standard Edition 서버 배포만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c20-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="f0c20-128">Lync Server 2010, 그룹 채팅 서버를 Lync Server 2013 &nbsp; 영구 채팅 서버 Standard Edition으로 업그레이드 하는 것은 지원 되지 않습니다 &nbsp; .</span><span class="sxs-lookup"><span data-stu-id="f0c20-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0c20-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0c20-129">See Also</span></span>


[<span data-ttu-id="f0c20-130">Lync Server 2013의 추가 서버 지원 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0c20-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="f0c20-131">Lync Server 2013에 대해 지원 되는 하드웨어</span><span class="sxs-lookup"><span data-stu-id="f0c20-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="f0c20-132">Lync Server 2013의 서버 소프트웨어 및 인프라 지원</span><span class="sxs-lookup"><span data-stu-id="f0c20-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="f0c20-133">Lync Server 2013의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="f0c20-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="f0c20-134">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="f0c20-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

