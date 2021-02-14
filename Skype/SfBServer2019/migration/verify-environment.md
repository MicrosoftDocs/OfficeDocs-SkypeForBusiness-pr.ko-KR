---
title: 레거시 환경 확인
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
description: 비즈니스용 Skype 서버 2019를 동시 사용 상태로 배포하기 전에 레거시 서비스가 구성되고 시작된지 확인해야 합니다. 비즈니스용 Skype 서버 2019 파일럿 풀을 배포하기 전에 레거시 환경에 있는 주요 서비스 및 기능을 파악하는 것이 중요합니다. 레거시 XMPP 배포와 동시 사용 상태로 Microsoft 비즈니스용 Skype 서버 2019 XMPP를 배포하기 전에 레거시 XMPP 서비스가 구성 및 시작되어 있는지 확인하고 레거시 XMPP 구성이 지원하는 페더링 파트너를 식별해야 합니다.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751680"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="a47fb-105">레거시 환경 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-105">Verify the legacy environment</span></span>

<span data-ttu-id="a47fb-106">비즈니스용 Skype 서버 2019를 동시 사용 상태로 배포하기 전에 레거시 서비스가 구성되고 시작된지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="a47fb-107">비즈니스용 Skype 서버 2019 파일럿 풀을 배포하기 전에 레거시 환경에 있는 주요 서비스 및 기능을 파악하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="a47fb-108">레거시 XMPP 배포와 동시 사용 상태로 Microsoft 비즈니스용 Skype 서버 2019 XMPP를 배포하기 전에 레거시 XMPP 서비스가 구성 및 시작되어 있는지 확인하고 레거시 XMPP 구성이 지원하는 페더링 파트너를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="a47fb-109">레거시 배포를 확인하면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="a47fb-110">레거시 서비스가 시작된지 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="a47fb-111">토폴로지 및 사용자 검토</span><span class="sxs-lookup"><span data-stu-id="a47fb-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="a47fb-112">페더링 및 에지 서버 설정 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="a47fb-113">XMPP 서비스 및 페더링 파트너 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="a47fb-114">레거시 서비스가 시작된지 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="a47fb-115">레거시 프런트 엔드 서버에서 관리 도구\서비스 애플릿으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a47fb-116">프런트 엔드 서버에서 다음 서비스가 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![프런트 엔드 서버에서 실행되는 서비스 목록](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a47fb-118">비즈니스용 Skype 서버 제어판에서 레거시 토폴로지 검토</span><span class="sxs-lookup"><span data-stu-id="a47fb-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a47fb-119">RTCUniversalServerAdmins 그룹의 구성원이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원인 계정으로 프런트 엔드 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="a47fb-120">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a47fb-121">**토폴로지** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-121">Select **Topology**.</span></span> <span data-ttu-id="a47fb-122">레거시 배포의 다양한 서버가 나열되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![제어판 토폴로지 페이지](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a47fb-124">비즈니스용 Skype 서버 제어판에서 레거시 사용자 검토</span><span class="sxs-lookup"><span data-stu-id="a47fb-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a47fb-125">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a47fb-126">사용자를 **선택하고** 찾기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a47fb-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="a47fb-127">등록자 풀 **열이** 나열된 각 사용자의 레거시 풀을 포인트로 하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![제어판에 사용자 나열](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="a47fb-129">레거시 에지 및 페더전 설정 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="a47fb-130">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="a47fb-131">**기존 배포에서 토폴로지 다운로드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="a47fb-132">파일 이름을 선택하고 기본 .tbxml 파일 형식으로 토폴로지 저장</span><span class="sxs-lookup"><span data-stu-id="a47fb-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="a47fb-133">레거시 설치 노드를 확장하여 배포의 다양한 서버 역할을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="a47fb-134">사이트 노드를 선택하고 사이트 **페더ation** 경로 할당 값이 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![토폴로지 작성기, 사이트 페더ation 경로](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="a47fb-136">Standard Edition Server 또는 Enterprise Edition 프런트 엔드 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="a47fb-137">연결 아래의 미디어에 대해 에지 풀이 구성되어 있는지 **여부를 확인하십시오.**</span><span class="sxs-lookup"><span data-stu-id="a47fb-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![서버 및 풀을 표시하는 토폴로지 작성기](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="a47fb-139">에지 풀을 선택하고 다음 홉 풀이 다음 홉 선택 아래에 구성되어 있는지 **여부를 식별합니다.**</span><span class="sxs-lookup"><span data-stu-id="a47fb-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![토폴로지 작성기, 다음 홉 선택](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="a47fb-141">레거시 XMPP 페더럴 파트너 구성 확인</span><span class="sxs-lookup"><span data-stu-id="a47fb-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="a47fb-142">레거시 XMPP 서버에서 관리 도구의 서비스 애플릿으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a47fb-143">Office Communications Server XMPP 게이트웨이 서비스가 시작되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a47fb-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server XMPP 게이트웨이 서비스](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

