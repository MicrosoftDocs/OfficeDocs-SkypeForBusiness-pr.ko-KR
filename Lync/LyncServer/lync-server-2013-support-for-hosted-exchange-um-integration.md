---
title: 호스팅된 Exchange UM 통합에 대 한 Lync Server 2013 지원
description: Lync Server 2013은 호스팅된 Exchange UM 통합을 지원 합니다.
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
ms.openlocfilehash: 88920667d703bc634921903e8e3995cb65db6873
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546323"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="10bc2-103">Lync Server 2013의 호스팅된 Exchange UM 통합 지원</span><span class="sxs-lookup"><span data-stu-id="10bc2-103">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10bc2-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="10bc2-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="10bc2-105">Lync Server 2013 ExUM 라우팅 응용 프로그램은 다음 다이어그램에 나와 있는 것 처럼, Lync Server 2013 및 Exchange UM을 모두 회사 내에서 로컬로 설치 하거나 서비스 공급자가 호스트 하는 Exchange UM을 사용 하 여 온-프레미스 환경에서 Exchange UM (통합 메시징)과의 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-105">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="10bc2-106">![온-프레미스 Lync Server Exchange UM 배포](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "온-프레미스 Lync Server Exchange UM 배포")</span><span class="sxs-lookup"><span data-stu-id="10bc2-106">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="10bc2-107">다음과 같은 모드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-107">The following modes are supported:</span></span>

  - <span data-ttu-id="10bc2-108">**온-프레미스 모드**     Lync Server 2013 및 Exchange UM은 둘 다 엔터프라이즈 내의 로컬 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-108">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="10bc2-109">**크로스-프레미스 모드**     Lync Server 2013는 엔터프라이즈 내의 로컬 서버에 배포 되며 Exchange UM은 Microsoft Exchange Online 데이터 센터와 같은 온라인 서비스 공급자의 기능을 통해 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-109">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="10bc2-110">**혼합 모드**     Lync Server 2013 배포에는 일부 사용자 사서함이 회사 내에서 Microsoft Exchange Server를 실행 하는 로컬 서버에 있고 호스팅된 Exchange 서비스 데이터 센터에 있는 일부 사서함이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-110">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10bc2-111">혼합 모드는 사용자를 호스트 된 Exchange UM으로 마이그레이션 하는 동안 전환 및 진행 하는 동시에 확인 솔루션으로 사용 하거나, 다른 사용자를 마이그레이션 한 후에 일부의 Exchange UM 서비스를 온-프레미스로 유지 하는 경우 영구 솔루션으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-111">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="10bc2-112">Lync Server 2013을 호스팅된 Exchange UM과 통합 하려면 *공유 SIP 주소 공간* ( *분할 도메인*이 라고도 함)을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-112">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="10bc2-113">이 구성에서 Lync Server 2013 및 타사에서 호스트 되는 Exchange UM 서비스 공급자는 모두 동일한 SIP 도메인 주소 공간에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10bc2-113">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="10bc2-114">자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 EXCHANGE UM 통합 아키텍처](lync-server-2013-hosted-exchange-um-integration-architecture.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="10bc2-114">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

