---
title: 'Lync Server 2013: 영구 채팅 서버 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71b856b4c5199acacd0ed7a3fdf41ed5ab92f59d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="67838-102">Lync Server 2013의 영구 채팅 서버 개요</span><span class="sxs-lookup"><span data-stu-id="67838-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67838-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="67838-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="67838-104">Lync Server 2013, 영구 채팅 서버를 통해 사용자는 시간에 따라 유지 되는 단체의 토픽 기반 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="67838-105">영구 채팅 서버는 조직에서 다음을 수행할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="67838-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="67838-106">지리적으로 분산 된 팀과 부서간 업무 흐름도 간의 의사 소통을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="67838-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="67838-107">영구 채팅을 사용 하면 팀에서 정보, 아이디어 및 의사 결정을 효율적으로 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="67838-108">채팅방에 게시 된 메시지 (토론 포럼)는 계속 해 서 온라인 상태가 아닌 경우에도 다른 위치와 부서의 사용자가 참여할 수 있도록 유지할 수 있습니다 (즉, 시간에 따라 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="67838-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="67838-109">사용자가 채팅방에 연결 되 면 사용자에 게 대화에 대 한 컨텍스트를 제공 하기 위해 채팅 실 (구성 가능한 채팅 기록 번호)이 채팅방에 자동으로 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67838-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="67838-110">정보 인식 개선.</span><span class="sxs-lookup"><span data-stu-id="67838-110">Improve information awareness.</span></span> <span data-ttu-id="67838-111">사용자는 클라이언트측 필터를 사용 하 여 메시지 내용의 키워드 또는 메시지의 "보낸 사람" 필드 값을 정의할 수 있으며, 이러한 조건이 충족 되는 경우에는 영구 채팅 인스턴트 메시지 또는 채팅방 메시지에서 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="67838-112">이렇게 하면 사용자가 가장 관심 있는 콘텐츠를 사용 하 여 최신 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="67838-113">확장 된 조직과의 통신을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="67838-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="67838-114">조직의 다른 사용자와의 장기 실행 항목을 쉽게 공동으로 작업 하 고 정보를 공유할 수 있는 지속적인 장소를 제공 함으로써 지속적인 채팅을 통해 통신을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="67838-115">정보 과부하를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="67838-115">Reduce information overload.</span></span> <span data-ttu-id="67838-116">사용자는 클라이언트측 필터를 사용 하 여 가장 관심 있는 채팅방과 메시지를 팔 로우 할 수 있으며 팔 로우 하는 채팅방을 자신의 연락처 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="67838-117">중요 한 지식과 정보의 dispersion을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="67838-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="67838-118">문서 및 링크는 모든 팀의 액세스를 위해 대화 내에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="67838-119">광범위 한 팀에 질문을 게시 하면 사용자가 주제별 전문가의 응답을 통해 혜택을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="67838-120">다른 정보 시스템과 통합 하면 중요 한 조직 데이터가 대규모 그룹에 쉽게 전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="67838-121">Lync Server 2013에서 채팅방을 사용 하도록 설정 하려면 Lync Server 2013 영구 채팅을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="67838-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="67838-122">채팅방을 사용 하는 방법에 대 한 자세한 내용은의 영구 <http://go.microsoft.com/fwlink/p/?linkid=270945>채팅 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67838-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="67838-123">Lync Server에 사용자를 설정 하 고 Lync Server 지원이 배포 되는 경우 사용자는 Lync 2013 영구 채팅을 설치 하 고 사용 하 여 채팅방 지원을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="67838-124">조직이 준수 규정을 따라야 하는 경우에는 선택적으로 영구 채팅 준수 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67838-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

