---
title: 'Lync Server 2013: 대화방 또는 범주 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0d849ce195b663b6f633a5b50aab32a547dd487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="9667b-102">Lync Server 2013에서 채팅방 또는 범주 삭제</span><span class="sxs-lookup"><span data-stu-id="9667b-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9667b-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9667b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9667b-104">영구 채팅방을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9667b-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="9667b-105">또한 더 이상 사용되지 않는 대화방이 있는 경우 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9667b-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="9667b-106">자세한 내용은 [Lync Server 2013에서 대화방 사용 안 함 또는 사용](lync-server-2013-disabling-or-enabling-a-chat-room.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9667b-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="9667b-107">영구 채팅 관리자는 사용 하지 않도록 설정 된 채팅방을 쿼리할 수 있으며 Windows PowerShell cmdlet, **clear-cspersistentchatroom**을 사용 하 여 대화방을 주기적으로 삭제 하 고 영구적으로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9667b-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="9667b-108">범주는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9667b-108">Categories can be deleted.</span></span> <span data-ttu-id="9667b-109">그러나 범주를 삭제하려면 먼저 범주 아래에 있는 모든 대화방을 삭제하거나 새 범주로 이동하여, 삭제 가능한 비어 있는 범주로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9667b-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="9667b-110">영구 채팅 서버에서는 채팅방이 포함 된 범주를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9667b-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="9667b-111">자세한 내용은 [Lync Server 2013에서 한 범주에서 다른 범주로 대화방 이동](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9667b-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="9667b-112">Windows PowerShell 명령줄 인터페이스를 사용 하 여 빈 범주를 삭제 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)의 "대화방 관리"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9667b-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="9667b-113">대화방 및 범주에 대 한 자세한 내용은 배포 설명서에서 lync server [2013의 대화방 구성](lync-server-2013-configure-rooms.md) 및 [lync server 2013의 범주 구성을](lync-server-2013-configure-categories.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9667b-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

