---
title: 'Lync Server 2013: 영구 채팅 정책 실행, 부여, 가져오기, 제거 또는 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run, grant, get, remove, or set Persistent Chat Policy
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204810(v=OCS.15)
ms:contentKeyID: 48183857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8465271c4bd2be3d6fc240811e61a61f20ac814
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-grant-get-remove-or-set-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="5e388-102">Lync Server 2013에서 영구 채팅 정책 실행, 부여, 가져오기, 제거 또는 설정</span><span class="sxs-lookup"><span data-stu-id="5e388-102">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e388-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5e388-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5e388-104">새 영구 채팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="5e388-104">To create a new Persistent Chat policy</span></span>

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

<span data-ttu-id="5e388-105">영구 채팅 정책 부여</span><span class="sxs-lookup"><span data-stu-id="5e388-105">To grant Persistent Chat policy</span></span>

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="5e388-106">영구 채팅 정책을 얻으려면</span><span class="sxs-lookup"><span data-stu-id="5e388-106">To get Persistent Chat policy</span></span>

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

<span data-ttu-id="5e388-107">영구 채팅 정책 제거</span><span class="sxs-lookup"><span data-stu-id="5e388-107">To remove Persistent Chat policy</span></span>

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="5e388-108">영구 채팅 정책을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5e388-108">To set Persistent Chat policy</span></span>

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

</div>

<span> </span>

</div>

</div>

</div>

