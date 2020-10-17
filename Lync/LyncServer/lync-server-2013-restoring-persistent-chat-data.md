---
title: 'Lync Server 2013: 영구 채팅 데이터 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dfe3a6c23e9de159c9024d660caf3f04fe648b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511415"
---
# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="f1b47-102">Lync Server 2013에서 영구 채팅 데이터 복원</span><span class="sxs-lookup"><span data-stu-id="f1b47-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1b47-103">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="f1b47-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="f1b47-104">영구 채팅방 콘텐츠는 영구 채팅 데이터베이스 (mgc .mdf)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b47-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="f1b47-105">정기적으로 백업 해야 하는 업무상 중요 한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1b47-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="f1b47-106">대화방 콘텐츠 (예: 사용자 및 그룹)와 채팅방 및 채팅방 콘텐츠를 채팅 하는 데 사용할 수 있는 역할 및 액세스와 함께 영구 채팅 데이터베이스에도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b47-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="f1b47-107">영구 채팅 데이터를 복원 하는 방법은 백업 하는 데 사용한 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f1b47-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="f1b47-108">SQL Server 백업 절차를 사용한 경우 SQL Server 복원 절차를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b47-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="f1b47-109">**Export-cspersistentchatdata** cmdlet을 사용 하 여 영구 채팅 데이터를 백업한 경우 **export-cspersistentchatdata** cmdlet을 사용 하 여 데이터를 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b47-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

