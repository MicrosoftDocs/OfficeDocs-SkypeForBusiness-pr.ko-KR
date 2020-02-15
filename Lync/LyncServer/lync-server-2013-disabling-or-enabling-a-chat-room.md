---
title: 'Lync Server 2013: 대화방을 사용 하지 않도록 설정 하거나 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d9c706c0ea5afcff4f249a9c00a2355667f221
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="8b679-102">Lync Server 2013에서 대화방을 사용 하지 않도록 설정 하거나 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8b679-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b679-103">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="8b679-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8b679-104">영구 채팅방의 항목이 더 이상 관련이 없으면 사용자가 대화방을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="8b679-105">대화방을 사용 하지 않도록 설정 하면 모든 구성원이 대화방에서 즉시 연결이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="8b679-106">채팅방을 사용 하지 않도록 설정한 후에는 사용자가 대화방 검색에서 해당 채팅방을 다시 가입 하거나 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="8b679-107">사용 하지 않도록 설정 된 대화방은 나중에 영구 채팅 관리자에 의해 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="8b679-108">대화방을 사용하지 않도록 설정하면 해당 구성원 자격 목록 및 기타 설정이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="8b679-109">대화방을 다시 사용 하도록 설정 하는 경우에는 설정을 수동으로 다시 만들지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="8b679-110">대화방의 기록이 유지 되는 경우 (대화방 기록 지 속성은 해당 종류 내의 모든 채팅방에 적용 되는 종류의 선택적 설정), 기본적으로는 유지 되지만, 해당 범주의 **채팅 사용 내역** 을 false로 설정 하 여 해제할 수는 있지만, 채팅방을 사용 하지 않도록 설정 하면 콘텐츠가 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="8b679-111">그러나 대화방을 사용할 수 없는 상태로 유지 하는 동안에는 검색에 해당 콘텐츠가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="8b679-112">나중에 대화방을 사용 하도록 설정 하면 사용자는 대화방을 사용 하지 않도록 설정 하기 전에 게시 된 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="8b679-113">Windows PowerShell 명령줄 인터페이스를 사용 하 여 대화방을 비활성화 하 고 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)의 "대화방 관리"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b679-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="8b679-114">채팅방을 사용 하지 않도록 설정 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="8b679-115">대화방을 사용 하려면 Disabled 속성을 False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="8b679-116">Lync Server 제어판을 사용 하 여 대화방을 사용 하거나 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b679-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="8b679-117">대화방을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Configure 채팅방 In Lync Server 2013](lync-server-2013-configure-rooms.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b679-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

