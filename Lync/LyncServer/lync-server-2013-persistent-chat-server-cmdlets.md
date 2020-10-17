---
title: 'Lync Server 2013: 영구 채팅 서버 cmdlet'
description: 'Lync Server 2013: 영구 채팅 서버 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server cmdlets
ms:assetid: 5aa59edb-db57-406f-9fbd-54bf1a55d31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204920(v=OCS.15)
ms:contentKeyID: 48184226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28016031ffd4efdc568999ec0a400d77bf628ba8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545174"
---
# <a name="persistent-chat-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ca116-103">Lync Server 2013의 영구 채팅 서버 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca116-103">Persistent Chat Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca116-104">_**마지막으로 수정 된 항목:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="ca116-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="ca116-105">영구 채팅 cmdlet을 사용 하면 Microsoft Lync Server 2013 영구 채팅 서비스 (이전에는 그룹 채팅 서비스)를 관리 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca116-105">The Persistent Chat cmdlets enable you to manage and configure the Microsoft Lync Server 2013 Persistent Chat service (formerly known as the Group Chat service).</span></span> <span data-ttu-id="ca116-106">영구 채팅을 사용 하면 사용자가 온라인 인스턴트 메시징 세션에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca116-106">Persistent Chat enables users to participate in online instant messaging sessions.</span></span> <span data-ttu-id="ca116-107">이러한 세션은 실시간으로 수행할 수 있지만 각 세션의 내용은 영구적입니다. 즉, 언제 든 지 이러한 대화를 모든 사용자가 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca116-107">Although these sessions can take place in real time, the content of each session is persistent; that means these conversations can be resumed by anyone at any time.</span></span>

<div>

## <a name="persistent-chat-cmdlets"></a><span data-ttu-id="ca116-108">영구 채팅 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca116-108">Persistent Chat Cmdlets</span></span>

<span data-ttu-id="ca116-109">영구 채팅 cmdlet을 사용 하면 Lync Server 영구 채팅 서비스를 관리 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca116-109">The Persistent Chat cmdlets enable you to manage and configure the Lync Server Persistent Chat service.</span></span>

<span data-ttu-id="ca116-110">**영구 채팅 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="ca116-110">**Persistent Chat Cmdlets**</span></span>

  - <span data-ttu-id="ca116-111">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-111">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-112">[Set-cspersistentchatactiveserver](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-112">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-113">[Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-113">[Get-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-114">[Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-114">[New-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-115">[Get-cspersistentchataddin을 제거 합니다.](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-115">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-116">[Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-116">[Set-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-117">[Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-117">[Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-118">[Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-118">[New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-119">[Get-cspersistentchatcategory을 제거 합니다.](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-119">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-120">[Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-120">[Set-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-121">[Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-121">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-122">[Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-122">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-123">[Get-cspersistentchatcomplianceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-123">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-124">[Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-124">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-125">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-125">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-126">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-126">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-127">[Get-cspersistentchatconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-127">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-128">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-128">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-129">[Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-129">[Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-130">[Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-130">[Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-131">[Get-cspersistentchateligibleprincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-131">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-132">[Get-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-132">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-133">[Get-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-133">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-134">[Get-cspersistentchatendpoint을 제거 합니다.](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-134">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-135">[Test-cspersistentchatmessage을 제거 합니다.](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-135">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-136">[Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-136">[Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-137">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-137">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-138">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-138">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-139">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-139">[New-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-140">[Grant-cspersistentchatpolicy을 제거 합니다.](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-140">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-141">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-141">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-142">[일반-Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-142">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-143">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-143">[Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-144">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-144">[New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-145">[Clear-cspersistentchatroom을 제거 합니다.](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-145">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-146">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-146">[Set-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ca116-147">[Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-147">[Get-CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="ca116-148">[Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca116-148">[Set-CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

