---
title: 레거시 환경 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019을 공존 상태로 배포 하기 전에 레거시 서비스가 구성 및 시작 되었는지 확인 해야 합니다. 비즈니스용 Skype Server 2019 파일럿 풀을 배포 하기 전에 레거시 환경에 존재 하는 주요 서비스 및 기능을 확인 하는 것이 중요 합니다. Microsoft Skype for Business Server 2019 XMPP를 레거시 XMPP 배포를 사용 하 여 배포 하기 전에 레거시 XMPP 서비스를 구성 및 시작 했는지 확인 하 고 레거시 XMPP 구성이 있는 페더레이션 파트너를 확인 해야 합니다. 동시.
ms.openlocfilehash: 4c648dbbadeca50c12eb6047958ef63066ed7a3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244101"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="b7d9f-105">레거시 환경 확인</span><span class="sxs-lookup"><span data-stu-id="b7d9f-105">Verify the legacy environment</span></span>

<span data-ttu-id="b7d9f-106">비즈니스용 Skype 서버 2019을 공존 상태로 배포 하기 전에 레거시 서비스가 구성 및 시작 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="b7d9f-107">비즈니스용 Skype Server 2019 파일럿 풀을 배포 하기 전에 레거시 환경에 존재 하는 주요 서비스 및 기능을 식별 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="b7d9f-108">Microsoft Skype for Business Server 2019 XMPP를 레거시 XMPP 배포를 사용 하 여 배포 하기 전에 레거시 XMPP 서비스가 구성 및 시작 되었는지 확인 하 고 레거시 XMPP의 페더레이션 파트너를 식별 해야 합니다. 구성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="b7d9f-109">레거시 배포 확인에는 다음이 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="b7d9f-110">레거시 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="b7d9f-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="b7d9f-111">토폴로지 및 사용자 검토</span><span class="sxs-lookup"><span data-stu-id="b7d9f-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="b7d9f-112">페더레이션 및 Edge 서버 설정 확인</span><span class="sxs-lookup"><span data-stu-id="b7d9f-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="b7d9f-113">XMPP 서비스 및 페더레이션 파트너 확인</span><span class="sxs-lookup"><span data-stu-id="b7d9f-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="b7d9f-114">레거시 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="b7d9f-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="b7d9f-115">레거시 프런트 엔드 서버에서 관리 toolservices 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="b7d9f-116">프런트 엔드 서버에서 다음 서비스가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![프런트 엔드 서버에서 실행 중인 서비스 목록](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b7d9f-118">비즈니스용 Skype Server 제어판에서 레거시 토폴로지 검토</span><span class="sxs-lookup"><span data-stu-id="b7d9f-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b7d9f-119">RTCUniversalServerAdmins 그룹의 구성원 이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="b7d9f-120">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b7d9f-121">**토폴로지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-121">Select **Topology**.</span></span> <span data-ttu-id="b7d9f-122">레거시 배포의 다양 한 서버가 나열 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![제어판 토폴로지 페이지](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b7d9f-124">비즈니스용 Skype Server 제어판에서 레거시 사용자 검토</span><span class="sxs-lookup"><span data-stu-id="b7d9f-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b7d9f-125">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b7d9f-126">**사용자**를 선택 하 고 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="b7d9f-127">**등록자 그룹** 열이 나열 된 각 사용자의 레거시 풀을 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![제어판의 사용자 목록](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="b7d9f-129">레거시 Edge 및 페더레이션 설정 확인</span><span class="sxs-lookup"><span data-stu-id="b7d9f-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="b7d9f-130">토폴로지 작성기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="b7d9f-131">**기존 배포에서 토폴로지 다운로드를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="b7d9f-132">파일 이름을 선택 하 고 기본 tbxml 파일 형식으로 토폴로지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="b7d9f-133">레거시 설치 노드를 확장 하 여 배포에 다양 한 서버 역할을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="b7d9f-134">사이트 노드를 선택 하 고 **사이트 페더레이션 경로 할당** 값이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![토폴로지 작성기, 사이트 페더레이션 경로](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="b7d9f-136">Standard Edition Server 또는 Enterprise Edition 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="b7d9f-137">**연결**아래 미디어에 대해 Edge 풀이 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![서버 및 풀을 보여 주는 토폴로지 작성기](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="b7d9f-139">Edge 풀을 선택 하 고 다음 홉 풀이 **다음 홉 선택**아래에 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![토폴로지 작성기, 다음 홉 선택](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="b7d9f-141">레거시 XMPP 페더레이션 파트너 구성 확인</span><span class="sxs-lookup"><span data-stu-id="b7d9f-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="b7d9f-142">레거시 XMPP 서버에서 관리 toolservices 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="b7d9f-143">Office Communications Server XMPP 게이트웨이 서비스가 시작 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server XMPP 게이트웨이 서비스](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

