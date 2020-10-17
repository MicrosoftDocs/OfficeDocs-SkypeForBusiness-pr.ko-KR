---
title: 'Lync Server 2013: 한 범주에서 다른 범주로 채팅방 이동'
description: 'Lync Server 2013: 한 범주에서 다른 범주로 채팅방을 이동 하는 중입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4066732a90a94414b55d6a567fde0d496e4faf13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542002"
---
# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="6c833-103">Lync Server 2013에서 한 범주에서 다른 범주로 대화방 이동</span><span class="sxs-lookup"><span data-stu-id="6c833-103">Moving a chat room from one category to another in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c833-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6c833-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6c833-105">채팅방을 만든 후에 영구 채팅방의 범주를 변경 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c833-105">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="6c833-106">하지만 채팅방 관리자가 다른 범주에 대해 **작성자** 권한을 갖고 있는 경우 방을 한 범주에서 다른 범주로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c833-106">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="6c833-107">방은 삭제되지 않고 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6c833-107">The room is not deleted and recreated.</span></span> <span data-ttu-id="6c833-108">데이터베이스 내의 연결에 대한 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="6c833-108">It is a change of association within the database.</span></span>

<span data-ttu-id="6c833-p102">채팅방 범주 변경은 드물게 수행됩니다. 범주는 해당 채팅방에 대해 허용되는 구성원 자격을 결정하므로 채팅방을 다른 범주로 이동하면 새 범주에 따라 더 이상 지원되지 않는 모든 SACL(시스템 액세스 제어 목록)이 삭제됩니다. 예를 들어 사용자가 특정 방의 구성원이었는데 새 범주에서는 더 이상 **AllowedMember**가 아닌 경우 방 구성원 자격이 수정되어 이 사용자가 방에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c833-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="6c833-112">Windows PowerShell 명령줄 인터페이스를 사용 하 여 대화방을 이동 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)의 "대화방 관리"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c833-112">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="6c833-113">대화방을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Configure 채팅방 In Lync Server 2013](lync-server-2013-configure-rooms.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c833-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

