---
title: 전화 접속 회의 구성 필수 구성 요소 및 권한
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60fc58e0ec40dadff044257d43629c2f3cb01ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="1ec14-102">Lync Server 2013의 전화 접속 회의 구성 필수 구성 요소 및 권한</span><span class="sxs-lookup"><span data-stu-id="1ec14-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ec14-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1ec14-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1ec14-104">전화 접속 회의는 Lync Server 2013 회의 작업 부하의 선택적 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="1ec14-105">토폴로지 작성기를 사용 하 여 토폴로지를 디자인 한 다음 프런트 엔드 풀 또는 Standard Edition 서버를 설정 하는 경우 전화 접속 회의를 구성 하기 전에 설치 해야 하는 구성 요소를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="1ec14-106">이 항목에서는 전화 접속 회의를 구성 하기 전에 수행 해야 하는 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="1ec14-107">이 섹션에서는 회의 작업 부하 및 전화 접속 회의와 관련 된 계획 섹션을 특별히 읽은 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="1ec14-108">전화 접속 회의 구성 필수 조건</span><span class="sxs-lookup"><span data-stu-id="1ec14-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="1ec14-109">전화 접속 회의에는 다음과 같은 Lync Server 2013 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="1ec14-110">통합 커뮤니케이션 응용 프로그램 서비스 (c) ( *응용 프로그램 서비스*라고 함)</span><span class="sxs-lookup"><span data-stu-id="1ec14-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="1ec14-111">회의 수행자 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1ec14-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="1ec14-112">회의 알림 신청</span><span class="sxs-lookup"><span data-stu-id="1ec14-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="1ec14-113">전화 접속 회의 설정 웹 페이지</span><span class="sxs-lookup"><span data-stu-id="1ec14-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="1ec14-114">하나 이상의 Lync Server 2013 중재 서버와 하나 이상의 PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="1ec14-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="1ec14-115">토폴로지 작성기를 사용 하 여 토폴로지를 정의 하 고 게시 한 다음 프런트 엔드 풀 또는 Standard Edition 서버를 배포 하는 경우 이러한 구성 요소를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="1ec14-116">엔터프라이즈 음성을 배포 하는 경우 전화 접속 회의를 구성 하기 전에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="1ec14-117">엔터프라이즈 음성을 배포 하지 않는 경우에는 프런트 엔드 풀 또는 Standard Edition 서버를 배포할 때 중재 서버와 PSTN (공용 전환 통신 네트워크) 게이트웨이를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1ec14-118">Office Communications Server 2007 R2에서 Lync Server 2013으로 업그레이드 하는 경우 Lync Server 2013 회의를 호스트 하는 데 사용할 모든 풀에 전화 접속 회의를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="1ec14-119">전화 접속 회의를 마이그레이션하는 방법에 대 한 자세한 내용은 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Office Communications Server 2007 R2에서 Lync Server 2013로 마이그레이션을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec14-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1ec14-120">이 섹션에서는 다음을 완료 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="1ec14-121">Lync Server 2013로 마이그레이션하는 경우 Office Communications Server 2007 R2 환경에 최신 업데이트를 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="1ec14-122">토폴로지 작성기를 사용 하 여 토폴로지를 디자인 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="1ec14-123">회의 작업을 지정 하는 동안 전화 접속 회의 옵션을 선택 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="1ec14-124">토폴로지를 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec14-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1ec14-125">토폴로지를 게시 하 고 프런트 엔드 풀 또는 Standard Edition 서버를 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="1ec14-126">토폴로지 게시 및 Lync Server 2013 설치에 대 한 자세한 내용은 배포 설명서에서 [Lync server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec14-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1ec14-127">게시 된 토폴로지를 설치할 때 전화 접속 회의 설정 웹 페이지가 프런트 엔드 서버 또는 Standard Edition 서버에 웹 서비스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="1ec14-128">Lync Server 2013을 배포한 후 토폴로지 작성기에서 파일 저장소의 경로를 변경 하는 경우에는 새 경로를 사용 하기 위해 회의 수행자와 회의 알림 응용 프로그램을 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="1ec14-129">엔터프라이즈 보이스을 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="1ec14-130">엔터프라이즈 음성을 배포 하지 않는 경우 Enterprise Edition 프런트 엔드 서버 또는 스탠더드 버전 서버에서 중재 서버를 collocated, 독립 실행형 중재 서버를 배포 했으며 PSTN 게이트웨이를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="1ec14-131">엔터프라이즈 음성을 배포 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 Enterprise Voice 배포](lync-server-2013-deploying-enterprise-voice.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec14-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="1ec14-132">독립 실행형 중재 서버 및 PSTN 게이트웨이를 설치 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 중재 서버 배포 및 피어 정의](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec14-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="1ec14-133">다음 순서도는 전화 접속 회의를 구성 하기 전에 수행 해야 하는 단계와 전화 접속 회의를 구성 하기 위해 수행 하는 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="1ec14-134">**전화 접속 회의 배포**</span><span class="sxs-lookup"><span data-stu-id="1ec14-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="1ec14-135">![전화 접속 회의 배포 순서도](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "전화 접속 회의 배포 순서도")</span><span class="sxs-lookup"><span data-stu-id="1ec14-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="1ec14-136">전화 접속 회의 권한</span><span class="sxs-lookup"><span data-stu-id="1ec14-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="1ec14-137">전화 접속 회의를 구성 하려면 다음 관리 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="1ec14-138">Lync Server 2013 제어판</span><span class="sxs-lookup"><span data-stu-id="1ec14-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="1ec14-139">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1ec14-139">Lync Server Management Shell</span></span>

<span data-ttu-id="1ec14-140">이러한 관리 도구를 사용 하 여 전화 접속 회의 설정을 구성 하 고 전화 접속 회의에 필요한 다이얼 플랜, 정책 및 기타 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="1ec14-141">전화 접속 회의를 구성 하려면 작업에 따라 다음 관리 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="1ec14-142">\*\*\*\*   이 관리자 역할이 음성 관련 설정 및 정책을 만들고, 구성 하 고, 관리할 수 CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1ec14-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="1ec14-143">**Csuseradministrator**   이 관리자 역할은 Lync Server의 사용자를 사용 하거나 사용 하지 않도록 설정 하 고, 사용자에 게 회의 정책 및 PIN 정책 등의 기존 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="1ec14-144">**Csadministrator**   이 관리자 역할은 CsVoiceAdministrator 및 csuseruseradministrator의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec14-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ec14-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ec14-145">See Also</span></span>


[<span data-ttu-id="1ec14-146">Lync Server 2013에서 엔터프라이즈 음성 배포</span><span class="sxs-lookup"><span data-stu-id="1ec14-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

