---
title: Lync Server 2013 호스팅된 Exchange UM 통합 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24139ad5294bf908a85b797300397fa8b2ac9140
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="9d9ca-102">Lync Server 2013의 호스팅된 Exchange UM 통합 지원</span><span class="sxs-lookup"><span data-stu-id="9d9ca-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d9ca-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9d9ca-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9d9ca-104">Lync Server 2013 ExUM 라우팅 응용 프로그램은 온-프레미스 환경의 UM (통합 메시징)과 Lync Server 2013 및 Exchange UM을 모두 엔터프라이즈 내에서 로컬로 설치 하거나,에 의해 호스팅되는 Exchange UM과 통합할 수 있도록 지원 합니다. 서비스 공급자 (다음 다이어그램에 표시 됨)</span><span class="sxs-lookup"><span data-stu-id="9d9ca-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="9d9ca-105">![온-프레미스 Lync Server Exchange UM 배포](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "온-프레미스 Lync Server Exchange UM 배포")</span><span class="sxs-lookup"><span data-stu-id="9d9ca-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="9d9ca-106">지원 되는 모드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-106">The following modes are supported:</span></span>

  - <span data-ttu-id="9d9ca-107">**온-프레미스 모드**   Lync Server 2013 및 Exchange UM은 모두 엔터프라이즈 내의 로컬 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="9d9ca-108">**크로스-프레미스 모드**   Lync Server 2013는 엔터프라이즈 내의 로컬 서버에 배포 되며 Exchange UM은 Microsoft exchange online 데이터 센터와 같은 온라인 서비스 공급자의 기능에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="9d9ca-109">**혼합 모드**   Lync Server 2013 배포에는 엔터프라이즈 내에서 Microsoft Exchange Server를 실행 하는 로컬 서버와 호스팅된 Exchange 서비스 데이터 센터에 있는 일부 사서함이 있는 사용자 사서함이 몇 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9d9ca-110">혼합 모드는 사용자를 호스트 된 Exchange UM로 마이그레이션하는 동안 전환 솔루션으로 사용할 수 있으며, 다른 사용자의 Exchange UM 서비스를 마이그레이션 후에는 일부 사용자에 게 유지 하도록 선택 하는 경우 영구 솔루션으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="9d9ca-111">Lync Server 2013을 호스트 된 Exchange UM과 통합 하려면 *공유 SIP 주소 공간* ( *분할 도메인*이 라고도 함)을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="9d9ca-112">이 구성에서는 Lync Server 2013와 타사의 호스트 된 Exchange UM 서비스 공급자가 모두 동일한 SIP 도메인 주소 공간에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="9d9ca-113">자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 EXCHANGE UM 통합 아키텍처](lync-server-2013-hosted-exchange-um-integration-architecture.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d9ca-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

