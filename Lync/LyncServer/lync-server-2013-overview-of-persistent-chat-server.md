---
title: 'Lync Server 2013: 영구 채팅 서버 개요'
description: 'Lync Server 2013: 영구 채팅 서버 개요'
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
ms.openlocfilehash: bbcb396522611aca52bd2093f2fd49f376341356
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577314"
---
# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6c198-103">Lync Server 2013의 영구 채팅 서버 개요</span><span class="sxs-lookup"><span data-stu-id="6c198-103">Overview of Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c198-104">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6c198-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6c198-105">Lync Server 2013, 영구 채팅 서버를 사용 하면 시간에 따라 지속 되는 단체 및 토픽 기반 대화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-105">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="6c198-106">영구 채팅 서버는 조직에서 다음을 수행 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-106">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="6c198-107">지리적으로 분산 된 팀과 부서간 업무 흐름도 간의 통신을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-107">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="6c198-108">영구 채팅을 사용 하 여 팀에서 정보, 아이디어 및 의사 결정을 효율적으로 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-108">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="6c198-109">대화방에 게시 된 메시지 (토론 포럼)는 동시에 온라인 상태가 아닌 경우에도 서로 다른 위치 및 부서의 사용자가 참여할 수 있도록 계속 해 서 사용할 수 있습니다 (즉, 시간이 지남에 따라 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="6c198-109">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="6c198-110">사용자가 대화방에 연결 되 면 대화방에 구성 가능한 채팅 기록 메시지를 자동으로 로드 하 여 사용자에 게 대화에 대 한 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-110">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="6c198-111">정보 인식을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-111">Improve information awareness.</span></span> <span data-ttu-id="6c198-112">사용자는 클라이언트 쪽 필터를 사용 하 여 메시지 콘텐츠의 키워드, 메시지의 "보낸 사람" 필드 값 등을 정의할 수 있으며, 이러한 조건이 영구적 채팅 인스턴트 메시지 또는 대화방 메시지에 맞을 때 알림을 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-112">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="6c198-113">이러한 방식으로 사용자는 가장 관심 있는 콘텐츠를 최신 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-113">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="6c198-114">확장 된 조직과의 통신을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-114">Improve communication with their extended organization.</span></span> <span data-ttu-id="6c198-115">조직의 다른 사람들과 오랫동안 실행 되는 항목에 대 한 공동 작업을 간편 하 게 수행 하 고 정보를 공유 하기 위한 영구 위치를 제공 함으로써 지속적인 채팅을 통해 통신을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-115">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="6c198-116">정보 과부하를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-116">Reduce information overload.</span></span> <span data-ttu-id="6c198-117">사용자는 클라이언트 쪽 필터를 사용 하 여 가장 관심 있는 대화방 및 메시지를 팔 로우 하 고, 팔 로우 하려는 채팅방을 대화 상대 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-117">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="6c198-118">중요 한 지식 및 정보에 대 한 dispersion을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-118">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="6c198-119">문서와 링크를 모든 팀이 액세스 하기 위해 대화 내에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-119">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="6c198-120">사용자는 광범위 한 팀에 질문을 게시 하 여 주제별 전문가가 제공 하는 반응을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-120">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="6c198-121">다른 정보 시스템과 통합 하면 중요 한 조직 데이터를 대규모 그룹으로 쉽게 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-121">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="6c198-122">Lync Server 2013에서 대화방을 사용 하도록 설정 하려면 Lync Server 2013 영구 채팅을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-122">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="6c198-123">채팅방을 사용 하는 방법에 대 한 자세한 내용은의 영구 채팅 도움말을 참조 하세요 <https://go.microsoft.com/fwlink/p/?linkid=270945> .</span><span class="sxs-lookup"><span data-stu-id="6c198-123">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="6c198-124">사용자가 Lync Server를 사용할 수 있도록 설정 되어 있고 Lync Server 지원이 배포 되는 경우 사용자는 Lync 2013 영구 채팅을 설치 하 고 사용 하 여 대화방 지원을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-124">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="6c198-125">조직이 규정 준수 규정을 준수 해야 하는 경우에는 필요에 따라 영구 채팅 준수 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c198-125">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

