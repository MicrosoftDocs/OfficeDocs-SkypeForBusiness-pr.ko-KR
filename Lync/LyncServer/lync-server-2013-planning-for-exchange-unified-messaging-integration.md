---
title: 'Lync Server 2013: Exchange 통합 메시징 통합 계획'
description: 'Lync Server 2013: Exchange 통합 메시징 통합 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31296444d21a86a7837da3e29fc2152f3ca96ccc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571884"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="2d333-103">Lync Server 2013의 Exchange 통합 메시징 통합 계획</span><span class="sxs-lookup"><span data-stu-id="2d333-103">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d333-104">_**마지막으로 수정 된 항목:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="2d333-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="2d333-105">Lync Server 2013에서는 음성 메시징 및 전자 메일 메시징을 단일 메시징 인프라로 결합할 때 Exchange UM (통합 메시징)과의 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d333-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="2d333-106">Microsoft Exchange Server 2007 SP1 (서비스 팩 1) 및 Microsoft Exchange Server 2010에서 Exchange UM (통합 메시징)은 설치 및 구성할 수 있는 여러 Exchange 서버 역할 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2d333-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="2d333-107">Microsoft Exchange Server 2013에서 Exchange UM은 Exchange 사서함 서버에서 서비스로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d333-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="2d333-108">Lync Server 2013 Enterprise Voice 배포의 경우 통합 메시징은 음성 메시징 및 전자 메일 메시징을 전화 (Outlook Voice Access) 또는 컴퓨터에서 사용할 수 있는 단일 저장소로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d333-108">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="2d333-109">통합 메시징 및 Lync Server 2013을 함께 사용 하 여 Enterprise Voice 사용자에 게 전화 응답, Outlook Voice Access 및 자동 전화 교환 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d333-109">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="2d333-110">Microsoft Exchange Server 2013의 아키텍처 변경 사항에 대 한 자세한 내용은 Microsoft Exchange Server 2013 설명서에서 "음성 아키텍처 변경"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) .</span><span class="sxs-lookup"><span data-stu-id="2d333-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="2d333-111">이러한 기능을 온-프레미스 Exchange UM 배포에서 지원 하려면 다음 중 하나를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d333-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="2d333-112">Microsoft Exchange Server 2007 SP1 (서비스 팩 1) 또는 최신 서비스 팩</span><span class="sxs-lookup"><span data-stu-id="2d333-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="2d333-113">Microsoft Exchange Server 2010 또는 최신 서비스 팩</span><span class="sxs-lookup"><span data-stu-id="2d333-113">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="2d333-114">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d333-114">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d333-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2d333-115">In This Section</span></span>

  - [<span data-ttu-id="2d333-116">통합 메시징 및 Lync Server 2013의 기능</span><span class="sxs-lookup"><span data-stu-id="2d333-116">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="2d333-117">Lync Server 2013의 온-프레미스 통합 메시징에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="2d333-117">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="2d333-118">온-프레미스 통합 메시징과 Lync Server 2013의 통합 지침</span><span class="sxs-lookup"><span data-stu-id="2d333-118">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="2d333-119">온-프레미스 통합 메시징과 Lync Server 2013의 통합을 위한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="2d333-119">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

