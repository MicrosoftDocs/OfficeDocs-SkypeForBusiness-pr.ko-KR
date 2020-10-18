---
title: 'Lync Server 2013: 메시지 삭제 또는 오래 된 메시지 제거'
description: 'Lync Server 2013: 메시지를 삭제 하거나 사용 하지 않는 메시지를 제거 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 928e34d2ab52b02155568c7da96e4ac1d8154b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575824"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="7756a-103">Lync Server 2013에서 메시지 삭제 또는 오래 된 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="7756a-103">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7756a-104">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="7756a-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="7756a-105">영구 채팅 관리자는 영구 채팅방에서 메시지를 삭제할 수 있으며, 필요에 따라 다른 메시지로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7756a-105">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="7756a-106">관리자는 또한 지속적인 유지 관리의 일환으로 오래된 메시지를 삭제하여 데이터베이스 증가를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7756a-106">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="7756a-107">예를 들어 다음 Windows PowerShell 명령은 사용자 kenmyer@litwareinc.com에서 게시 한 It\ 대화방 대화방에서 모든 메시지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7756a-107">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="7756a-108">다음은 제거한 메시지를 더 이상 사용할 수 없음을 메모를 사용 하 여 바꾸는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="7756a-108">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="7756a-109">자세한 내용은 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7756a-109">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

