---
title: 파일럿 Edge 서버 배포
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="d58c9-102">파일럿 Edge 서버 배포</span><span class="sxs-lookup"><span data-stu-id="d58c9-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d58c9-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d58c9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d58c9-104">이 항목에서는 Lync Server 2013 Edge 서버를 배포 하기 전에 알아야 하는 구성 설정을 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="d58c9-105">Lync Server 2013의 배포 및 구성 프로세스는 Lync Server 2010과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="d58c9-106">이 섹션에서는 파일럿 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="d58c9-107">자세한 단계는 배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하 고 외부 사용자 액세스에 대 한 구성 정보도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="d58c9-108">**새 Edge 풀 정의** 마법사를 탐색할 때 다음 단계에 표시 된 키 구성 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="d58c9-109">**새 Edge 풀 정의** 마법사의 몇 페이지만 표시 됨에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d58c9-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="d58c9-110">**Edge 풀 정의**</span><span class="sxs-lookup"><span data-stu-id="d58c9-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="d58c9-111">도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d58c9-112">Lync Server 2013 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="d58c9-113">**Edge 풀**을 마우스 오른쪽 단추로 클릭 하 고 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="d58c9-114">![새 에지 풀 정의 대화 상자](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "새 에지 풀 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="d58c9-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="d58c9-115">Edge 풀은 **여러 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="d58c9-116">![에지 풀 FQDN 정의 대화 상자](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "에지 풀 FQDN 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="d58c9-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="d58c9-117">**기능 선택** 페이지에서 페더레이션 또는 xmpp 페더레이션을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="d58c9-118">페더레이션 및 XMPP 페더레이션은 현재 레거시 Lync Server 2010 Edge 서버를 통해 라우팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="d58c9-119">이러한 기능은 이후 마이그레이션 단계에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="d58c9-120">![기능 선택 대화 상자](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "기능 선택 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="d58c9-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="d58c9-121">그런 다음 마법사의 **외부 fqdn**을 계속 완료 하 고, **내부 ip 주소를 정의**하 고, **외부 ip 주소를 정의**합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="d58c9-122">**다음 홉 정의** 페이지에서 Lync Server 2010 Edge 풀의 다음 홉에 대 한 디렉터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="d58c9-123">![다음 홉 정의 대화 상자](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "다음 홉 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="d58c9-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="d58c9-124">**프런트 엔드 또는 중재 풀 연결** 페이지에서 지금은이 Edge 풀과 풀을 연결 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="d58c9-125">외부 미디어 트래픽은 현재 레거시 Lync Server 2010 Edge 서버를 통해 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="d58c9-126">이 설정은 이후 마이그레이션 단계에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="d58c9-127">![프런트 엔드 풀 연결 대화 상자](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "프런트 엔드 풀 연결 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="d58c9-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="d58c9-128">**마침을** 클릭 한 다음 토폴로지를 **게시** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="d58c9-129">배포 설명서에서 [Lync server 2013에 대 한 Edge 서버 설치](lync-server-2013-install-edge-servers.md) 의 단계에 따라 새 Edge 서버에 파일을 설치 하 고 인증서를 구성한 다음 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="d58c9-130">배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 항목의 지침을 준수 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="d58c9-131">이 섹션에서는 이러한 서버 역할을 설치할 때 구성 설정에 대 한 몇 가지 지침만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="d58c9-132">이제 Lync Server 2013 Edge 서버 배포와 함께 레거시 Lync Server 2010 Edge 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="d58c9-133">두 배포가 모두 제대로 실행 되 고 있는지 확인 하 고 서비스가 시작 되며 다음 단계로 이동 하기 전에 각 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d58c9-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

