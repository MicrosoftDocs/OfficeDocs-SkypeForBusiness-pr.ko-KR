---
title: 'Lync Server 2013: 새 채팅방 만들기 및 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1442454b2afb129fda50d98ed17ccdc2c7ba35c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="88e8c-102">Lync Server 2013에서 새 채팅방 만들기 및 편집</span><span class="sxs-lookup"><span data-stu-id="88e8c-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e8c-103">_**마지막으로 수정한 주제:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="88e8c-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="88e8c-104">영구 채팅방 구성은 일반적으로 사용자가 처리 합니다. 영구 채팅 관리자는 일반적으로 채팅방을 구성 하거나 관리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="88e8c-105">회의실을 관리 하기 위한 Windows PowerShell cmdlet은 **CsPersistentChatAdministrator** 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="88e8c-106">지정 된 범주의 **작성자** 인 사용자는 Lync 클라이언트를 사용 하 여 회의실을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="88e8c-107">특정 채팅방에 대 한 관리자로 지정 된 사용자는 대화방 속성 또는 구성원 편집과 같은 채팅방의 지속적인 관리를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="88e8c-108">영구 채팅 관리자도 작성자가 될 수 있으며 작성자에 게 적용 되는 제한 사항이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="88e8c-109">선택적으로 영구 채팅 관리자 인 경우 Windows PowerShell cmdlet을 사용 하는 대신 사용자 인터페이스를 통해 채팅방을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="88e8c-110">이렇게 하려면 SIP-영구 채팅 서버에 대 한 관리자를 사용 하도록 설정한 다음 Lync 클라이언트를 사용 하 여 채팅방을 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="88e8c-111">사용자를 위해 사용자 지정 채팅방 관리 워크플로를 만들려는 경우 사용자를 Lync 클라이언트의 사용자 지정 솔루션으로 리디렉션하도록 영구 채팅 서버 구성에서 **RoomManagementUrl** 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="88e8c-112">Windows PowerShell 명령줄 인터페이스를 사용 하 여 채팅방을 구성 하는 방법에 대 한 자세한 내용은 [Windows powershell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)에서 "Room 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88e8c-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="88e8c-113">채팅방을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 회의실 구성을](lync-server-2013-configure-rooms.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88e8c-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88e8c-114">영구 채팅 서버는 사용자가 특정 사이트에 대 한 채팅방을 만들고 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="88e8c-115">그러나 같은 토폴로지 내에 있는 다른 사이트의 채팅방을 만들거나 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="88e8c-116">조직의 모든 사이트에 대 한 채팅방 작성자 및 관리자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="88e8c-117">Lync Server Survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 채팅방 카드를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e8c-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

