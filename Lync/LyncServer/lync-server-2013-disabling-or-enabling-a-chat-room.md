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
ms.openlocfilehash: 96ad55bd6396cdac9b30441eb8b41bebaba834ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Lync Server 2013에서 대화방을 사용 하지 않도록 설정 하거나 사용 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-05_

영구 채팅방의 항목이 더 이상 관련이 없으면 사용자가 대화방을 사용 하지 않도록 설정할 수 있습니다. 대화방을 사용 하지 않도록 설정 하면 모든 구성원이 대화방에서 즉시 연결이 해제 됩니다. 채팅방을 사용 하지 않도록 설정한 후에는 사용자가 대화방 검색에서 해당 채팅방을 다시 가입 하거나 검색할 수 없습니다.

사용 하지 않도록 설정 된 대화방은 나중에 영구 채팅 관리자에 의해 사용 하도록 설정할 수 있습니다. 대화방을 사용하지 않도록 설정하면 해당 구성원 자격 목록 및 기타 설정이 보존됩니다. 대화방을 다시 사용 하도록 설정 하는 경우에는 설정을 수동으로 다시 만들지 않아도 됩니다.

대화방의 기록이 유지 되는 경우 (대화방 기록 지 속성은 해당 종류 내의 모든 채팅방에 적용 되는 종류의 선택적 설정), 기본적으로는 유지 되지만, 해당 범주의 **채팅 사용 내역** 을 false로 설정 하 여 해제할 수는 있지만, 채팅방을 사용 하지 않도록 설정 하면 콘텐츠가 보존 됩니다. 그러나 대화방을 사용할 수 없는 상태로 유지 하는 동안에는 검색에 해당 콘텐츠가 표시 되지 않습니다. 나중에 대화방을 사용 하도록 설정 하면 사용자는 대화방을 사용 하지 않도록 설정 하기 전에 게시 된 메시지를 검색할 수 있습니다.

Windows PowerShell 명령줄 인터페이스를 사용 하 여 대화방을 비활성화 하 고 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)의 "대화방 관리"를 참조 하십시오. 채팅방을 사용 하지 않도록 설정 하려면 다음과 같은 명령을 사용 합니다.

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

대화방을 사용 하려면 Disabled 속성을 False로 설정 합니다.

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Lync Server 제어판을 사용 하 여 대화방을 사용 하거나 사용 하지 않도록 설정할 수 없습니다.

대화방을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Configure 채팅방 In Lync Server 2013](lync-server-2013-configure-rooms.md) 을 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

