---
title: 'Lync Server 2013: 대화방 또는 범주 삭제'
description: 'Lync Server 2013: 대화방 또는 범주를 삭제 합니다.'
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
ms.openlocfilehash: 3ef89802171a1eeca7de18ff0a4eb8eb3895f1b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555374"
---
# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Lync Server 2013에서 채팅방 또는 범주 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

영구 채팅방을 삭제할 수 있습니다. 또한 더 이상 사용되지 않는 대화방이 있는 경우 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 대화방 사용 안 함 또는 사용](lync-server-2013-disabling-or-enabling-a-chat-room.md)을 참조 하십시오.

영구 채팅 관리자는 사용 하지 않도록 설정 된 채팅방을 쿼리할 수 있으며 Windows PowerShell cmdlet, **clear-cspersistentchatroom**을 사용 하 여 대화방을 주기적으로 삭제 하 고 영구적으로 삭제할 수 있습니다.

범주는 삭제할 수 있습니다. 그러나 범주를 삭제하려면 먼저 범주 아래에 있는 모든 대화방을 삭제하거나 새 범주로 이동하여, 삭제 가능한 비어 있는 범주로 만들어야 합니다. 영구 채팅 서버에서는 채팅방이 포함 된 범주를 삭제할 수 없습니다. 자세한 내용은 [Lync Server 2013에서 한 범주에서 다른 범주로 대화방 이동](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)을 참조 하십시오.

Windows PowerShell 명령줄 인터페이스를 사용 하 여 빈 범주를 삭제 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)의 "대화방 관리"를 참조 하십시오.

대화방 및 범주에 대 한 자세한 내용은 배포 설명서에서 lync server [2013의 대화방 구성](lync-server-2013-configure-rooms.md) 및 [lync server 2013의 범주 구성을](lync-server-2013-configure-categories.md) 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

