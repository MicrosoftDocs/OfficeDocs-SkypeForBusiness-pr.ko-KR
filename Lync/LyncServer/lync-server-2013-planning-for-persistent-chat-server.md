---
title: 'Lync Server 2013: 영구 채팅 서버 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Persistent Chat Server
ms:assetid: 57b2f574-234e-4a5a-bb78-8823369ba79e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398381(v=OCS.15)
ms:contentKeyID: 48184190
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37208a366ae1cac70733113d6b15605886f34e97
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521965"
---
# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="7521e-102">Lync Server 2013의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="7521e-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7521e-103">_**마지막으로 수정 된 항목:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="7521e-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="7521e-104">Lync Server 2013, 영구 채팅 서버를 사용 하 여 여러 사용자가 텍스트, 링크 및 파일을 비롯 한 특정 항목에 대 한 콘텐츠를 게시 하 고 액세스 하는 대화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7521e-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="7521e-105">사용자가 세션 중에 실시간으로 통신할 수 있지만 각 세션의 콘텐츠는 영구적 이며 세션이 종료 된 후에도 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7521e-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="7521e-106">이 섹션에서는 요구 사항 정의, 구성 요소 및 지원 되는 토폴로지 확인, 배포 권장 사항을 비롯 한 Lync Server 2013, 영구 채팅 서버 배포의 계획 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521e-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7521e-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7521e-107">In This Section</span></span>

  - [<span data-ttu-id="7521e-108">Lync Server 2013의 영구 채팅 서버 개요</span><span class="sxs-lookup"><span data-stu-id="7521e-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="7521e-109">Lync Server 2013에서 영구 채팅 서버가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="7521e-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="7521e-110">Lync Server 2013의 영구 채팅 서버에 대 한 조직의 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="7521e-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="7521e-111">Lync Server 2013의 영구 채팅 서버에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="7521e-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="7521e-112">Lync Server 2013의 영구 채팅 서버에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7521e-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="7521e-113">Lync Server 2013의 영구 채팅 서버에 대 한 시스템 및 인프라 설정</span><span class="sxs-lookup"><span data-stu-id="7521e-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="7521e-114">Lync Server 2013의 영구 채팅 서버에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="7521e-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

