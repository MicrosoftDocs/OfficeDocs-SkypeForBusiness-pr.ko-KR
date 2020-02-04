---
title: 'Lync Server 2013: 채팅방 또는 범주 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Lync Server 2013에서 채팅방 또는 범주 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

영구 채팅방을 삭제할 수 있습니다. 더 이상 사용 하지 않는 채팅방이 있는 경우이 채팅방을 사용 하지 않도록 설정할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 채팅방 사용 또는 사용 안 함을](lync-server-2013-disabling-or-enabling-a-chat-room.md)참조 하세요.

영구 채팅 관리자는 사용 하지 않도록 설정 된 채팅방을 쿼리할 수 있으며, Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**를 사용 하 여 주기적으로 채팅방을 제거 하 고 영구적으로 삭제할 수 있습니다.

범주를 삭제할 수 있습니다. 그러나 범주를 삭제 하려면 먼저 그 아래에 있는 모든 채팅방을 삭제 하거나 채팅방을 새 범주로 이동 하 고 빈 범주를 삭제 하 고 남겨 두어야 합니다. 영구 채팅 서버에서는 채팅방을 포함 하는 범주를 삭제할 수 없습니다. 자세한 내용은 [Lync Server 2013에서 한 범주에서 다른 범주로 채팅방 이동을](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)참조 하세요.

Windows PowerShell 명령줄 인터페이스를 사용 하 여 빈 범주를 삭제 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)에서 "Room 관리"를 참조 하세요.

채팅방과 범주에 대 한 자세한 내용은 [Lync server 2013에서 회의실 구성을](lync-server-2013-configure-rooms.md) 참조 하 고 배포 설명서의 [lync server 2013에서 범주를 구성](lync-server-2013-configure-categories.md) 하세요.

</div>

<span> </span>

</div>

</div>

</div>

