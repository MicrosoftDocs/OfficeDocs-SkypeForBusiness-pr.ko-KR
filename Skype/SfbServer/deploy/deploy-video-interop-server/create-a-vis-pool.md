---
title: 비즈니스용 Skype 서버에서 VIS 풀 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '요약: 토폴로지 작성기에서 비즈니스용 Skype 서버에서 비디오 Interop 서버 풀을 만들 수 있습니다.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802058"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="94181-103">비즈니스용 Skype 서버에서 VIS 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="94181-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="94181-104">**요약:** 토폴로지 작성기에서 비즈니스용 Skype 서버에서 비디오 Interop 서버 풀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94181-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="94181-105">토폴로지 작성기에서 VIS 또는 VIS 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="94181-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="94181-106">프런트 엔드 서버에서 토폴로지 작성기 열기</span><span class="sxs-lookup"><span data-stu-id="94181-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="94181-107">토폴로지 작성기 왼쪽 창에서 비디오 **Interop** 서버 풀을 마우스 오른쪽 단추로 클릭하고 새 **비디오 Interop 서버 풀을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="94181-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="94181-108">그러면 새 Video Interop 서버 풀 **만들기 마법사가 열립니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="94181-109">새 Video Interop 서버에 대한 풀 FQDN을  제공하고 이 풀에 서버가 하나 또는 이 풀에 요구 사항에 따라 여러 서버가 있는 경우 다음을 **누르십시오.** </span><span class="sxs-lookup"><span data-stu-id="94181-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="94181-110">비디오 Interop 서버 풀을 배포하여 고가용성을 제공하려면 이 풀에 여러 **서버가 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="94181-111">이 옵션은 이 옵션에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="94181-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="94181-112">Video Interop 서버 풀을 지원하려면 DNS 부하 분산을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="94181-113">다음 페이지에서 이 풀  항목의 컴퓨터 정의에 대해 풀에 있는 각 서버의 컴퓨터 **FQDN을** 텍스트 필드에 입력하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="94181-114">풀에 다른 Video Interop 서버를 추가하기 위해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="94181-115">풀의 모든 컴퓨터를 정의한 경우 **다음을 누르고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="94181-116">고가용성을 요구하지 않는 풀에 Video Interop 서버를 하나만 배포하려면 이 풀에 서버가 하나씩 있으며 다음을 누르는 것이 **좋습니다.** </span><span class="sxs-lookup"><span data-stu-id="94181-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="94181-117">드롭다운 목록에서 다음 홉 풀/FE를 선택하고 다음을 **누르고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="94181-118">VIS와 연결하려면 에지 풀을 선택하고 Finish를 **누르십시오.**</span><span class="sxs-lookup"><span data-stu-id="94181-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="94181-119">TCP 또는 TLS 포트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="94181-120">토폴로지 작성기 왼쪽 창에서 새로 추가된 Video Interop 서버를 선택하고 마우스 오른쪽 단추로 클릭하고 속성 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="94181-121">요구 사항에 따라 TCP 또는 TLS 포트를 사용하도록 설정하거나 업데이트하고 확인을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="94181-122">기본적으로 TLS가 추가되어도 Cisco Unified Communications Manager(CallManager 또는 CUCM)를 통해 TCP만 완전히 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94181-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="94181-123">비디오 게이트웨이를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-123">Add a video gateway.</span></span> <span data-ttu-id="94181-124">이렇게하려면 공유 구성 요소를 확장하고  비디오 게이트웨이를 마우스 오른쪽 단추로 클릭한 다음 새 비디오 **게이트웨이를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94181-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="94181-125">비디오 게이트웨이 FQDN 또는 IP 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="94181-126">비디오 게이트웨이가 하위 도메인 또는 다른 도메인에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94181-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="94181-127">시스템의 VTC에서 사용하는 CUCM은 비디오 게이트웨이 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="94181-128">IPv4 또는 IPv6을 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="94181-129">구성된 모든 IP 주소를 사용하거나 서비스 사용을 선택한 IP 주소로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94181-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="94181-130">비디오 게이트웨이의 수신 포트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="94181-131">TCP 또는 TLS(전송 프로토콜)를 선택하고 비디오 SIP 트렁크에 대해 설정된 Video Interop 서버와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="94181-132">비디오 게이트웨이의 전송 프로토콜은 VIS에 대해 구성된 전송 프로토콜과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="94181-133">위의 단계를 완료하면 해당 SIP 비디오 트렁크가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="94181-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="94181-134">SIP 비디오 트렁크를 마우스 오른쪽 단추로 클릭하고 방금 추가한 트렁크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="94181-135">비디오 SIP 트렁크 이름, 연결된 Video Interop 서버, SIP 전송 프로토콜 및 포트를 모두 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94181-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="94181-136">Video Interop 서버는 1:N 트렁크를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="94181-137">따라서 여러 트렁크를 추가할 수 있습니다. 이 트렁크는 단일 Video Interop 서버와 연결됩니다. 여기서 각 트렁크는 다른 비디오 게이트웨이에서 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="94181-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="94181-138">제한은 특정 비디오 게이트웨이에 비즈니스용 Skype 서버 배포에 정의할 수 있는 트렁크가 하나뿐이기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="94181-139">비즈니스용 Skype 서버 [2015에서](../../deploy/install/create-and-publish-new-topology.md)새 토폴로지 만들기 및 게시에 설명된 토폴로지 문서를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="94181-140">복구 기능을 향상하기 위해 두 번째 Video Interop 서버 또는 VIS 풀 또는 백업 프런트 엔드 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94181-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="94181-141">자세한 [내용은 탄력성](../../plan-your-deployment/video-interop-server.md#resiliency) 메커니즘을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94181-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="94181-142">이제 토폴로지 작성기에서 수행한 모든 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="94181-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="94181-143">새 VIS 서버 또는 서버에 소프트웨어를 계속 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="94181-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="94181-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94181-144">See also</span></span>

[<span data-ttu-id="94181-145">비즈니스용 Skype 서버에서 VIS 서버 역할 배포</span><span class="sxs-lookup"><span data-stu-id="94181-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="94181-146">비즈니스용 Skype 서버의 비디오 Interop 서버 계획</span><span class="sxs-lookup"><span data-stu-id="94181-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="94181-147">비즈니스용 Skype 서버에서 새 토폴로지 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="94181-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
