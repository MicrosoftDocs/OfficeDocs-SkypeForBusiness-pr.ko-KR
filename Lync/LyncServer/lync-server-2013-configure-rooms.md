---
title: 'Lync Server 2013: 대화방 구성'
description: 'Lync Server 2013: 대화방을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9f5b2ece8cf436fe69c000da73871cb92686d82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542774"
---
# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="06ceb-103">Lync Server 2013에서 대화방 구성</span><span class="sxs-lookup"><span data-stu-id="06ceb-103">Configure rooms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06ceb-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="06ceb-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="06ceb-105">영구 대화방 구성은 일반적으로 사용자 또는 기타 중앙 팀에서 Windows PowerShell 명령줄 인터페이스를 사용 하 여 처리 합니다. 일반적으로 관리자는 대화방을 관리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-105">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="06ceb-106">그러나 채팅방을 만들고 관리 해야 하는 경우에는 Windows PowerShell 명령줄 인터페이스를 사용 하거나, 자신을 채팅방에 구성원으로 추가 하 고 Lync 2013 클라이언트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-106">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="06ceb-107">Windows PowerShell 명령줄 인터페이스를 사용 하 여 대화방을 구성 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)의 "대화방 관리"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06ceb-107">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="06ceb-108">채팅방에서 데이터 관리</span><span class="sxs-lookup"><span data-stu-id="06ceb-108">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="06ceb-109">영구 채팅 서버를 사용 하면 사용자가 영구 채팅방에 메시지를 게시 하 여 공동 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-109">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="06ceb-110">데이터는 서버에 유지 되며, 룸 구성원은 기록 데이터를 포함 하 여 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-110">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="06ceb-111">그러나 다른 역할을 가진 사용자는 다음 목록에 나와 있는 것 처럼 영구 데이터에 대 한 액세스 권한을 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-111">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="06ceb-p103">관리자는 데이터베이스가 너무 크게 증가하지 않도록 방지하기 위해 채팅방에서 이전 콘텐츠(예: 특정 일 수 이전에 게시된 콘텐츠)를 삭제할 수 있습니다. 또는 특정 채팅방에 적합하지 않은 것으로 고려되는 메시지를 제거하거나 교체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="06ceb-114">메시지 작성자를 포함하여 최종 사용자는 채팅방의 콘텐츠를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-114">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="06ceb-p104">채팅방 관리자는 방을 사용하지 않도록 설정할 수 있지만 방을 삭제할 수는 없습니다. 채팅방을 만든 후에는 관리자만 방을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="06ceb-117">메시지가 삭제되면 작업을 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-117">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="06ceb-118">하지만 백업이 있으면 삭제된 메시지를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-118">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="06ceb-119">영구 채팅 준수 서버가 사용 되도록 설정 된 경우 이전 메시지는 준수 데이터베이스에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-119">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06ceb-120">이 대화방 데이터 사용량은 관리자 역할이 포함 된 경우를 제외 하 고 Lync Server 2013, 영구 채팅 서버 API 응용 프로그램에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-120">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="06ceb-121">영구 채팅 서버 API는 관리자의 작업을 수행 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-121">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="06ceb-122">Lync Server 관리 셸에서 이러한 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ceb-122">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

