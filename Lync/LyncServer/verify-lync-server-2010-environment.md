---
title: Lync Server 2010 환경 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="4a9a5-102">Lync Server 2010 환경 확인</span><span class="sxs-lookup"><span data-stu-id="4a9a5-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a9a5-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4a9a5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4a9a5-104">Lync server 2010을 함께 사용 하는 상태에서 Lync 서버 2013를 배포 하기 전에 Lync Server 2010 서비스가 구성 및 시작 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="4a9a5-105">Lync Server 2013 파일럿 풀을 배포 하기 전에 레거시 환경에 존재 하는 주요 서비스 및 기능을 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="4a9a5-106">Microsoft Lync Server 2013 XMPP를 레거시 XMPP 배포를 사용 하 여 공존 상태로 배포 하기 전에 레거시 XMPP 서비스가 구성 및 시작 되었는지 확인 하 고 레거시 XMPP 구성이 지 원하는 페더레이션 파트너를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="4a9a5-107">레거시 Lync Server 2010 배포 확인에는 다음이 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="4a9a5-108">Lync Server 2010 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="4a9a5-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="4a9a5-109">Lync Server 2010에서 토폴로지와 사용자를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="4a9a5-110">페더레이션 및 Edge 서버 설정을 확인 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="4a9a5-111">XMPP 서비스 및 페더레이션 파트너를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="4a9a5-112">**Lync Server 2010 서비스가 시작 되었는지 확인**</span><span class="sxs-lookup"><span data-stu-id="4a9a5-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="4a9a5-113">Lync Server 2010 프런트 엔드 서버에서 관리 도구\\서비스 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="4a9a5-114">프런트 엔드 서버에서 다음 서비스가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="4a9a5-115">프런트 엔드(images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "서버에서 실행 중인 서비스의") ![프런트 엔드 서버 목록에서 실행 중인 서비스 목록]</span><span class="sxs-lookup"><span data-stu-id="4a9a5-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="4a9a5-116">**Lync Server 제어판에서 Lync Server 2010 토폴로지 검토**</span><span class="sxs-lookup"><span data-stu-id="4a9a5-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="4a9a5-117">RTCUniversalServerAdmins 그룹의 구성원 이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="4a9a5-118">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="4a9a5-119">**토폴로지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-119">Select **Topology**.</span></span> <span data-ttu-id="4a9a5-120">Lync Server 2010 배포의 다양 한 서버가 나열 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="4a9a5-121">![Lync server 2010 제어판 토폴로지 페이지](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync server 2010 제어판 토폴로지 페이지")</span><span class="sxs-lookup"><span data-stu-id="4a9a5-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="4a9a5-122">**Lync server 제어판에서 Lync Server 2010 사용자를 검토 하려면**</span><span class="sxs-lookup"><span data-stu-id="4a9a5-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="4a9a5-123">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="4a9a5-124">**사용자** 를 선택 하 고 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="4a9a5-125">**등록자 그룹** 열이 나열 된 각 사용자의 Lync Server 2010 풀을 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="4a9a5-126">![Lync server 2010 제어판 목록 사용자]에 게(images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync server 2010 제어판의 목록을") 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="4a9a5-127">**Lync Server 2010 Edge 및 페더레이션 설정을 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="4a9a5-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="4a9a5-128">토폴로지 작성기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="4a9a5-129">**기존 배포에서 토폴로지 다운로드를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="4a9a5-130">파일 이름을 선택 하 고 기본 tbxml 파일 형식을 사용 하 여 토폴로지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="4a9a5-131">Lync Server 2010 노드를 확장 하 여 배포에 다양 한 서버 역할을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="4a9a5-132">사이트 노드를 선택 하 고 **사이트 페더레이션 경로 할당** 값이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="4a9a5-133">![토폴로지 작성기, 사이트 페더레이션 경로](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "토폴로지 작성기, 사이트 페더레이션 경로")</span><span class="sxs-lookup"><span data-stu-id="4a9a5-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="4a9a5-134">다음으로 Standard Edition Server 또는 Enterprise Edition 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="4a9a5-135">**연결**아래 미디어에 대 한 Edge 풀이 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="4a9a5-136">서버 및 풀을 보여 주는 서버 및 풀(images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "토폴로지 작성기") 를 ![보여 주는 토폴로지 작성기]</span><span class="sxs-lookup"><span data-stu-id="4a9a5-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="4a9a5-137">마지막으로 Edge 풀을 선택 하 고 다음 홉 풀이 **다음 홉 선택**아래에 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="4a9a5-138">![토폴로지 작성기, 다음 홉 선택](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "토폴로지 작성기, 다음 홉 선택")</span><span class="sxs-lookup"><span data-stu-id="4a9a5-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="4a9a5-139">**레거시 XMPP 페더레이션 파트너 구성 확인**</span><span class="sxs-lookup"><span data-stu-id="4a9a5-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="4a9a5-140">레거시 XMPP 서버에서 관리 도구\\서비스 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="4a9a5-141">Office Communications Server XMPP 게이트웨이 서비스가 시작 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9a5-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="4a9a5-142">![Office Communications server XMPP 게이트웨이 서비스](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "office communications Server Xmpp 게이트웨이 서비스")</span><span class="sxs-lookup"><span data-stu-id="4a9a5-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

