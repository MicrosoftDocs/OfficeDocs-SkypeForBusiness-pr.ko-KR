---
title: 파일럿에 지 서버 배포
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이 항목에서는 비즈니스용 Skype Server 2019 Edge 서버를 배포 하기 전에 알아야 하는 구성 설정을 강조 합니다. 비즈니스용 Skype Server 2019의 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 유사 합니다. 이 섹션에서는 파일럿 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다. 자세한 단계는 배포 프로세스를 설명 하는 배포 설명서의 비즈니스용 Skype 서버 2019 외부 사용자 액세스 배포를 참조 하 고 외부 사용자 액세스에 대 한 구성 정보도 제공 합니다.
ms.openlocfilehash: f692eb5ad4a24b47a8bab7a56be218eab04af7dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189096"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="cfb8d-106">파일럿에 지 서버 배포</span><span class="sxs-lookup"><span data-stu-id="cfb8d-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="cfb8d-107">이 항목에서는 비즈니스용 Skype Server 2019 Edge 서버를 배포 하기 전에 알아야 하는 구성 설정을 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="cfb8d-108">비즈니스용 Skype Server 2019의 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="cfb8d-109">이 섹션에서는 파일럿 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="cfb8d-110">**새 Edge 풀 정의** 마법사를 탐색할 때 다음 단계에 표시 된 키 구성 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="cfb8d-111">**새 Edge 풀 정의** 마법사의 몇 페이지만 표시 됨에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="cfb8d-112">Edge 풀을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="cfb8d-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="cfb8d-113">도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="cfb8d-114">비즈니스용 Skype 서버 2019 노드를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="cfb8d-115">**Edge 풀**을 마우스 오른쪽 단추로 클릭 하 고 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![새 에지 풀 정의 대화 상자](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="cfb8d-117">Edge 풀은 **여러 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![에지 풀 FQDN 정의 대화 상자](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="cfb8d-119">**기능 선택** 페이지에서 페더레이션 또는 xmpp 페더레이션을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="cfb8d-120">페더레이션 및 XMPP federation가 현재 레거시 Edge 서버를 통해 라우팅된 경우</span><span class="sxs-lookup"><span data-stu-id="cfb8d-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="cfb8d-121">이러한 기능은 이후 마이그레이션 단계에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="cfb8d-122">**외부 fqdn**을 지정 하 고 **내부 ip 주소를 정의**하 고 **외부 ip 주소를 정의**하 여 다음 마법사 페이지를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="cfb8d-123">**다음 홉 서버 정의** 페이지에서 레거시 Edge 풀의 다음 홉에 대 한 디렉터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![다음 홉 정의 대화 상자](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="cfb8d-125">**프런트 엔드 또는 중재 풀 연결** 페이지에서 지금은이 Edge 풀과 풀을 연결 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="cfb8d-126">외부 미디어 트래픽은 현재 레거시에 지 서버를 통해 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="cfb8d-127">이 설정은 이후 마이그레이션 단계에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![프런트 엔드 풀 연결 대화 상자](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="cfb8d-129">**마침을**클릭 한 다음 토폴로지를 **게시** 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="cfb8d-130">배포 설명서의 단계에 따라 새 Edge 서버에 파일을 설치 하 고 인증서를 구성한 다음 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="cfb8d-131">배포 설명서의 항목에 있는 지침을 준수 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="cfb8d-132">이 섹션에서는 이러한 서버 역할을 설치할 때 구성 설정에 대 한 몇 가지 지침만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="cfb8d-133">이제 비즈니스용 Skype Server 2019 Edge 서버 배포와 함께 레거시 Edge 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="cfb8d-134">두 배포가 모두 제대로 실행 되 고 있는지 확인 하 고 서비스가 시작 되며 다음 단계로 이동 하기 전에 각 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb8d-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

