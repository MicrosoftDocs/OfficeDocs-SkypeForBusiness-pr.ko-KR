---
title: 'Lync Server 2013: 메시지 삭제 또는 오래된 메시지 제거'
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
ms.openlocfilehash: d8040d52690628b6085727d6a1fdac9288b94d5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="4c4d2-102">Lync Server 2013에서 메시지 삭제 또는 오래된 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="4c4d2-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c4d2-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4c4d2-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4c4d2-104">영구 채팅 관리자는 영구 채팅방에서 메시지를 삭제할 수 있으며 필요에 따라 다른 메시지로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c4d2-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="4c4d2-105">또한 관리자는 진행 중인 유지 관리의 일부로 오래 된 메시지를 제거 하 여 데이터베이스의 증가를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c4d2-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="4c4d2-106">예를 들어 다음 Windows PowerShell 명령은 사용자 kenmyer@litwareinc.com에서 게시 한 모든 메시지를 It 채팅방의 채팅방에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c4d2-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="4c4d2-107">이 예제에서는 제거 된 메시지를 메시지가 더 이상 사용할 수 없는 메모로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4c4d2-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="4c4d2-108">자세한 내용은 [제거 CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c4d2-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

