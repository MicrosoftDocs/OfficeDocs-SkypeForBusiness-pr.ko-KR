---
title: 'Lync Server 2013: Office Web Apps 서버에서 사용할 클라이언트 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4b9b881d0f7d469c924a0ba032071092bddbbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="4c42e-102">Office Web Apps 서버에서 사용할 Lync Server 2013의 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="4c42e-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c42e-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="4c42e-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="4c42e-104">사용자가 Office Web App Server의 전체 기능을 경험할 수 있도록 하려면 Microsoft Lync 2013에서 해당 사용자를 업그레이드 해야 합니다. Lync 2013 사용자만이 실제 PowerPoint 프레젠테이션과 관계 없이 PowerPoint 슬라이드 스크롤을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="4c42e-105">(즉,이 사용자는 실제 프레젠테이션을 진행 하는 것을 방해 하지 않고 언제 든 지 프레젠테이션의 모든 슬라이드를 볼 수 있습니다.) Lync 2013를 사용 하지 않는 사용자는 계속 해 서 온라인 회의에 참가 하 여 PowerPoint 프레젠테이션을 볼 수 있습니다. 그러나 슬라이드를 독립적으로 스크롤하거나 슬라이드 전환을 표시 하거나 포함 된 비디오를 볼 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="4c42e-106">이러한 접근 권한 값은 Lync 2013 사용자가 항상 사용할 수 있다는 점에 유의 하십시오. 이는 PowerPoint 발표자가 Microsoft Lync 2010을 실행 하는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="4c42e-107">Lync 2010를 실행 하는 사용자가 PowerPoint 프레젠테이션을 호스트 하는 경우 lync Server 2013에서 Office Web Apps 서버를 조정 하 여 Lync 2013 사용자가 해당 프레젠테이션의 Office Web Apps 서버 버전을 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="4c42e-108">Office Web Apps 서버는 Lync 2013 이외의 클라이언트를 실행 하는 사용자를 위해 PowerPoint 서비스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="4c42e-109">대신 사용자가 회의 서버 서비스에 연결 하 고 Microsoft Lync Server 2010에서와 동일한 방식으로 PowerPoint 프레젠테이션을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="4c42e-110">이는 또한 이러한 사용자가 Lync Server 2010에서 제공 하는 제한 된 기능에만 액세스할 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="4c42e-111">Office Web Apps 서버에 대 한 클라이언트 구성이 필요 하지는 않지만 (사용자를 Lync 2013로 업그레이드 하는 것 외에), 전화 회의 참석자가 Internet Explorer 9로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="4c42e-112">Internet Explorer 8을 사용 하 여 회의에 액세스할 수 있지만, 웹 브라우저를 사용 하는 데는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="4c42e-113">예를 들어 Internet Explorer 8 사용자는 PowerPoint 스테이지의 크기를 사용자 지정 크기로 조정할 수 없게 됩니다. 대신 세 가지 미리 정의 된 스테이지 크기 중 하나를 사용 하는 것으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="4c42e-114">마찬가지로 Internet Explorer 8 사용자는 미디어 파일을 재생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c42e-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

