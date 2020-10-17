---
title: Lync Server 2010 환경 확인
description: Lync Server 2010 environment를 확인 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555584"
---
# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="be677-103">Lync Server 2010 환경 확인</span><span class="sxs-lookup"><span data-stu-id="be677-103">Verify Lync Server 2010 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be677-104">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="be677-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="be677-105">Lync server 2010와 함께 동시 사용 상태에 Lync Server 2013을 배포 하기 전에 Lync server 2010 서비스가 구성 및 시작 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-105">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="be677-106">Lync Server 2013 파일럿 풀을 배포 하기 전에 레거시 환경에 있는 주요 서비스와 기능을 파악 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-106">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="be677-107">레거시 XMPP 배포를 사용 하 여 Microsoft Lync Server 2013 XMPP를 공존 상태로 배포 하기 전에 레거시 XMPP 서비스가 구성 및 시작 되었는지 확인 하 고 레거시 XMPP 구성에서 지 원하는 페더레이션 파트너를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-107">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="be677-108">레거시 Lync Server 2010 배포를 확인 하면 다음이 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be677-108">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="be677-109">Lync Server 2010 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="be677-109">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="be677-110">Lync Server 2010에서 토폴로지와 사용자를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-110">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="be677-111">페더레이션 및 에지 서버 설정 확인</span><span class="sxs-lookup"><span data-stu-id="be677-111">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="be677-112">XMPP 서비스 및 페더레이션 파트너 확인</span><span class="sxs-lookup"><span data-stu-id="be677-112">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="be677-113">**Lync Server 2010 서비스가 시작 되었는지 확인**</span><span class="sxs-lookup"><span data-stu-id="be677-113">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="be677-114">Lync Server 2010 프런트 엔드 서버에서 관리 도구 \\ 서비스 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-114">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="be677-115">프런트 엔드 서버에서 다음 서비스가 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-115">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="be677-116">![프런트 엔드 서버에서 실행 중인 서비스 목록](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "프런트 엔드 서버에서 실행 중인 서비스 목록")</span><span class="sxs-lookup"><span data-stu-id="be677-116">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="be677-117">**Lync Server 제어판에서 Lync Server 2010 토폴로지 검토**</span><span class="sxs-lookup"><span data-stu-id="be677-117">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="be677-118">RTCUniversalServerAdmins 그룹의 구성원이나 CsAdministrator 또는 CsUserAdministrator 관리자 역할의 구성원인 계정으로 프런트 엔드 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-118">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="be677-119">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="be677-119">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="be677-120">**토폴로지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-120">Select **Topology**.</span></span> <span data-ttu-id="be677-121">Lync Server 2010 배포의 다양 한 서버가 나열 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-121">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="be677-122">![Lync Server 2010 제어판 토폴로지 페이지](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 제어판 토폴로지 페이지")</span><span class="sxs-lookup"><span data-stu-id="be677-122">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="be677-123">**Lync Server 제어판에서 Lync Server 2010 사용자를 검토 하려면**</span><span class="sxs-lookup"><span data-stu-id="be677-123">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="be677-124">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="be677-124">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="be677-125">**사용자**를 선택한 후 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-125">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="be677-126">나열 된 각 사용자에 대해 **등록자 풀** 열이 Lync Server 2010 풀을 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-126">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="be677-127">![Lync Server 2010 제어판 사용자가 나열 됩니다.](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 제어판 사용자가 나열 됩니다.")</span><span class="sxs-lookup"><span data-stu-id="be677-127">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="be677-128">**Lync Server 2010 Edge 및 페더레이션 설정을 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="be677-128">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="be677-129">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-129">Start Topology Builder.</span></span>

2.  <span data-ttu-id="be677-130">**기존 배포에서 토폴로지 다운로드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-130">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="be677-131">파일 이름을 선택하고 기본 .tbxml 파일 형식으로 토폴로지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-131">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="be677-132">Lync Server 2010 노드를 확장 하 여 배포의 다양 한 서버 역할을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-132">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="be677-133">사이트 노드를 선택하고 **사이트 페더레이션 경로 지정** 값이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-133">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="be677-134">![토폴로지 작성기, 사이트 페더레이션 경로](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "토폴로지 작성기, 사이트 페더레이션 경로")</span><span class="sxs-lookup"><span data-stu-id="be677-134">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="be677-p103">그런 다음 Standard Edition Server 또는 Enterprise Edition 프런트 엔드 풀을 선택합니다. **연결** 아래에서 미디어에 대한 에지 풀이 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="be677-137">![서버 및 풀을 보여 주는 토폴로지 작성기](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "서버 및 풀을 보여 주는 토폴로지 작성기")</span><span class="sxs-lookup"><span data-stu-id="be677-137">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="be677-138">마지막으로 에지 풀을 선택하고 **다음 홉 선택** 아래에서 다음 홉 풀이 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-138">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="be677-139">![토폴로지 작성기, 다음 홉 선택](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "토폴로지 작성기, 다음 홉 선택")</span><span class="sxs-lookup"><span data-stu-id="be677-139">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="be677-140">**레거시 XMPP 페더레이션 파트너 구성 확인**</span><span class="sxs-lookup"><span data-stu-id="be677-140">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="be677-141">레거시 XMPP 서버에서 관리 도구 \\ 서비스 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-141">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="be677-142">Office Communications Server XMPP 게이트웨이 서비스가 시작되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be677-142">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="be677-143">![Office Communications Server XMPP 게이트웨이 서비스](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 게이트웨이 서비스")</span><span class="sxs-lookup"><span data-stu-id="be677-143">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

