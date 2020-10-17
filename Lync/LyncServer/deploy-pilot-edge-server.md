---
title: 파일럿 Edge 서버 배포
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f2d51480567d1f775e9fb4b2161c9e54f8dfe7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502963"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="82f17-102">파일럿 Edge 서버 배포</span><span class="sxs-lookup"><span data-stu-id="82f17-102">Deploy pilot Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82f17-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="82f17-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="82f17-104">이 항목에서는 Lync Server 2013에 지 서버를 배포 하기 전에 알아야 하는 구성 설정을 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="82f17-105">Lync Server 2013에 대 한 배포 및 구성 프로세스는 Lync Server 2010와 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="82f17-106">또한 이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="82f17-107">자세한 단계에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하 고, 외부 사용자 액세스에 대 한 구성 정보도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="82f17-p102">**새 에지 풀 정의** 마법사를 탐색할 때 다음 단계에 표시된 핵심 구성 설정을 검토합니다. **새 에지 풀 정의** 마법사의 일부 페이지만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="82f17-110">**에지 풀을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="82f17-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="82f17-111">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="82f17-112">Lync Server 2013 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="82f17-113">**에지 풀**을 마우스 오른쪽 단추로 클릭하고 **새 에지 풀**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="82f17-114">![새에 지 풀 정의 대화 상자](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "새에 지 풀 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="82f17-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="82f17-115">에지 풀은 **다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="82f17-116">![에 지 풀 FQDN 정의 대화 상자](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "에 지 풀 FQDN 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="82f17-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="82f17-117">**기능 선택** 페이지에서 페더레이션을 사용하도록 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="82f17-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="82f17-118">페더레이션 및 XMPP 페더레이션은 현재 레거시 Lync Server 2010에 지 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="82f17-119">이러한 기능은 마이그레이션의 이후 단계에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="82f17-120">![기능 선택 대화 상자](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "기능 선택 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="82f17-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="82f17-121">그런 후 **외부 FQDN**, **내부 IP 주소 정의** 및 **외부 IP 주소 정의** 마법사 페이지를 계속해서 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="82f17-122">**다음 홉 정의** 페이지에서 Lync Server 2010에 지 풀의 다음 홉에 대 한 디렉터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="82f17-123">![다음 홉 정의 대화 상자](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "다음 홉 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="82f17-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="82f17-124">**프런트 엔드 또는 중재 풀 연결** 페이지에서 지금은이에 지 풀과 풀을 연결 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="82f17-125">외부 미디어 트래픽은 현재 레거시 Lync Server 2010에 지 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="82f17-126">이 설정은 마이그레이션의 이후 단계에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="82f17-127">![프런트 엔드 풀 연결 대화 상자](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "프런트 엔드 풀 연결 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="82f17-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="82f17-128">**마침**을 클릭한 후 토폴로지를 **게시**합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="82f17-129">배포 설명서의 [설치에 지 서버 2013](lync-server-2013-install-edge-servers.md) 의 단계에 따라 새에 지 서버에 파일을 설치 하 고, 인증서를 구성 하 고, 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="82f17-130">배포 설명서에서 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 항목에 설명 된 지침을 따르는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="82f17-131">이 섹션에는 단순히 이러한 서버 역할을 설치할 때의 구성 설정에 대한 일부 지침만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="82f17-132">이제 Lync Server 2013에 지 서버 배포와 함께 레거시 Lync Server 2010 Edge 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="82f17-133">두 배포가 올바르게 실행되고 있는지, 서비스가 시작되었는지, 다음 단계로 이동하기 전에 각 배포를 관리할 수 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="82f17-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

