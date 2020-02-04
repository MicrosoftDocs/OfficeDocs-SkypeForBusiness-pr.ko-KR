---
title: 파일럿 Edge 서버 배포
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 686973f9334b9bf376a2e56c52f3306cf243c0eb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="cd856-102">파일럿 Edge 서버 배포</span><span class="sxs-lookup"><span data-stu-id="cd856-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd856-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cd856-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cd856-104">이 항목에서는 Lync Server 2013 Edge 서버를 배포 하기 전에 알아야 하는 구성 설정을 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="cd856-105">이 섹션에서는 파일럿 Edge 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="cd856-106">자세한 단계는 배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하 고 외부 사용자 액세스에 대 한 구성 정보도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="cd856-107">**새 Edge 풀 정의** 마법사를 탐색할 때 다음 단계에 표시 된 키 구성 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="cd856-108">**새 Edge 풀 정의** 마법사의 몇 페이지만 표시 됨에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd856-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="cd856-109">**Edge 풀 정의**</span><span class="sxs-lookup"><span data-stu-id="cd856-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="cd856-110">토폴로지 작성기를 사용 하 여 파일럿 풀 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="cd856-111">Lync Server 2013 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="cd856-112">**Edge 풀**을 마우스 오른쪽 단추로 클릭 하 고 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="cd856-113">![새 에지 풀 정의 대화 상자](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "새 에지 풀 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="cd856-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="cd856-114">Edge 풀은 **여러 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="cd856-115">![에지 풀 FQDN 정의 대화 상자](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "에지 풀 FQDN 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="cd856-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="cd856-116">**기능 선택** 페이지에서 페더레이션 또는 xmpp 페더레이션을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="cd856-117">페더레이션 및 XMPP 페더레이션은 현재 레거시 Office 통신 서버 2007 R2 Edge 서버를 통해 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="cd856-118">이러한 기능은 이후 마이그레이션 단계에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="cd856-119">![기능 선택 대화 상자](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "기능 선택 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="cd856-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="cd856-120">다음 마법사 페이지를 계속 진행 합니다. **IP 옵션**, **외부 FQDN**, **내부 IP 주소 정의**, **외부 ip 주소 정의**를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="cd856-121">**다음 홉 정의** 페이지에서 Lync Server 2013 Edge 풀의 다음 홉에 대 한 디렉터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="cd856-122">![새 에지 풀 정의 대화 상자, 다음 홉 풀 목록](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "새 에지 풀 정의 대화 상자, 다음 홉 풀 목록")</span><span class="sxs-lookup"><span data-stu-id="cd856-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="cd856-123">**프런트 엔드 풀 연결** 페이지에서 지금은이 Edge 풀과 풀을 연결 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="cd856-124">외부 미디어 트래픽은 현재 레거시 Office 통신 서버 2007 R2 Edge 서버를 통해 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="cd856-125">이 설정은 이후 마이그레이션 단계에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="cd856-126">![새 에지 풀 정의 대화 상자](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "새 에지 풀 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="cd856-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="cd856-127">**마침을** 클릭 한 다음 토폴로지를 **게시** 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="cd856-128">배포 설명서에서 [Lync server 2013에 대 한 Edge 서버 설치](lync-server-2013-install-edge-servers.md) 의 단계에 따라 새 Edge 서버에 파일을 설치 하 고 인증서를 구성한 다음 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="cd856-129">배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 항목의 지침을 준수 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="cd856-130">이 섹션에서는 이러한 서버 역할을 설치할 때 구성 설정에 대 한 몇 가지 지침만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="cd856-131">이제 Lync Server 2013 Edge 서버 배포와 병행 하 여 BackCompatSite의 현재 상태에 따라 표시 되는 레거시 Office 통신 서버 2007 R2 Edge 서버 배포를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="cd856-132">페더레이션이 Office Communications Server 2007 R2 감독을 사용 하도록 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="cd856-133">두 배포가 모두 제대로 실행 되 고 있는지 확인 하 고 서비스가 시작 되며 다음 단계로 이동 하기 전에 각 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd856-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="cd856-134">![OCS 에지 서버를 보여 주는 토폴로지 작성기](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "OCS 에지 서버를 보여 주는 토폴로지 작성기")</span><span class="sxs-lookup"><span data-stu-id="cd856-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

