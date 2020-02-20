---
title: 'Lync Server 2013: 새 음성 메일 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691374b2287029c21be88e25ab7a56ecce96a675
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="fa1ce-102">Lync Server 2013의 새로운 음성 메일 기능</span><span class="sxs-lookup"><span data-stu-id="fa1ce-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa1ce-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="fa1ce-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="fa1ce-104">Lync Server 2013에서는 음성 메일을 관리 하기 위한 향상 된 음성 메일 이스케이프 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa1ce-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="fa1ce-105">이 새로운 기능은 음성 메일로 통화가 라우팅된 경우를 검색하고, 사용자에게 통화에 응답할 기회를 주지 않고 통화가 사용자의 휴대폰 음성 메일로 즉시 라우팅되는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="fa1ce-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="fa1ce-106">이러한 시나리오는 사용자가 자신의 휴대폰에 동시 신호 울림을 설정하고 휴대폰이 꺼지거나, 배터리가 소진되었거나, 작동 범위 바깥에 있는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fa1ce-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="fa1ce-107">음성 메일 이스케이프는 통화가 사용자의 휴대폰 음성 메일에 의해 즉시 수신되었음을 확인하고, 휴대폰 음성 메일에 대한 통화 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="fa1ce-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="fa1ce-108">통화는 사용자의 다른 끝점에서 계속 신호가 울려서 사용자가 통화를 받을 수 있는 기회를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa1ce-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="fa1ce-109">사용자가 통화에 응답하지 않으면 통화가 회사의 음성 메일로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa1ce-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fa1ce-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa1ce-110">See Also</span></span>


[<span data-ttu-id="fa1ce-111">Lync Server 2013에서 음성 메일 이스케이프 구성</span><span class="sxs-lookup"><span data-stu-id="fa1ce-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="fa1ce-112">Lync Server 2013의 새로운 Enterprise Voice 기능</span><span class="sxs-lookup"><span data-stu-id="fa1ce-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

