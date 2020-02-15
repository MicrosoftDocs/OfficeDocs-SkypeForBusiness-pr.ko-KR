---
title: 'Lync Server 2013: 영구 채팅 데이터베이스 백업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98d4d69a09ad58d4578c0636f7e6bce54497cb9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 데이터베이스 백업

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-17_

영구 채팅방 콘텐츠는 영구 채팅 데이터베이스 (Mgc .mdf)에 저장 됩니다. 정기적으로 백업 해야 하는 업무상 중요 한 데이터입니다. 대화방 콘텐츠 외에도 영구 채팅 데이터베이스에는 주체에 대 한 정보 (예: 사용자 및 사용자 그룹)와 채팅방과 채팅방을 채팅 하는 데 사용할 수 있는 역할과 액세스 권한이 저장 됩니다.

두 가지 방법으로 영구 채팅 데이터를 백업할 수 있습니다.

  - SQL Server 백업

  - 영구 `Export-CsPersistentChatData` 채팅 데이터를 파일로 내보내는 cmdlet

SQL Server 백업을 사용 하 여 만든 데이터에는 만든 시간 보다 훨씬 더 많은 디스크 공간이 필요 하지만 `Export-CsPersistentChatData`, sql Server 백업은 관리자가 익숙하게 사용 하는 절차 일 가능성이 높습니다.

</div>

<span> </span>

</div>

</div>

</div>

