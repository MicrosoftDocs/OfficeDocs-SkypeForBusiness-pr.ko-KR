---
title: 'Lync Server 2013: 영구 채팅 데이터베이스 백업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ffb99effcf0a42bbddefd7151aa40a8d691d9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 데이터베이스 백업

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-17_

영구 채팅방 콘텐츠는 Mgc .mdf (영구 채팅 데이터베이스)에 저장 됩니다. 정기적으로 백업 해야 하는 비즈니스에 중요 한 데이터입니다. 채팅방 콘텐츠 외에도 영구 채팅 데이터베이스는 사용자 및 사용자 그룹과 같은 주체에 대 한 정보를 저장 하 고 채팅방과 채팅방에 대 한 역할 및 액세스를 유지 합니다.

영구 채팅 데이터를 백업 하는 방법에는 두 가지가 있습니다.

  - SQL Server 백업

  - 영구 `Export-CsPersistentChatData` 채팅 데이터를 파일로 내보내는 cmdlet

SQL Server 백업을 사용 하 여 만든 데이터에는 훨씬 더 많은 디스크 공간이 필요 하지만 `Export-CsPersistentChatData`, sql server 백업에는 관리자가 익숙한 프로시저 일 가능성이 더 높습니다.

</div>

<span> </span>

</div>

</div>

</div>

