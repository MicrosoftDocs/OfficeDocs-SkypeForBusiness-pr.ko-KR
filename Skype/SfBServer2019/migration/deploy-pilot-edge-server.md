---
title: 파일럿 Edge 서버 배포
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 항목에서는 비즈니스용 Skype 서버 2019 에지 서버를 배포하기 전에 알고 있어야 하는 구성 설정을 강조합니다. 비즈니스용 Skype 서버 2019의 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 유사합니다. 또한 이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서도 설명합니다. 자세한 단계는 배포 프로세스에 대해 설명하고 외부 사용자 액세스에 대한 구성 정보도 제공하는 배포 설명서의 비즈니스용 Skype 서버 2019에서 외부 사용자 액세스 배포를 참조하십시오.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752870"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="67e02-106">파일럿 Edge 서버 배포</span><span class="sxs-lookup"><span data-stu-id="67e02-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="67e02-107">이 항목에서는 비즈니스용 Skype 서버 2019 에지 서버를 배포하기 전에 알고 있어야 하는 구성 설정을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="67e02-108">비즈니스용 Skype 서버 2019의 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="67e02-109">또한 이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="67e02-p103">**새 에지 풀 정의** 마법사를 탐색할 때 다음 단계에 표시된 핵심 구성 설정을 검토합니다. **새 에지 풀 정의** 마법사의 일부 페이지만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-p103">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="67e02-112">에지 풀을 정의하는 경우</span><span class="sxs-lookup"><span data-stu-id="67e02-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="67e02-113">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="67e02-114">비즈니스용 Skype 서버 2019 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="67e02-115">**에지 풀** 을 마우스 오른쪽 단추로 클릭하고 **새 에지 풀** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![새 에지 풀 정의 대화 상자](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="67e02-117">에지 풀은 **다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀** 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![에지 풀 FQDN 정의 대화 상자](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="67e02-119">**기능 선택** 페이지에서 페더레이션을 사용하도록 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="67e02-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="67e02-120">페더ation과 XMPP 페더ation은 모두 현재 레거시 에지 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="67e02-121">이러한 기능은 마이그레이션의 이후 단계에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="67e02-122">외부 **FQDNS,** 내부 **IP** 주소 정의 및 외부 IP 주소 정의 마법사 페이지 **완료를 계속합니다.**</span><span class="sxs-lookup"><span data-stu-id="67e02-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="67e02-123">다음 홉 **서버** 정의 페이지에서 레거시 에지 풀의 다음 홉에 대한 Director를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![다음 홉 정의 대화 상자](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="67e02-125">프런트 엔드 또는 중재 풀 연결 **페이지에서** 현재 풀을 이 에지 풀과 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="67e02-126">외부 미디어 트래픽은 현재 레거시 에지 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="67e02-127">이 설정은 마이그레이션의 이후 단계에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![프런트 엔드 풀 연결 대화 상자](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="67e02-129">마친 **다음**  토폴로지 게시를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="67e02-130">배포 설명서의 단계에 따라 새 에지 서버에 파일을 설치하고 인증서를 구성한 다음 서비스를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="67e02-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="67e02-131">배포 설명서의 항목에 있는 지침을 따르는 것이 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="67e02-132">이 섹션에는 단순히 이러한 서버 역할을 설치할 때의 구성 설정에 대한 일부 지침만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="67e02-133">이제 레거시 에지 서버가 비즈니스용 Skype 서버 2019 에지 서버 배포와 동시에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="67e02-134">두 배포가 올바르게 실행되고 있는지, 서비스가 시작되었는지, 다음 단계로 이동하기 전에 각 배포를 관리할 수 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67e02-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

