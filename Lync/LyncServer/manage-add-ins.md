---
title: 추가 기능 관리
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 465f71a8221ce273574c5cf602146272b34f0cf7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a><span data-ttu-id="9cf94-102">추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="9cf94-102">Manage add-ins</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cf94-103">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9cf94-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9cf94-104">새 영구 채팅 서버 추가 기능을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9cf94-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="9cf94-105">추가 기능 만들기, 가져오기, 설정 또는 제거</span><span class="sxs-lookup"><span data-stu-id="9cf94-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="9cf94-106">새로운 추가 기능을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9cf94-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9cf94-107">PersistentChatPoolFqdn &lt;String&gt; 은 영구 채팅 서버 풀이 둘 이상 있는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cf94-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="9cf94-108">추가 기능을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="9cf94-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="9cf94-109">또는</span><span class="sxs-lookup"><span data-stu-id="9cf94-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="9cf94-110">추가 기능을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9cf94-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="9cf94-111">또는</span><span class="sxs-lookup"><span data-stu-id="9cf94-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="9cf94-112">추가 기능을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="9cf94-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="9cf94-113">또는</span><span class="sxs-lookup"><span data-stu-id="9cf94-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

