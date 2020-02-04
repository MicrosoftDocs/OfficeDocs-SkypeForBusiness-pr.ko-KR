---
title: 'Lync Server 2013: 온-프레미스 통합 메시징의 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1739dbb7d603f112af72c78032c46b94470302bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="48c31-102">Lync Server 2013의 온-프레미스 통합 메시징의 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="48c31-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48c31-103">_**마지막으로 수정한 주제:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="48c31-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="48c31-104">이 항목에서는 Exchange UM (통합 메시징) 기능을 Lync Server 2013 배포에 제공 하는 데 필요한 Microsoft Exchange Server 2013 구성 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="48c31-105">온-프레미스 Exchange UM 통합에 대해 지원 되는 토폴로지에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="48c31-106">Exchange Server 구성 요소</span><span class="sxs-lookup"><span data-stu-id="48c31-106">Exchange Server Components</span></span>

<span data-ttu-id="48c31-107">[통합 메시징 및 Lync Server 2013의 기능](lync-server-2013-features-of-integrated-unified-messaging.md) 에서 설명 하는 Exchange UM 기능을 조직의 Enterprise Voice 사용자에 게 제공 하려면 사용자 사서함을 호스트 하 고 전자 메일 및 음성 메일에 대 한 단일 저장소 위치를 제공 하는 Microsoft Exchange 사서함 서버 및 클라이언트 액세스 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="48c31-108">Exchange UM은 Exchange 사서함 및 클라이언트 액세스 서버에서 서비스로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="48c31-109">Microsoft Exchange Server 2007 및 Microsoft Exchange Server 2010의 Exchange UM 구성 요소에 대 한 자세한 내용은 온 [-프레미스 EXCHANGE Um 배포를 참조 하 여 Lync Server 2013 음성 메일을](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 배포 설명서에 제공 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="48c31-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="48c31-110">지원 되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="48c31-110">Supported Topologies</span></span>

<span data-ttu-id="48c31-111">Lync Server 2013 및 Exchange UM (통합 메시징)을 동일한 포리스트나 여러 포리스트에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="48c31-112">구축이 여러 포리스트에 걸쳐 있는 경우 각 Exchange UM 포리스트에 대해 Exchange 통합 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="48c31-113">또한 각 Exchange UM 포리스트를 신뢰 하는 Lync Server 2013 포리스트와 Lync Server 2013 포리스트에서 신뢰 하도록 각 Microsoft Exchange 포리스트를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="48c31-114">이 포리스트 트러스트 외에도, 모든 사용자에 대 한 Exchange UM 설정은 Lync Server 2013 포리스트의 사용자 개체에 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="48c31-115">Lync Server 2013는 Exchange UM 통합에 대해 다음 토폴로지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="48c31-116">단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="48c31-116">Single forest</span></span>

  - <span data-ttu-id="48c31-117">단일 도메인 (즉 단일 도메인이 있는 단일 포리스트)</span><span class="sxs-lookup"><span data-stu-id="48c31-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="48c31-118">Lync Server 2013, Microsoft Exchange 및 사용자가 모두 동일한 도메인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="48c31-119">여러 도메인 (즉, 하나 이상의 자식 도메인이 있는 루트 도메인)</span><span class="sxs-lookup"><span data-stu-id="48c31-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="48c31-120">Lync Server 2013 및 Microsoft Exchange server는 사용자를 만드는 도메인과 다른 도메인에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="48c31-121">Exchange UM 서버는 지원 되는 Lync Server 2013 풀의 다른 도메인에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="48c31-122">다중 포리스트 (즉, 리소스 포리스트).</span><span class="sxs-lookup"><span data-stu-id="48c31-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="48c31-123">Lync Server 2013는 단일 포리스트에 배포 되 고 사용자는 여러 포리스트에 걸쳐 분산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="48c31-124">사용자의 Exchange UM 특성을 Lync Server 2013 포리스트로 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48c31-125">Exchange는 여러 포리스트에 배포 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="48c31-126">각 Exchange 조직은 사용자에 게 Exchange UM을 제공 하거나 Lync Server 2013와 동일한 포리스트에 Exchange UM을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c31-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

