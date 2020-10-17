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
ms.openlocfilehash: 5eec65c22465ee5a2198e7f7147db2d0d014cc2b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523145"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="a450b-102">Lync Server 2013에서 영구 채팅 데이터베이스 백업</span><span class="sxs-lookup"><span data-stu-id="a450b-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a450b-103">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="a450b-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="a450b-104">영구 채팅방 콘텐츠는 영구 채팅 데이터베이스 (Mgc .mdf)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a450b-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="a450b-105">정기적으로 백업 해야 하는 업무상 중요 한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="a450b-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="a450b-106">대화방 콘텐츠 외에도 영구 채팅 데이터베이스에는 주체에 대 한 정보 (예: 사용자 및 사용자 그룹)와 채팅방과 채팅방을 채팅 하는 데 사용할 수 있는 역할과 액세스 권한이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a450b-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="a450b-107">두 가지 방법으로 영구 채팅 데이터를 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a450b-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="a450b-108">SQL Server 백업</span><span class="sxs-lookup"><span data-stu-id="a450b-108">SQL Server Backup</span></span>

  - <span data-ttu-id="a450b-109">`Export-CsPersistentChatData`영구 채팅 데이터를 파일로 내보내는 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a450b-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="a450b-110">SQL Server 백업을 사용 하 여 만든 데이터에는 만든 시간 보다 훨씬 더 많은 디스크 공간이 필요 `Export-CsPersistentChatData` 하지만, Sql Server 백업은 관리자가 익숙하게 사용 하는 절차 일 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="a450b-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

