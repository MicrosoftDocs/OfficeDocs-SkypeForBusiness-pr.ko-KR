---
title: 'Lync Server 2013: 새 채팅방 만들기 또는 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 564db7b9d1bfaab00e51628377f330da05af17e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Lync Server 2013에서 새 채팅방 만들기 또는 편집

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-03-19_

영구 대화방 구성은 일반적으로 사용자가 처리 합니다. 영구 채팅 관리자는 일반적으로 대화방을 구성 하거나 관리 하지 않습니다. 대화방을 관리 하기 위한 Windows PowerShell cmdlet은 **CsPersistentChatAdministrator** 관리자만 사용할 수 있습니다.

지정 된 범주의 **작성자** 인 사용자는 Lync 클라이언트를 사용 하 여 대화방을 만들고 관리할 수 있습니다. 특정 대화방의 관리자로 지정된 사용자도 대화방 속성 또는 구성원과 같은 대화방의 지속적인 관리를 수행할 수 있습니다.

<div>


> [!TIP]  
> 영구 채팅 관리자도 작성자가 될 수 있으며 작성자에 게 적용 되는 제한 사항의 영향을 받지 않습니다.



</div>

선택적으로 영구 채팅 관리자는 Windows PowerShell cmdlet을 사용 하는 대신 사용자 인터페이스를 통해 대화방을 만들고 관리할 수 있습니다. 이 작업을 수행 하려면 영구 채팅 서버에 대해 관리자를 SIP-사용 하도록 설정한 다음 Lync 클라이언트를 사용 하 여 대화방을 만들고 관리 합니다.

사용자에 대해 사용자 지정 대화방 관리 워크플로를 만들려는 경우에는 사용자를 Lync 클라이언트에서 사용자 지정 솔루션으로 리디렉션하도록 영구 채팅 서버 구성에서 **RoomManagementUrl** 속성을 설정할 수 있습니다.

Windows PowerShell 명령줄 인터페이스를 사용 하 여 대화방을 구성 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)의 "대화방 관리"를 참조 하십시오.

대화방을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Configure 채팅방 In Lync Server 2013](lync-server-2013-configure-rooms.md) 을 참조 하십시오.

<div>


> [!NOTE]  
> 영구 채팅 서버를 사용 하면 사용자가 특정 사이트에 대해 채팅방을 만들고 관리할 수 있습니다. 그러나 동일한 토폴로지 내의 다른 사이트에서는 사용자가 채팅방을 만들거나 관리할 수 없습니다. 조직의 모든 사이트에 대해 대화방 작성자 및 관리자를 지정 해야 합니다.



</div>

<div>


> [!NOTE]  
> Lync Server Sba (survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 대화방 카드를 볼 수 없습니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

