---
title: 'Lync Server 2013: 인스턴트 메시지에 사용자 지정 텍스트 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 466eac15cf75728578e7d517d15ddb222d1c4b70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521365"
---
# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="dffd5-102">Lync Server 2013의 인스턴트 메시지에 사용자 지정 텍스트 추가</span><span class="sxs-lookup"><span data-stu-id="dffd5-102">Adding custom text to instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dffd5-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="dffd5-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="dffd5-104">IMWarning 매개 변수를 사용 하 여 **새-csclientpolicy** 또는 **Set-Csclientpolicy** lync Server Management Shell cmdlet을 사용 하 여 모든 Lync 2013 IM (인스턴트 메시징) 대화 시작 부분에 고 지 사항이 나 경고를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffd5-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="dffd5-105">다음 예의 명령은 새 IM 대화가 시작 될 때마다 대화 창 위쪽에 보안 알림을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffd5-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="dffd5-106">**Grant-CSClientPolicy**를 사용하여 새로운 이 정책을 사용자에게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dffd5-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="dffd5-107">자세한 내용은 Lync Server 관리 셸 설명서에서 **New-csclientpolicy** 및 **Grant-csclientpolicy** 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dffd5-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

