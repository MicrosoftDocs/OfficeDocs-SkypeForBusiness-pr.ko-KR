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

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>Lync Server 2013에서 메시지 삭제 또는 오래된 메시지 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-05_

영구 채팅 관리자는 영구 채팅방에서 메시지를 삭제할 수 있으며 필요에 따라 다른 메시지로 바꿀 수 있습니다. 또한 관리자는 진행 중인 유지 관리의 일부로 오래 된 메시지를 제거 하 여 데이터베이스의 증가를 최소화할 수 있습니다. 예를 들어 다음 Windows PowerShell 명령은 사용자 kenmyer@litwareinc.com에서 게시 한 모든 메시지를 It 채팅방의 채팅방에서 제거 합니다.

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

이 예제에서는 제거 된 메시지를 메시지가 더 이상 사용할 수 없는 메모로 바꿉니다.

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

자세한 내용은 [제거 CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

