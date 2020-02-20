---
title: 'Lync Server 2013: 중재 서버 배포 및 피어 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a5611e8137aba2f465c6488201ba1b2936dd76
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="0e1bb-102">Lync Server 2013에서 중재 서버 배포 및 피어 정의</span><span class="sxs-lookup"><span data-stu-id="0e1bb-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e1bb-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0e1bb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0e1bb-104">Enterprise Voice 작업, 전화 접속 회의 및 고급 Enterprise Voice 응용 프로그램 (응답 그룹 응용 프로그램, 통화 대기 응용 프로그램, CAC (통화 허용 제어) 등)은 프런트 엔드 풀에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="0e1bb-105">Lync Server 2013를 사용 하는 경우 중재 서버의 기능이 프런트 엔드 서버에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="0e1bb-106">별도의 독립 실행형 중재 서버가 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="0e1bb-107">프런트 엔드 풀은 지원 되는 게이트웨이 (PSTN (공중 전화망) 게이트웨이 또는 IP-PBX)와 직접 통신할 수 있으며, 중재 서버가 중개자 역할을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="0e1bb-108">단, ITSP(인터넷 전화 통신 서비스 공급자)에 대한 SBC(세션 경계 컨트롤러)에 연결하도록 SIP 트렁크를 구성하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="0e1bb-109">엔터프라이즈 음성 인프라를 SIP 트렁크 공급자에 연결 하려면 별도의 중재 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="0e1bb-110">Lync Server (프런트 엔드 풀 또는 독립 실행형 중재 서버의 중재 서버 구성 요소)와 게이트웨이가 연결 되는 것은 *트렁크*라는 논리적 연결로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="0e1bb-111">이 섹션의 항목은 트렁크를 정의하는 방법과 SIP 트렁크에 연결하기 위해 독립 실행형 중재 서버를 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1bb-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e1bb-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0e1bb-112">In This Section</span></span>

  - [<span data-ttu-id="0e1bb-113">Lync Server 2013의 토폴로지 작성기에서 중재 서버 정의</span><span class="sxs-lookup"><span data-stu-id="0e1bb-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="0e1bb-114">Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="0e1bb-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="0e1bb-115">Lync Server 2013에서 중재 서버용 파일 설치</span><span class="sxs-lookup"><span data-stu-id="0e1bb-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="0e1bb-116">Lync Server 2013의 토폴로지 작성기에서 추가 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="0e1bb-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="0e1bb-117">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="0e1bb-117">Related Sections</span></span>

[<span data-ttu-id="0e1bb-118">Lync Server 2013에서 전화 접속 회의 구성</span><span class="sxs-lookup"><span data-stu-id="0e1bb-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

