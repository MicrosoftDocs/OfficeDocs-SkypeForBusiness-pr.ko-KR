---
title: 범주 관리
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7632c0de3c17c921af05a8daa225364727a3a3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a><span data-ttu-id="e4bac-102">범주 관리</span><span class="sxs-lookup"><span data-stu-id="e4bac-102">Manage categories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4bac-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e4bac-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e4bac-104">새 영구 채팅 서버 범주를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e4bac-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4bac-105">PersistentChatPoolFqdn는 둘 이상의 영구 채팅 서버 풀이 있는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4bac-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="e4bac-106">기존 영구 채팅 서버 범주를 변경 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4bac-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="e4bac-107">Windows PowerShell: AllowedMembers, DeniedMembers, 크리에이터을 동시에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4bac-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="e4bac-108">작성자는 AllowedMembers의 하위 집합에서 DeniedMembers를 뺀 값 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4bac-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="e4bac-109">멤버 및 작성자와 동시에 범주의 속성을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4bac-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="e4bac-110">범주 만들기, 가져오기, 설정 또는 제거</span><span class="sxs-lookup"><span data-stu-id="e4bac-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="e4bac-111">새 범주를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e4bac-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="e4bac-112">범주를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="e4bac-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="e4bac-113">또는</span><span class="sxs-lookup"><span data-stu-id="e4bac-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="e4bac-114">범주를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e4bac-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="e4bac-115">또는</span><span class="sxs-lookup"><span data-stu-id="e4bac-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="e4bac-116">범주를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e4bac-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="e4bac-117">또는</span><span class="sxs-lookup"><span data-stu-id="e4bac-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

