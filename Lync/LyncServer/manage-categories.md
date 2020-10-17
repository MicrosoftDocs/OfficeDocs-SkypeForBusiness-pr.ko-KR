---
title: 범주 관리
description: 종류 관리
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf335b96c455647ebeb665364944e15d2e463fbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545934"
---
# <a name="manage-categories"></a><span data-ttu-id="a82b3-103">범주 관리</span><span class="sxs-lookup"><span data-stu-id="a82b3-103">Manage categories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a82b3-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a82b3-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a82b3-105">새 영구 채팅 서버 범주를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a82b3-105">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a82b3-106">PersistentChatPoolFqdn은 영구 채팅 서버 풀이 둘 이상 있는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82b3-106">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="a82b3-107">기존 영구 채팅 서버 범주를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="a82b3-107">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="a82b3-108">Windows PowerShell: AllowedMembers, DeniedMembers 및 생성기를 동시에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a82b3-108">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="a82b3-109">Creators는 AllowedMembers에서 DeniedMembers를 제외한 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82b3-109">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="a82b3-110">범주의 속성을 구성원과 작성자로 동시에 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a82b3-110">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="a82b3-111">범주 작성, 가져오기, 설정 또는 제거</span><span class="sxs-lookup"><span data-stu-id="a82b3-111">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="a82b3-112">새 범주를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a82b3-112">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="a82b3-113">범주를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="a82b3-113">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="a82b3-114">또는</span><span class="sxs-lookup"><span data-stu-id="a82b3-114">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="a82b3-115">범주를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a82b3-115">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="a82b3-116">또는</span><span class="sxs-lookup"><span data-stu-id="a82b3-116">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="a82b3-117">범주를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a82b3-117">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="a82b3-118">또는</span><span class="sxs-lookup"><span data-stu-id="a82b3-118">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

