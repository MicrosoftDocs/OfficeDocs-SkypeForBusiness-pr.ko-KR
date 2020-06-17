---
title: 파일럿 풀 배포
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
description: 비즈니스용 Skype 서버 2019로 마이그레이션하는 데 필요한 첫 단계 중 하나는 파일럿 풀을 배포 하는 것입니다. 파일럿 풀은 레거시 배포를 사용 하 여 비즈니스용 Skype 서버 2019의 공존 성을 테스트 합니다. 동시 사용은 모든 사용자 및 풀을 비즈니스용 Skype 서버 2019로 이동할 때까지 지속 되는 임시 상태입니다.
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752860"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="7c7ac-105">비즈니스용 Skype 서버 2019 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="7c7ac-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="7c7ac-106">비즈니스용 Skype 서버 2019로 마이그레이션하는 데 필요한 첫 단계 중 하나는 파일럿 풀을 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="7c7ac-107">파일럿 풀은 레거시 배포를 사용 하 여 비즈니스용 Skype 서버 2019의 공존 성을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="7c7ac-108">동시 사용은 모든 사용자 및 풀을 비즈니스용 Skype 서버 2019로 이동할 때까지 지속 되는 임시 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="7c7ac-109">파일럿 풀을 배포할 때는 새 프런트 엔드 풀 정의 마법사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="7c7ac-110">레거시 풀에 있는 비즈니스용 Skype 서버 2019 파일럿 풀에 동일한 기능 및 작업을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="7c7ac-111">이전 환경을 보관 또는 모니터링 하기 위해 보관 서버, 모니터링 서버 또는 System Center Operations Manager를 배포한 경우 마이그레이션 전체에서 보관 또는 모니터링을 계속 하려면 파일럿 환경에도 이러한 기능을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="7c7ac-112">이전 환경을 보관 하거나 모니터링 하기 위해 배포한 버전은 비즈니스용 Skype 서버 2019 환경에 데이터가 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7c7ac-113">다음 절차에서는 전체 파일럿 풀 배포 프로세스에서 고려해야 하는 기능 및 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="7c7ac-114">이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서만 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="7c7ac-115">비즈니스용 Skype 서버 2019 파일럿 풀을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="7c7ac-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="7c7ac-116">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="7c7ac-117">**비즈니스용 Skype 서버 2019**  >  **Enterprise Edition 프런트 엔드 풀**에 도달할 때까지 트리를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="7c7ac-118">**Enterprise Edition 프런트 엔드** 풀을 마우스 오른쪽 단추로 클릭 하 고 **새 프런트 엔드 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="7c7ac-119">풀 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="7c7ac-120">파일럿 풀을 정의할 때는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버를 배포 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="7c7ac-121">비즈니스용 Skype 서버 2019에서는 파일럿 풀 기능이 레거시 풀에 배포 된 것과 일치 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7c7ac-122">파일럿 풀에 대해 정의 하는 풀 또는 서버 FQDN은 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="7c7ac-123">현재 배포 된 레거시 풀이나 현재 배포 되어 있는 다른 서버 이름과는 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="7c7ac-124">**기능 선택** 페이지에서 이 프런트 엔드 풀에 필요한 기능의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="7c7ac-125">예를 들어 IM (인스턴트 메시징) 및 현재 상태 기능만 배포 하는 경우에는 회의 확인란을 선택 하 여 단체 IM을 허용 하지만 전화 접속 (PSTN) 회의, Enterprise Voice 또는 통화 허용 제어 확인란은 음성, 비디오 및 공동 작업 회의 기능을 나타내므로 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="7c7ac-126">**배치 된 서버 역할 선택** 페이지에서 비즈니스용 Skype 서버 2019에 중재 서버를 함께 배치할는 방법을 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="7c7ac-127">이전 토폴로지를 비즈니스용 Skype 서버 2019에 병합 하는 경우 먼저 레거시 중재 서버를 함께 배치할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="7c7ac-128">토폴로지를 병합 하 고 비즈니스용 Skype 서버 2019 중재 서버를 구성한 후에는 배포 프로세스에서 나중에 중재 서버 역할을 비즈니스용 Skype 서버 2019로 이동할 때 배치 된 중재 서버를 유지할지 아니면 독립 실행형 서버로 변경할 것인지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="7c7ac-129">파일럿 풀 배포 중에 **서버 역할을이 프런트 엔드 풀과 연결** 페이지에서 **이 프런트 엔드 풀의 미디어 구성 요소에 대해에 지 풀을 사용할 수 있도록 설정** 합니다 옵션을 선택 *하지 마십시오* .</span><span class="sxs-lookup"><span data-stu-id="7c7ac-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="7c7ac-130">이 기능은 나중에 마이그레이션 중에 사용하고 온라인으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="7c7ac-131">현재는 이 설정을 해제한 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="7c7ac-132">**Office Web Apps 서버 선택** 페이지에서 **새로 만들기**를 클릭한 다음 응용 프로그램 서버의 FQDN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="7c7ac-133">**보관 Sql server 저장소 정의** 페이지에서 비즈니스용 Skype 서버 보관 및 모니터링에 대 한 sql server 저장소를 정의할 때 비즈니스용 skype 서버 2019에서 이전에 만든 sql server 인스턴스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="7c7ac-134">토폴로지를 게시 하려면 **비즈니스용 Skype 서버** 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="7c7ac-135">게시 프로세스를 완료했으면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-135">When the publish process has completed, click **Finish**.</span></span>

12. <span data-ttu-id="7c7ac-136">다음 섹션인 "레거시 풀과의 파일럿 풀 동시 사용 확인" 섹션으로 이동 하기 전에 게시 된 토폴로지에서 방금 정의한 비즈니스용 skype 서버 새 프런트 엔드 파일럿 풀을 설치 해야 함 다음에 설명 된 절차에 따라 [토폴로지의 서버에 비즈니스용 Skype 서버 설치](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="7c7ac-136">Before moving to the next section called "Verify pilot pool coexistence with legacy pool" you need to install the Skype for Business Server new Front End pilot pool we just defined in the published topology, follow the procedures outlined here [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>

13. <span data-ttu-id="7c7ac-137">이전 단계가 완료 되 면 다음 섹션으로 이동 하 여 레거시 풀과의 파일럿 풀 공존 성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-137">Once previous step is complete, move to the next section to Verify pilot pool coexistence with legacy pool.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

