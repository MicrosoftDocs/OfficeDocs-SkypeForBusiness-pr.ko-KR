---
title: 'Lync Server 2013: 호스팅된 Exchange 통합 메시징 통합'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Unified Messaging integration
ms:assetid: f4de0165-da3b-499e-98fc-28ddd0db02d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413027(v=OCS.15)
ms:contentKeyID: 48185829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fff608d74da3851f810b971f922bafd2e4c1f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="27eab-102">Lync Server 2013의 호스팅된 Exchange 통합 메시징 통합</span><span class="sxs-lookup"><span data-stu-id="27eab-102">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27eab-103">_**마지막으로 수정한 주제:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="27eab-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="27eab-104">이전 Lync Server 2013 릴리스는 Exchange UM (통합 메시징)의 *온-프레미스* 배포와 통합할 수 있도록 지원 되는 것 외에도 Lync server 2013에는 *호스팅된* Exchange UM과의 통합에 대 한 지원이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27eab-104">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="27eab-105">호스트 된 Exchange UM을 사용 하면 Lync Server 2013에서 사용자에 게 음성 메시지 일부 또는 전부를 Microsoft Exchange Online과 같은 호스팅된 Exchange 서비스 공급자로 전송 하 여 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27eab-105">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="27eab-106">Lync Server 2013 Enterprise Voice는 Exchange UM 인프라를 사용 하 여 전화 응답, 통화 알림, 음성 액세스 (음성 메일 포함) 및 자동 전화 교환 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27eab-106">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="27eab-107">세부 정보는 [통합 된 통합 메시징 및 Lync Server 2013 기능](lync-server-2013-features-of-integrated-unified-messaging.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27eab-107">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="27eab-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="27eab-108">In This Section</span></span>

  - [<span data-ttu-id="27eab-109">Lync Server 2013의 호스팅된 Exchange UM 아키텍처 및 라우팅</span><span class="sxs-lookup"><span data-stu-id="27eab-109">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="27eab-110">Lync Server 2013의 호스팅된 음성 메일 정책</span><span class="sxs-lookup"><span data-stu-id="27eab-110">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="27eab-111">Lync Server 2013의 호스팅된 Exchange 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="27eab-111">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="27eab-112">Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리</span><span class="sxs-lookup"><span data-stu-id="27eab-112">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="27eab-113">호스팅된 Exchange UM과 Lync Server 2013의 통합을 위한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="27eab-113">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

