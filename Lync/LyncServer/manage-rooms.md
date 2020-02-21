---
title: 대화방 관리
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6c684544a9acff04b4f03a47dcb7b403503f7b3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="5583d-102">대화방 관리</span><span class="sxs-lookup"><span data-stu-id="5583d-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5583d-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5583d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5583d-104">새 영구 채팅 서버 대화방을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5583d-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5583d-105">다음 중 하나에 해당하는 경우 -PersistentChatPoolFqdn은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="5583d-106">영구 채팅 서버 풀은 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="5583d-107">범주에 풀 FQDN을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="5583d-108">추가하는 채팅방에 풀 FQDN을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5583d-109">기존 영구 채팅 서버 대화방을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="5583d-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="5583d-110">Windows PowerShell: 구성원, 관리자 및 발표자를 동시에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="5583d-111">이들은 모두 AllowedMembers의 일부로 추가되거나, 호스트 범주의 DeniedMembers로 제외될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="5583d-112">type=normal인 채팅방에는 발표자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="5583d-113">채팅방 만들기, 가져오기, 설정, 지우기 또는 제거</span><span class="sxs-lookup"><span data-stu-id="5583d-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="5583d-114">새 채팅방을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5583d-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="5583d-115">채팅방을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5583d-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="5583d-116">채팅방을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="5583d-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="5583d-117">또는</span><span class="sxs-lookup"><span data-stu-id="5583d-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="5583d-118">여기서, –filter는 이름 및 설명만 지원하며 이름/설명이 키워드 문자열과 일치하는 채팅방을 찾는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="5583d-119">PoolFqdn은 지정 된 영구 채팅 서버 풀에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5583d-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="5583d-120">채팅방을 지우거나 채팅방의 메시지를 지우려면</span><span class="sxs-lookup"><span data-stu-id="5583d-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="5583d-121">또는</span><span class="sxs-lookup"><span data-stu-id="5583d-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="5583d-122">채팅방을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="5583d-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="5583d-123">또는</span><span class="sxs-lookup"><span data-stu-id="5583d-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

