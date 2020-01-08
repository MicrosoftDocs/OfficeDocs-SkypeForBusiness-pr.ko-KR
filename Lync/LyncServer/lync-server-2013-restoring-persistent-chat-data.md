---
title: 'Lync Server 2013: 영구 채팅 데이터 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed69938186de2aebf6268168e663abcb125ad86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 데이터 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-18_

영구 채팅방 콘텐츠는 mgc .mdf (영구 채팅 데이터베이스)에 저장 됩니다. 정기적으로 백업 해야 하는 비즈니스에 중요 한 데이터입니다. 채팅방 콘텐츠, 사용자 및 그룹과 같은 주체와 채팅방 콘텐츠를 채팅 하는 데 사용 하는 역할 및 액세스 권한 외에도 영구 채팅 데이터베이스에 저장 됩니다.

영구 채팅 데이터를 복원 하는 방법은 백업 하는 데 사용한 방법에 따라 다릅니다.

  - SQL Server 백업 절차를 사용 하는 경우 SQL Server restore 프로시저를 사용 해야 합니다.

  - **CsPersistentChatData** cmdlet을 사용 하 여 영구 채팅 데이터를 백업한 경우 **CsPersistentChatData** cmdlet을 사용 하 여 데이터를 복원 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

