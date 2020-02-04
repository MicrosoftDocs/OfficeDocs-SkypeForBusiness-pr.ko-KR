---
title: 'Lync Server 2013: 채팅방 비활성화 또는 활성화'
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
ms.openlocfilehash: a3ed23319631dd8ab51131fe9a8d7a9099e35d18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Lync Server 2013에서 채팅방 비활성화 또는 활성화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-05_

영구 채팅방의 항목이 더 이상 관련이 없다면 사용자가 채팅방을 사용 하지 않도록 설정할 수 있습니다. 채팅방을 사용 하지 않도록 설정 하면 모든 구성원이 채팅방에서 바로 연결이 해제 됩니다. 채팅방을 사용 하지 않도록 설정한 후에는 사용자가 다시 참가 하거나 채팅방 검색에서 찾을 수 없습니다.

사용 하지 않도록 설정 된 채팅방은 나중에 영구 채팅 관리자가 설정할 수 있습니다. 채팅방을 사용 하지 않도록 설정한 경우, 해당 채팅방의 회원 가입 목록 및 기타 설정이 유지 됩니다. 채팅방을 다시 사용 하도록 설정 하는 경우 수동으로 설정을 다시 만들 필요가 없습니다.

채팅방의 기록이 계속 유지 되는 경우 (채팅방 변경 내용 유지는 범주 내의 모든 채팅방에 적용 되는 범주에 대 한 선택 사항 이지만, 기본값은 유지 되지만, 범주의 **채팅 가능 내역** 을 false로 설정 하 여 해제할 수 있음), 채팅방을 사용 하지 않도록 설정한 경우 콘텐츠가 보존 됨을 의미 합니다. 그러나 대화방을 사용할 수 없는 상태로 유지 하는 동안에는 검색에 해당 콘텐츠가 표시 되지 않습니다. 나중에 채팅방을 사용 하도록 설정 하는 경우 사용자는 채팅방을 사용 하지 않도록 설정 하기 전에 게시 된 메시지를 검색할 수 있습니다.

Windows PowerShell 명령줄 인터페이스를 사용 하 여 채팅방을 사용 하지 않도록 설정 하 고 사용 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)에서 "Room 관리"를 참조 하세요. 채팅방을 사용 하지 않도록 설정 하려면 다음과 같은 명령을 사용 합니다.

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

채팅방을 사용 하도록 설정 하려면 사용 안 함 속성을 False로 설정 합니다.

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

회의실은 Lync Server 제어판을 사용 하 여 사용 하거나 사용 하지 않도록 설정할 수 없습니다.

채팅방을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 회의실 구성을](lync-server-2013-configure-rooms.md) 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

