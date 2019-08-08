---
title: 비즈니스용 Skype 서버에서 VIS 풀 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '요약: 토폴로지 작성기를 사용 하 여 비즈니스용 Skype 서버에서 비디오 Interop 서버 풀을 만듭니다.'
ms.openlocfilehash: dc97fde4447778be20cb60d86cddac65b663c321
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235664"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="5666d-103">비즈니스용 Skype 서버에서 VIS 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="5666d-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="5666d-104">**요약:** 토폴로지 작성기를 사용 하 여 비즈니스용 Skype 서버에서 비디오 Interop 서버 풀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="5666d-105">토폴로지 작성기를 사용 하 여 VIS 또는 VIS 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="5666d-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="5666d-106">프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="5666d-107">토폴로지 작성기의 왼쪽 창에서 **비디오 Interop 서버 풀** 을 마우스 오른쪽 단추로 클릭 하 고 **새 비디오 interop 서버 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="5666d-108">**새 비디오 Interop 서버 풀 만들기** 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="5666d-109">새 비디오 Interop 서버의 풀 FQDN을 제공 하 고 **이 풀에 서버가 하나** 있거나 요구 사항에 따라 **여러 서버가 있는** 경우 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="5666d-110">고가용성을 제공 하기 위해 비디오 Interop 서버 풀을 배포 하려는 경우 **이 풀에 여러 서버가 있는**경우를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="5666d-111">이 옵션은 다음을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="5666d-112">비디오 Interop 서버 풀을 지원 하려면 DNS 부하 분산을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="5666d-113">다음 페이지에서 **이 풀의 컴퓨터 정의** 항목에 대해 풀에 있는 각 서버의 **컴퓨터 FQDN** 을 텍스트 필드로 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="5666d-114">이 단계를 반복 하 여 다른 비디오 Interop 서버를 풀에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="5666d-115">풀의 모든 컴퓨터를 정의한 경우 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="5666d-116">고가용성이 필요 하지 않으므로 풀에 비디오 Interop 서버를 하나만 배포 하려는 경우 **이 풀에 서버가 하나** 있고 **다음**을 누릅니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="5666d-117">드롭다운 목록에서 다음 홉 풀/FE를 선택 하 고 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="5666d-118">VIS와 연결할 Edge 풀을 선택 하 고 **마침을**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="5666d-119">TCP 또는 TLS 포트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="5666d-120">토폴로지 작성기의 왼쪽 창에서 새로 추가한 비디오 Interop 서버를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="5666d-121">요구 사항에 따라 TCP 또는 TLS 포트를 사용 하거나 업데이트 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="5666d-122">기본적으로 TLS가 추가 되지만, Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM)를 사용 하 여 TCP만 완전히 테스트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="5666d-123">비디오 게이트웨이를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-123">Add a video gateway.</span></span> <span data-ttu-id="5666d-124">이렇게 하려면 공유 구성 요소를 확장 하 고 **비디오 게이트웨이** 를 마우스 오른쪽 단추로 클릭 한 다음 **새 비디오 게이트웨이**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="5666d-125">비디오 게이트웨이 FQDN 또는 IP 주소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="5666d-126">비디오 게이트웨이는 하위 도메인 이나 다른 도메인에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="5666d-127">시스템의 VTCs에서 사용 하는 CUCM 비디오 게이트웨이 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="5666d-128">IPv4 또는 IPv6 중 적절 하 게 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="5666d-129">구성 된 모든 IP 주소를 사용 하거나 선택한 IP 주소로 서비스 사용량을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="5666d-130">비디오 게이트웨이의 수신 대기 포트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="5666d-131">전송 프로토콜 (TCP 또는 TLS)을 선택 하 고 비디오 SIP 트렁크 용으로 설정 된 비디오 Interop 서버와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="5666d-132">비디오 게이트웨이의 전송 프로토콜이 VIS에 대해 구성 된 전송 프로토콜과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="5666d-133">위의 단계가 완료 된 후 해당 SIP 영상 트렁크가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="5666d-134">SIP 비디오 트렁크를 마우스 오른쪽 단추로 클릭 하 고 방금 추가한 트렁크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="5666d-135">비디오 SIP 트렁크 이름, 연결 된 비디오 Interop 서버, SIP 전송 프로토콜 및 포트 모두 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="5666d-136">비디오 Interop 서버는 1: N trunks를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="5666d-137">따라서 각 트렁크가 다른 비디오 게이트웨이에서 종료 되는 단일 영상 Interop 서버와 연결 된 여러 trunks을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="5666d-138">이 제한 사항은 특정 비디오 게이트웨이에 비즈니스용 Skype 서버 배포에 정의할 수 있는 트렁크가 하나만 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="5666d-139">비즈니스용 [Skype 서버 2015에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md)에 설명 된 대로 토폴로지 문서를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5666d-140">복구 력을 개선 하기 위해 두 번째 비디오 Interop 서버 또는 VIS 풀 또는 백업 프런트 엔드 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="5666d-141">자세한 내용은 [회복성 메커니즘](../../plan-your-deployment/video-interop-server.md#resiliency) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5666d-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="5666d-142">이제 토폴로지 작성기를 사용 하 여 수행 하는 모든 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="5666d-143">새 VIS 서버 또는 서버에 소프트웨어 설치를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="5666d-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="5666d-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5666d-144">See also</span></span>

[<span data-ttu-id="5666d-145">비즈니스용 Skype 서버에서 VIS 서버 역할 배포</span><span class="sxs-lookup"><span data-stu-id="5666d-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="5666d-146">비즈니스용 Skype 서버의 비디오 Interop 서버 계획</span><span class="sxs-lookup"><span data-stu-id="5666d-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="5666d-147">비즈니스용 Skype 서버 2015에서 새 토폴로지 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="5666d-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
