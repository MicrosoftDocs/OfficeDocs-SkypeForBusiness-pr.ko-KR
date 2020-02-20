---
title: 'Lync Server 2013: 범주, 대화방 및 추가 기능 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c285ca6c9f90cab304d3ce87341c33fea83ac09f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="ad422-102">Lync Server 2013에서 범주, 대화방 및 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="ad422-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad422-103">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ad422-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ad422-104">Lync Server 2013 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 관리자는 **영구 채팅** 페이지를 사용 하 여 범주 및 추가 기능을 만들 수 있습니다. 영구 채팅방을 관리 하기 위해 관리자는 Windows PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="ad422-105">또한 영구 채팅 관리자가 SIP를 사용 하도록 설정 된 경우에는 Lync 클라이언트를 사용 하 여 웹 페이지를 실행 하 여 대화방을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="ad422-106">다음 항목에서는 범주 및 대화방을 만들고 작업하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ad422-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ad422-107">In This Section</span></span>

  - [<span data-ttu-id="ad422-108">Lync Server 2013에서 새 범주 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="ad422-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="ad422-109">Lync Server 2013에서 새 채팅방 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="ad422-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="ad422-110">Lync Server 2013에서 대화방을 위한 새 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="ad422-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="ad422-111">Lync Server 2013의 강당 대화방에서 메시지를 게시할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="ad422-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="ad422-112">Lync Server 2013에서 대화방을 사용 하지 않도록 설정 하거나 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ad422-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="ad422-113">Lync Server 2013에서 한 범주에서 다른 범주로 대화방 이동</span><span class="sxs-lookup"><span data-stu-id="ad422-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="ad422-114">Lync Server 2013에서 채팅방 또는 범주 삭제</span><span class="sxs-lookup"><span data-stu-id="ad422-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="ad422-115">Lync Server 2013에서 메시지 삭제 또는 오래 된 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="ad422-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

