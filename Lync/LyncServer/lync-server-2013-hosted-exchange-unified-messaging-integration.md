---
title: 'Lync Server 2013: 호스팅된 Exchange 통합 메시징 통합'
description: 'Lync Server 2013: 호스팅된 Exchange 통합 메시징 통합'
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
ms.openlocfilehash: 980c0bc47258e9fae94ff623559342ca36eea145
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550124"
---
# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="44d2e-103">Lync Server 2013의 호스팅된 Exchange 통합 메시징 통합</span><span class="sxs-lookup"><span data-stu-id="44d2e-103">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44d2e-104">_**마지막으로 수정 된 항목:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="44d2e-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="44d2e-105">Exchange UM (통합 메시징)을 *온-프레미스* 배포와 통합 하기 위해 이전 lync server 2013 릴리스가 제공 되는 것 외에도 lync server 2013은 *호스팅된* exchange UM과의 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d2e-105">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="44d2e-106">호스팅된 Exchange UM을 사용 하면 Lync Server 2013에서 사용자에 게 음성 메시징을 제공 하 여 Microsoft Exchange Online과 같은 호스팅된 Exchange 서비스 공급자에 게 음성을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d2e-106">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="44d2e-107">Lync Server 2013 Enterprise Voice는 Exchange UM 인프라를 사용 하 여 전화 응답, 통화 알림, 음성 액세스 (음성 메일 포함) 및 자동 전화 교환 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d2e-107">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="44d2e-108">자세한 내용은 [통합 메시징 및 Lync Server 2013의 기능](lync-server-2013-features-of-integrated-unified-messaging.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="44d2e-108">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44d2e-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="44d2e-109">In This Section</span></span>

  - [<span data-ttu-id="44d2e-110">Lync Server 2013의 호스팅된 Exchange UM 아키텍처 및 라우팅</span><span class="sxs-lookup"><span data-stu-id="44d2e-110">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="44d2e-111">Lync Server 2013의 호스팅된 음성 메일 정책</span><span class="sxs-lookup"><span data-stu-id="44d2e-111">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="44d2e-112">Lync Server 2013의 호스팅된 Exchange 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="44d2e-112">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="44d2e-113">Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리</span><span class="sxs-lookup"><span data-stu-id="44d2e-113">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="44d2e-114">호스팅된 Exchange UM과 Lync Server 2013의 통합을 위한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="44d2e-114">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

