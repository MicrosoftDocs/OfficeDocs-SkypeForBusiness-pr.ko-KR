---
title: 'Lync Server 2013: Lync Server에서 작동 하도록 Microsoft Exchange Server의 통합 메시징 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 462252b1826802ec424c6684e3a6347754095508
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517055"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="747e9-102">Lync Server 2013에서 작동 하도록 Microsoft Exchange Server의 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="747e9-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="747e9-103">_**마지막으로 수정 된 항목:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="747e9-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="747e9-104">Exchange UM (통합 메시징)을 사용 하 여 Enterprise Voice users에 대 한 전화 응답, Outlook Voice Access 또는 자동 전화 교환 서비스를 제공 하려는 경우 계획 설명서의 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013에서 Exchange 통합 메시징 통합에 대 한 계획</A> 을 읽고이 섹션의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="747e9-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="747e9-105">Enterprise Voice와 함께 작동 하도록 Exchange UM (통합 메시징)을 구성 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="747e9-106">Exchange UM (통합 메시징) 서비스를 실행 하는 서버에서 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="747e9-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="747e9-107">모든 클라이언트 액세스 및 사서함 서버를 모든 UM SIP URI 다이얼 플랜에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="747e9-108">그렇지 않으면 아웃 바운드 통화 라우팅이 예상 대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="747e9-109">필요에 따라 하나 이상의 UM SIP URI 다이얼 플랜을 구독자 액세스 전화 번호와 함께 만든 다음 해당 Lync Server 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="747e9-110">**exchucutil.ps1** 스크립트를 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="747e9-111">UM IP 게이트웨이 만들기</span><span class="sxs-lookup"><span data-stu-id="747e9-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="747e9-112">UM 헌트 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="747e9-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="747e9-113">Lync Server 2013에 UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="747e9-114">UM 자동 전화 교환 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="747e9-115">구독자 액세스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="747e9-116">각 사용자에 대해 SIP URI를 만들고 UM SIP URI 다이얼 플랜에 사용자를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="747e9-117">요구 사항 및 권장 사항</span><span class="sxs-lookup"><span data-stu-id="747e9-117">Requirements and Recommendations</span></span>

<span data-ttu-id="747e9-118">시작 하기 전에이 섹션의 설명서에서는 클라이언트 액세스 및 사서함과 같은 Exchange 2013 역할을 배포한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="747e9-119">Microsoft Exchange Server 2013에서 Exchange UM은 이러한 서버에서 서비스로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="747e9-120">Exchange 2013 배포에 대 한 자세한 내용은 다음 위치에서 Exchange 2013 TechNet 라이브러리를 참조 하세요. [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="747e9-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="747e9-121">또한 다음에 주의하십시오.</span><span class="sxs-lookup"><span data-stu-id="747e9-121">Also note the following:</span></span>

  - <span data-ttu-id="747e9-122">Exchange UM이 여러 포리스트에 설치 된 경우 각 UM 포리스트에서 Exchange Server 통합 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="747e9-123">또한 각 UM 포리스트는 Lync Server 2013이 배포 되는 포리스트를 신뢰 하도록 구성 해야 하며, Lync Server 2013가 배포 되는 포리스트는 각 UM 포리스트를 신뢰 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="747e9-124">통합 메시징 서비스가 실행 되 고 있는 Exchange 서버 역할과 Lync Server 2013을 실행 하는 서버에서 함께 수행 하는 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="747e9-125">Lync Server 2013 통합 단계를 수행 하기 전에 Exchange Server 통합 메시징 통합 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="747e9-126">어떤 서버에서 어떤 통합 단계를 수행 하 고 어떤 관리자 역할을 사용 하는지 확인 하려면 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">온-프레미스 통합 메시징 및 Lync Server 2013 통합을 위한 배포 프로세스</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="747e9-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="747e9-127">다음 도구는 Exchange UM을 실행 하는 각 서버에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="747e9-128">Exchange 관리 셸</span><span class="sxs-lookup"><span data-stu-id="747e9-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="747e9-129">다음 작업을 수행하는 스크립트 **exchucutil.ps1**</span><span class="sxs-lookup"><span data-stu-id="747e9-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="747e9-130">각 Lync Server 2013에 대해 UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="747e9-131">각 게이트웨이에 대한 헌트 그룹 만들기.</span><span class="sxs-lookup"><span data-stu-id="747e9-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="747e9-132">각 헌트 그룹의 파일럿 식별자는 게이트웨이와 연결 된 프런트 엔드 풀 또는 Standard Edition 서버에서 사용 하는 UM SIP URI 다이얼 플랜을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="747e9-133">Lync Server 2013에 Active Directory 도메인 서비스에서 Exchange UM 개체를 읽을 수 있는 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="747e9-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="747e9-134">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="747e9-134">In This Section</span></span>

  - [<span data-ttu-id="747e9-135">Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="747e9-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="747e9-136">Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="747e9-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

