---
title: 'Lync Server 2013: 채팅방 구성'
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
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="9e56b-102">Lync Server 2013에서 채팅방 구성</span><span class="sxs-lookup"><span data-stu-id="9e56b-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e56b-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9e56b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9e56b-104">영구 채팅방 구성은 일반적으로 사용자 또는 다른 중앙 팀에서 Windows PowerShell 명령줄 인터페이스를 사용 하 여 처리 합니다. 일반적으로 관리자는 채팅방을 관리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="9e56b-105">그러나 채팅방을 만들고 관리 해야 하는 경우 Windows PowerShell 명령줄 인터페이스를 사용 하거나 채팅방의 구성원으로 자신을 추가 하 고 Lync 2013 클라이언트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="9e56b-106">Windows PowerShell 명령줄 인터페이스를 사용 하 여 채팅방을 구성 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)에서 "Room 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e56b-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="9e56b-107">채팅방에서 데이터 관리</span><span class="sxs-lookup"><span data-stu-id="9e56b-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="9e56b-108">영구 채팅 서버를 통해 사용자는 영구 채팅방에 메시지를 게시 하 여 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="9e56b-109">데이터는 서버에 유지 되며, 룸 구성원은 기록 데이터를 포함 하 여 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="9e56b-110">그러나 다른 역할의 사용자는 다음 목록에 나온 것 처럼 영구 데이터에 대 한 액세스 권한이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="9e56b-111">관리자는 모든 채팅방에서 이전 콘텐츠 (예: 특정 날짜 이전에 게시 된 콘텐츠)를 삭제 하 여 데이터베이스가 너무 커지지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="9e56b-112">또는 특정 채팅방에 적합 하지 않은 것으로 간주 되는 메시지를 제거 하거나 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="9e56b-113">메시지 작성자를 비롯 한 최종 사용자는 채팅방에서 콘텐츠를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="9e56b-114">채팅방 관리자는 채팅방을 사용 하지 않도록 설정할 수 있지만 회의실을 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="9e56b-115">관리자만이 채팅방을 만든 후 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="9e56b-116">메시지가 삭제 되 면 작업을 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="9e56b-117">그러나 백업이 있으면 삭제 된 메시지를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="9e56b-118">영구 채팅 준수 서버를 사용 하는 경우 이전 메시지가 준수 데이터베이스에서 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e56b-119">이 채팅방 데이터 사용량은 관리자 역할이 관련 된 경우를 제외 하 고 Lync Server 2013, 영구 채팅 서버 API 응용 프로그램에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="9e56b-120">영구 채팅 서버 API는 관리자의 작업을 수행 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="9e56b-121">Lync Server 관리 셸에서 이러한 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e56b-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

