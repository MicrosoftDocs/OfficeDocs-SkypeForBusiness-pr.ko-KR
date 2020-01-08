---
title: Lync Server 2013, 영구 채팅 서버 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de49e9843c5243457d1c4d736d9bfeda246f042e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="a25bb-102">Lync Server 2013, 영구 채팅 서버 관리</span><span class="sxs-lookup"><span data-stu-id="a25bb-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a25bb-103">_**마지막으로 수정한 주제:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="a25bb-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="a25bb-104">Lync Server 2013, 영구 채팅 서버를 사용 하 여 여러 사용자가 텍스트, 링크, 파일을 비롯 한 특정 항목에 대 한 콘텐츠를 게시 하 고 액세스 하는 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="a25bb-105">사용자가 세션 중에 실시간으로 통신할 수 있지만, 각 세션의 내용이 영구적 이므로 세션이 종료 된 후에도 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="a25bb-106">영구 채팅방의 콘텐츠는 주로 짧은 문자 메시지로 구성 되며, *스토리*는 긴 메시지를 포함 하 고 (예를 들어 하이퍼링크, 이모티콘 및 업로드 된 문서) 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a25bb-107">Lync 2013 클라이언트에서는 파일 업로드 및 다운로드가 지원 되지 않습니다. 그러나 Lync Server 2013, 영구 채팅 서버에서 여전히 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="a25bb-108">레거시 그룹 채팅 클라이언트는 파일을 게시 하 고 볼 수 있지만 Lync 2013 클라이언트를 통해 동일한 채팅방을 액세스 하는 경우에는 파일에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="a25bb-109">채팅방에 대 한 액세스는 구성원 목록으로 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="a25bb-110">전체 채팅방 기록은 시간 시간순 검토 또는 전체 텍스트 검색의 모든 구성원에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="a25bb-111">영구 채팅 클라이언트를 사용 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 클라이언트 계획](lync-server-2013-planning-for-clients.md) 및 [lync server 2013에서 클라이언트 및 장치](lync-server-2013-deploying-clients-and-devices.md) 배포 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a25bb-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="a25bb-112">조직에 대해 영구 채팅 서버를 설정 하는 경우 배포 중에 초기 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="a25bb-113">그러나 영구 채팅 서버 지원을 구현 하는 방법을 변경 해야 하는 경우도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="a25bb-114">예를 들어 조직 내 특정 팀 또는 그룹에 대해 영구적 채팅 서버 지원과 컨트롤을 다르게 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="a25bb-115">이 섹션에서는 영구 채팅 서버 배포를 사용자 지정 하는 데 도움이 되는 정보와 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25bb-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="a25bb-116">영구 채팅 서버에 대해 구성할 수 있는 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 영구 채팅 서버에 대 한 조직의 요구 사항 정의](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) 및 lync server 2013에서 계획 설명서, 배포 설명서 또는 운영 설명서의 [영구 채팅 서버 작동 방식](lync-server-2013-how-persistent-chat-server-works.md) 에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a25bb-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="a25bb-117">Lync Server 2013의 영구 채팅 서버를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a25bb-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a25bb-118">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a25bb-118">In This Section</span></span>

  - [<span data-ttu-id="a25bb-119">Lync Server 2013에서 영구 채팅 서버가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="a25bb-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="a25bb-120">범주를 사용하여 영구 채팅 서버 관리</span><span class="sxs-lookup"><span data-stu-id="a25bb-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="a25bb-121">영구 채팅 구성원 자격 이해</span><span class="sxs-lookup"><span data-stu-id="a25bb-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="a25bb-122">영구 채팅 서버 모범 사례</span><span class="sxs-lookup"><span data-stu-id="a25bb-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="a25bb-123">Lync Server 2013에서 범주, 채팅방 및 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="a25bb-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="a25bb-124">Lync Server 2013에서 영구 채팅 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="a25bb-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="a25bb-125">Lync Server 2013에서 영구 채팅 시스템 운영 및 유지 관리</span><span class="sxs-lookup"><span data-stu-id="a25bb-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

