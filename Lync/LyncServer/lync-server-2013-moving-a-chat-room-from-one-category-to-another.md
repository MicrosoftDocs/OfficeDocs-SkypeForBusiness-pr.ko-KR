---
title: 'Lync Server 2013: 범주 간 채팅방 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Lync Server 2013에서 범주 간 채팅방 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

채팅방을 만든 후 영구 채팅방의 범주를 변경 하지 않는 것이 좋습니다. 그러나 채팅방 관리자에 다른 범주에 대 한 **작성자** 권한이 있는 경우 한 범주에서 다른 범주로 방을 이동할 수 있습니다. 룸은 삭제 되었다가 다시 생성 되지 않습니다. 데이터베이스 내의 연결을 변경 하는 것입니다.

채팅방 범주를 변경 하는 것은 거의 수행 하지 않아야 합니다. 범주는 채팅방에 대해 허용 된 구성원 자격을 결정 하므로 채팅방을 다른 범주로 이동 하면 새 범주에서 더 이상 지원 되지 않는 모든 Sacl (시스템 액세스 제어 목록)이 제거 됩니다. 예를 들어 사용자가 채팅방의 구성원이 고 더 이상 새 범주에 있는 **Allowedmember** 가 아닌 경우 룸 구성원 자격이 수정 되 고 사용자가 채팅방에서 제거 됩니다.

Windows PowerShell 명령줄 인터페이스를 사용 하 여 채팅방을 이동 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)에서 "room 관리"를 참조 하세요.

채팅방을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 회의실 구성을](lync-server-2013-configure-rooms.md) 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

