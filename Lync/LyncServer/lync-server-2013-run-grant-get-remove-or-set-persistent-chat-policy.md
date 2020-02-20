---
title: 'Lync Server 2013: 영구 채팅 정책 실행, 부여, 가져오기, 제거 또는 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run, grant, get, remove, or set Persistent Chat Policy
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204810(v=OCS.15)
ms:contentKeyID: 48183857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85f28c4a358c0ccb09b62c7d453746f3a5570763
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-grant-get-remove-or-set-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="4c6eb-102">Lync Server 2013에서 영구 채팅 정책 실행, 부여, 가져오기, 제거 또는 설정</span><span class="sxs-lookup"><span data-stu-id="4c6eb-102">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c6eb-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4c6eb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4c6eb-104">새 영구 채팅 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4c6eb-104">To create a new Persistent Chat policy</span></span>

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

<span data-ttu-id="4c6eb-105">영구 채팅 정책을 부여 하려면</span><span class="sxs-lookup"><span data-stu-id="4c6eb-105">To grant Persistent Chat policy</span></span>

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="4c6eb-106">영구 채팅 정책을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="4c6eb-106">To get Persistent Chat policy</span></span>

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

<span data-ttu-id="4c6eb-107">영구 채팅 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="4c6eb-107">To remove Persistent Chat policy</span></span>

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="4c6eb-108">영구 채팅 정책을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="4c6eb-108">To set Persistent Chat policy</span></span>

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

</div>

<span> </span>

</div>

</div>

</div>

