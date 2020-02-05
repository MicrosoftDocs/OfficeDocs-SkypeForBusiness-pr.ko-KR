---
title: 비즈니스용 Skype 서버에 대 한 Edge 토폴로지 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: '요약: 비즈니스용 Skype 서버에서 Edge 서버 토폴로지를 빌드, 게시 및 내보내기 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 3abde687899f240174e91d2583321bcdc6855fff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768331"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="e1525-103">비즈니스용 Skype 서버에 대 한 Edge 토폴로지 만들기</span><span class="sxs-lookup"><span data-stu-id="e1525-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="e1525-104">**요약:** 비즈니스용 Skype 서버에서 Edge 서버 토폴로지를 빌드, 게시 및 내보내기 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="e1525-105">토폴로지 작성기는 비즈니스용 Skype 서버의 모든 토폴로지 구성 요소에 사용 되는 것 처럼 Edge 서버 토폴로지를 작성 하는 데 필요한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="e1525-106">아래 단계를 수행 하기 전에 적어도 하나 이상의 프런트 엔드 풀 또는 Standard Edition server를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="e1525-107">이 문서의 다음 항목을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="e1525-108">Edge 서버 토폴로지 빌드</span><span class="sxs-lookup"><span data-stu-id="e1525-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="e1525-109">Edge 서버 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="e1525-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="e1525-110">Edge 서버 토폴로지 내보내기</span><span class="sxs-lookup"><span data-stu-id="e1525-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="e1525-111">아래 단계를 수행 하려면 다음 도메인 그룹의 구성원 인 사용자로 아래에 언급 된 도메인 서버에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="e1525-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e1525-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="e1525-113">도메인 관리자</span><span class="sxs-lookup"><span data-stu-id="e1525-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="e1525-114">Edge 서버 토폴로지 빌드</span><span class="sxs-lookup"><span data-stu-id="e1525-114">Build your Edge Server topology</span></span>

<span data-ttu-id="e1525-115">첫 번째 배포 단계는 다음 세 가지 옵션 중 하나로 구성 되는 비즈니스용 Skype Server Edge 서버 토폴로지를 작성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="e1525-116">단일에 지 서버</span><span class="sxs-lookup"><span data-stu-id="e1525-116">A single Edge Server</span></span>
    
- <span data-ttu-id="e1525-117">DNS 부하 분산 Edge 풀 (하나 이상의 서버)</span><span class="sxs-lookup"><span data-stu-id="e1525-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="e1525-118">하드웨어 부하 분산 된 Edge 풀 (하나 이상의 서버)</span><span class="sxs-lookup"><span data-stu-id="e1525-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="e1525-119">필요한 내용이 확실 하지 않은 경우 다음 단계를 시작 하기 전에 계획 설명서를 참조 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-119">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation.</span></span> <span data-ttu-id="e1525-120">그렇지 않으면 시작 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-120">Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="e1525-121">단일 Edge 서버에 대 한 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="e1525-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="e1525-122">비즈니스용 Skype server Standard Edition server 또는 비즈니스용 Skype 서버 프런트 엔드 풀에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="e1525-123">그런 다음 비즈니스용 **Skype 서버 토폴로지 작성기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="e1525-124">콘솔 트리에서 Edge 서버를 배포할 사이트를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="e1525-125">**Edge 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="e1525-126">**새 Edge 풀 정의** 화면에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="e1525-127">**Edge 풀 FQDN 정의** 화면에서 edge 서버에서 사용할 내부 FQDN (정규화 된 도메인 이름)을 입력 하 고, **단일 컴퓨터 풀**을 선택 하 고 완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="e1525-128">**기능 선택** 화면에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="e1525-129">SIP 액세스 서비스, 비즈니스용 Skype 서버 웹 회의 서비스, 그리고 A/V Edge 서비스에 대해 동일한 FQDN과 IP 주소를 사용 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="e1525-130">그렇다면 **단일 FQDN 및 IP 주소 사용 확인란** 을 선택 하 고 아래 9 단계에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1525-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="e1525-131">페더레이션을 사용 하도록 계획 하는 경우 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="e1525-132">**다음**을 클릭 하 고 나면 **IP 옵션** 화면에서 직접 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-132">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="e1525-133">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-133">Your options are as follows:</span></span>
    
   - <span data-ttu-id="e1525-134">내부 인터페이스에 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="e1525-135">내부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="e1525-136">외부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="e1525-137">외부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="e1525-138">IPv4 또는 IPv6 주소를 사용 하 고 있는지에 관계 없이 Edge 서버에서 해당 주소를 내부적으로 또는 외부적으로 적용 하는 것이 좋습니다 (10 단계에이 점에 유의 하 여 유지 해야 함).</span><span class="sxs-lookup"><span data-stu-id="e1525-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="e1525-139">또한 외부 IP 주소에 대 한 NAT (network address translation) 주소를 사용 하도록 Edge 서버 또는 Edge 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="e1525-140">이 **Edge 풀의 외부 IP 주소를 NAT에서 번역 됨** 확인란을 선택 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="e1525-141">준비 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="e1525-142">외부 Fqdn 화면에서 선택한 항목은 위의 7 단계에서 선택한 항목에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="e1525-143">**단일 FQDN 및 IP 주소 사용** 확인란을 선택한 경우에는 **SIP 액세스** 상자에 단일 외부 FQDN을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="e1525-144">그런 다음 모든 edge 서비스에 대해 서로 다른 포트 번호를 입력 해야 모든 사용자가 독립적으로 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="e1525-145">**SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스에 대 한 444, **A/V** edge 서비스에 대 한 443을 5061 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="e1525-146">완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="e1525-147">**단일 FQDN 및 IP 주소 사용** 확인란을 선택 하지 않은 경우에는 **SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스, 그리고 **a/V** Edge 서비스에 대 한 세 개의 외부 fqdn을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="e1525-148">완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="e1525-149">이제 **내부 IP 주소 정의** 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="e1525-150">여기서는 8 단계에서 다시 선택한 항목에 따라 **내부 IPv4 주소** 및 **내부 IPv6 주소** 텍스트 상자에 Edge 서버의 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="e1525-151">준비 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="e1525-152">**외부 IP 주소 정의** 화면에는 이전 선택 사항에 따라 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="e1525-153">모든 서비스에 단일 FQDN을 사용 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="e1525-154">이 경우에는 사용 중인 외부 IPv4 또는 IPv6 주소를 **SIP Access** 텍스트 상자에 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="e1525-155">서비스에 대해 세 개의 개별 Fqdn과 IP 주소를 사용 하도록 선택 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="e1525-156">그러한 경우에는 **SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스, **A/V** Edge 서비스에 대 한 외부 IPv4 또는 IPv6 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1525-157">이전에 IPv6 주소 지정을 사용 하도록 선택 하지 않은 경우이 대화 상자가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-157">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="e1525-158">그 이유는 다음 단계로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-158">That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="e1525-159">8 단계에서 NAT를 다시 사용 하도록 선택한 경우에는 이제 **공용 IP 주소** 텍스트 상자로 화면을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="e1525-160">A/V Edge 서비스에 대해 설정한 공용 IPv4 및/또는 IPv6 주소를 입력 해야 NAT에서 번역할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="e1525-161">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="e1525-162">다음 화면은 **다음 홉을 정의**합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="e1525-163">**다음 홉 풀** 상자에서 프런트 엔드 풀 또는 독립 실행형 풀 일 수 있는 내부 풀의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="e1525-164">해당 환경에 디렉터가 있는 경우에는 디렉터를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="e1525-165">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="e1525-166">**프런트 엔드 풀 연결** 화면에서이 Edge 서버와 연결 하려면 프런트 엔드 풀 및 스탠더드 버전 서버를 포함 하 여 하나 이상의 내부 풀을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="e1525-167">이 Edge 서버를 사용 하 여 지원 되는 외부 사용자와 통신 하는 데 사용할 내부 풀의 이름을 선택 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="e1525-168">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1525-169">여기에서 염두에 두어야 할 사항은 내부 풀이나 독립 실행형 서버가 이미 다른 비즈니스용 Skype 서버 Edge 서버를 사용 하 고 있는 경우 여러 연관을 가질 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="e1525-170">해당 상황에 해당 하는 내부 풀 또는 독립 실행형 서버를 선택 하는 경우에는 다른 Edge 서버에 대 한 경고가 표시 되며 계속할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="e1525-171">이 새로운 연결을 계속 하면 다른 Edge 서버와의 연결이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="e1525-172">다음 화면에서 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="e1525-173">이제이 업데이트 된 기술을 게시 하 고 [비즈니스용 Skype 서버에 edge 서버 배포](deploy-edge-servers.md) 의 지침에 따라 여기에서 edge Server에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="e1525-174">DNS 부하 분산 Edge 서버 풀에 대 한 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="e1525-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="e1525-175">비즈니스용 Skype server Standard Edition server 또는 비즈니스용 Skype Server 프런트 엔드 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="e1525-176">그런 다음 비즈니스용 **Skype 서버 토폴로지 작성기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="e1525-177">콘솔 트리에서 Edge 서버를 배포할 사이트를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="e1525-178">**Edge 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="e1525-179">**새 Edge 풀 정의** 화면에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="e1525-180">**Edge 풀 FQDN 정의** 화면에서 edge 풀에서 사용할 내부 FQDN (정규화 된 도메인 이름)을 입력 하 고, **여러 컴퓨터 풀**을 선택 하 고 완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="e1525-181">**기능 선택** 화면에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="e1525-182">SIP 액세스 서비스, 비즈니스용 Skype 서버 웹 회의 서비스, 그리고 A/V Edge 서비스에 대해 동일한 FQDN과 IP 주소를 사용 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="e1525-183">그렇다면 **단일 FQDN 및 IP 주소 사용 확인란** 을 선택 하 고 아래 9 단계에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1525-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="e1525-184">페더레이션을 사용 하도록 계획 하는 경우 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="e1525-185">**다음**을 클릭 하 고 나면 **IP 옵션** 화면에서 직접 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-185">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="e1525-186">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-186">Your options are as follows:</span></span>
    
    - <span data-ttu-id="e1525-187">내부 인터페이스에 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="e1525-188">내부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="e1525-189">외부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="e1525-190">외부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="e1525-191">IPv4 또는 IPv6 주소를 사용 하 고 있는지 여부와 관계 없이 Edge 서버에서 해당 주소를 내부적으로 또는 외부적으로 적용 하는 것이 좋습니다 (11 단계에서이를 염두에 두어야 함).</span><span class="sxs-lookup"><span data-stu-id="e1525-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="e1525-192">또한 외부 IP 주소에 대 한 NAT (network address translation) 주소를 사용 하도록 Edge 서버 또는 Edge 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="e1525-193">이 **Edge 풀의 외부 IP 주소를 NAT에서 번역 됨** 확인란을 선택 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="e1525-194">준비 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="e1525-195">외부 Fqdn 화면에서 선택한 항목은 위의 7 단계에서 선택한 항목에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="e1525-196">**단일 FQDN 및 IP 주소 사용** 확인란을 선택한 경우에는 **SIP 액세스** 상자에 단일 외부 FQDN을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="e1525-197">그런 다음 모든 edge 서비스에 대해 서로 다른 포트 번호를 입력 해야 모든 사용자가 독립적으로 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="e1525-198">**SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스에 대 한 444, **A/V** edge 서비스에 대 한 443을 5061 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="e1525-199">완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="e1525-200">**단일 FQDN 및 IP 주소 사용** 확인란을 선택 하지 않은 경우에는 **SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스, 그리고 **a/V** Edge 서비스에 대 한 세 개의 외부 fqdn을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="e1525-201">완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="e1525-202">이제 **이 풀의 컴퓨터 정의** 화면에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="e1525-203">**추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="e1525-204">이제 **내부 IP 주소 정의** 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="e1525-205">여기서는 8 단계에서 다시 선택한 항목에 따라 **내부 IPv4 주소** 및 **내부 IPv6 주소** 텍스트 상자에 Edge 서버의 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="e1525-206">준비 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="e1525-207">**외부 IP 주소 정의** 화면에는 이전 선택 사항에 따라 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="e1525-208">모든 서비스에 단일 FQDN을 사용 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="e1525-209">이 경우에는 사용 중인 외부 IPv4 또는 IPv6 주소를 **SIP Access** 텍스트 상자에 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="e1525-210">서비스에 대해 세 개의 개별 Fqdn과 IP 주소를 사용 하도록 선택 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="e1525-211">그러한 경우에는 **SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스, **A/V** Edge 서비스에 대 한 외부 IPv4 또는 IPv6 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1525-212">이전에 IPv6 주소 지정을 사용 하도록 선택 하지 않은 경우이 대화 상자가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-212">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="e1525-213">그 이유는 다음 단계로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-213">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="e1525-214">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-214">Click **Finish**.</span></span> <span data-ttu-id="e1525-215">방금 만든 Edge 서버가 이제 **이 풀의 컴퓨터 정의** 대화 상자에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="e1525-216">**이 풀의 컴퓨터 정의** 화면에서 **추가** 단추를 다시 클릭 하 고이 풀에서 사용할 모든 Edge 서버를 추가할 때까지 11 ~ 13 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="e1525-217">이 작업이 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="e1525-218">8 단계에서 NAT를 다시 사용 하도록 선택한 경우에는 이제 **공용 IP 주소** 텍스트 상자로 화면을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="e1525-219">A/V Edge 서비스에 대해 설정한 공용 IPv4 및/또는 IPv6 주소를 입력 해야 NAT에서 번역할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="e1525-220">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="e1525-221">다음 화면은 **다음 홉을 정의**합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="e1525-222">**다음 홉 풀** 상자에서 프런트 엔드 풀 또는 독립 실행형 풀 일 수 있는 내부 풀의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="e1525-223">해당 환경에 디렉터가 있는 경우에는 디렉터를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="e1525-224">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="e1525-225">**프런트 엔드 풀 연결** 화면에서이 Edge 서버와 연결 하려면 프런트 엔드 풀 및 스탠더드 버전 풀을 포함 하 여 하나 이상의 내부 풀을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="e1525-226">이 Edge 서버를 사용 하 여 지원 되는 외부 사용자와 통신 하는 데 사용할 내부 풀의 이름을 선택 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="e1525-227">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1525-228">여기에서 염두에 두어야 할 사항은 내부 풀이나 독립 실행형 서버가 이미 다른 비즈니스용 Skype 서버 Edge 서버를 사용 하 고 있는 경우 여러 연관을 가질 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="e1525-229">해당 상황에 해당 하는 내부 풀 또는 독립 실행형 서버를 선택 하는 경우에는 다른 Edge 서버에 대 한 경고가 표시 되며 계속할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="e1525-230">이 새로운 연결을 계속 하면 다른 Edge 서버와의 연결이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="e1525-231">다음 화면에서 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="e1525-232">이제이 업데이트 된 기술을 게시 하 고 [비즈니스용 Skype 서버에 edge 서버 배포](deploy-edge-servers.md) 의 지침에 따라 여기에서 edge Server에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="e1525-233">하드웨어 부하 분산 Edge 서버 풀에 대 한 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="e1525-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="e1525-234">비즈니스용 Skype server Standard Edition server 또는 비즈니스용 Skype Server 프런트 엔드 서버에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="e1525-235">그런 다음 비즈니스용 **Skype 서버 토폴로지 작성기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="e1525-236">콘솔 트리에서 Edge 서버를 배포할 사이트를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="e1525-237">**Edge 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 edge 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="e1525-238">**새 Edge 풀 정의** 화면에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="e1525-239">**Edge 풀 FQDN 정의** 화면에서 edge 풀에서 사용할 내부 FQDN (정규화 된 도메인 이름)을 입력 하 고, **여러 컴퓨터 풀**을 선택 하 고 완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="e1525-240">**기능 선택** 화면에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="e1525-241">SIP 액세스 서비스, 비즈니스용 Skype 서버 웹 회의 서비스, 그리고 A/V Edge 서비스에 대해 동일한 FQDN과 IP 주소를 사용 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="e1525-242">그렇다면 **단일 FQDN 및 IP 주소 사용 확인란** 을 선택 하 고 아래 9 단계에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1525-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="e1525-243">페더레이션을 사용 하도록 계획 하는 경우 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="e1525-244">**다음**을 클릭 하 고 나면 **IP 옵션** 화면에서 직접 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-244">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="e1525-245">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-245">Your options are as follows:</span></span>
    
   - <span data-ttu-id="e1525-246">내부 인터페이스에 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="e1525-247">내부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="e1525-248">외부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="e1525-249">외부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="e1525-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="e1525-250">IPv4 또는 IPv6 주소를 사용 하 고 있는지 여부와 관계 없이 Edge 서버에서 해당 주소를 내부적으로 또는 외부적으로 적용 하는 것이 좋습니다 (11 단계에서이를 염두에 두어야 함).</span><span class="sxs-lookup"><span data-stu-id="e1525-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="e1525-251">하드웨어 부하 분산 장치를 사용 하는 경우 다른 두 토폴로지 옵션의 경우와 달리 **Edge 풀의 외부 IP 주소가 NAT에서 번역 되**는 옵션을 선택 **하지 않아야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="e1525-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="e1525-252">이는 **지원 되지**않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="e1525-253">외부 Fqdn 화면에서 선택한 항목은 위의 7 단계에서 선택한 항목에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="e1525-254">**단일 FQDN 및 IP 주소 사용** 확인란을 선택한 경우에는 **SIP 액세스** 상자에 단일 외부 FQDN을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="e1525-255">그런 다음 모든 edge 서비스에 대해 서로 다른 포트 번호를 입력 해야 모든 사용자가 독립적으로 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="e1525-256">**SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스에 대 한 444, **A/V** edge 서비스에 대 한 443을 5061 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="e1525-257">완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="e1525-258">**단일 FQDN 및 IP 주소 사용** 확인란을 선택 하지 않은 경우에는 **SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스, 그리고 **a/V** Edge 서비스에 대 한 세 개의 외부 fqdn을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="e1525-259">완료 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="e1525-260">이제 **이 풀의 컴퓨터 정의** 화면에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="e1525-261">**추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="e1525-262">이제 **내부 IP 주소 정의** 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="e1525-263">여기서는 8 단계에서 다시 선택한 항목에 따라 **내부 IPv4 주소** 및 **내부 IPv6 주소** 텍스트 상자에 Edge 서버의 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="e1525-264">준비 되 면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="e1525-265">**외부 IP 주소 정의** 화면에는 이전 선택 사항에 따라 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="e1525-266">모든 서비스에 단일 FQDN을 사용 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="e1525-267">이 경우에는 사용 중인 외부 IPv4 또는 IPv6 주소를 **SIP Access** 텍스트 상자에 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="e1525-268">서비스에 대해 세 개의 개별 Fqdn과 IP 주소를 사용 하도록 선택 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="e1525-269">그러한 경우에는 **SIP 액세스** 에 지 서비스, **웹 회의** 에 지 서비스, **A/V** Edge 서비스에 대 한 외부 IPv4 또는 IPv6 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1525-270">이전에 IPv6 주소 지정을 사용 하도록 선택 하지 않은 경우이 대화 상자가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-270">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="e1525-271">그 이유는 다음 단계로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-271">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="e1525-272">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-272">Click **Finish**.</span></span> <span data-ttu-id="e1525-273">방금 만든 Edge 서버가 이제 **이 풀의 컴퓨터 정의** 대화 상자에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="e1525-274">**이 풀의 컴퓨터 정의** 화면에서 **추가** 단추를 다시 클릭 하 고이 풀에서 사용할 모든 Edge 서버를 추가할 때까지 11 ~ 13 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="e1525-275">이 작업이 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="e1525-276">다음 화면은 **다음 홉을 정의**합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="e1525-277">**다음 홉 풀** 상자에서 프런트 엔드 풀 또는 독립 실행형 풀 일 수 있는 내부 풀의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="e1525-278">해당 환경에 디렉터가 있는 경우에는 디렉터를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="e1525-279">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="e1525-280">**프런트 엔드 풀 연결** 화면에서이 Edge 서버와 연결 하려면 프런트 엔드 풀 및 스탠더드 버전 풀을 포함 하 여 하나 이상의 내부 풀을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="e1525-281">이 Edge 서버를 사용 하 여 지원 되는 외부 사용자와 통신 하는 데 사용할 내부 풀의 이름을 선택 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="e1525-282">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1525-283">여기에서 염두에 두어야 할 사항은 내부 풀이나 독립 실행형 서버가 이미 다른 비즈니스용 Skype 서버 Edge 서버를 사용 하 고 있는 경우 여러 연관을 가질 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="e1525-284">해당 상황에 해당 하는 내부 풀 또는 독립 실행형 서버를 선택 하는 경우에는 다른 Edge 서버에 대 한 경고가 표시 되며 계속할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="e1525-285">이 새로운 연결을 계속 하면 다른 Edge 서버와의 연결이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="e1525-286">다음 화면에서 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="e1525-287">이제이 업데이트 된 기술을 게시 하 고 [비즈니스용 Skype 서버에 edge 서버 배포](deploy-edge-servers.md) 의 지침에 따라 여기에서 edge Server에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="e1525-288">Edge 서버 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="e1525-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="e1525-289">위의 단계를 완료 한 후에는이 새로운 토폴로지를 게시 하 여 비즈니스용 Skype 서버에 지 서버 또는 Edge 풀로 내보낼 수 있도록 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="e1525-290">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="e1525-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="e1525-291">**토폴로지 작성기** 를 시작 합니다 (이전 절차에서 아직 시작 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="e1525-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="e1525-292">**토폴로지 작성기**의 콘솔 트리에서 **비즈니스용 skype 서버** 를 마우스 오른쪽 단추로 클릭 한 다음 **비즈니스용 skype server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="e1525-293">마법사의 **시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="e1525-294">**다른 데이터베이스 만들기** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="e1525-295">상태가 데이터베이스를 성공적으로 생성 했음을 나타내는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="e1525-296">로그를 보려면 **로그 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="e1525-297">마법사를 닫으려면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="e1525-298">Edge 서버 토폴로지 내보내기</span><span class="sxs-lookup"><span data-stu-id="e1525-298">Export your Edge Server topology</span></span>

<span data-ttu-id="e1525-299">성공적으로 배포 하려면 비즈니스용 Skype 서버 배포 마법사에서 중앙 관리 저장소 데이터에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="e1525-300">도메인 또는 포리스트의 내부 서버에는 일반적으로 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="e1525-301">Edge 서버는 도메인 외부에 있으므로 일반적으로 실제 미디어에서 토폴로지 파일을 Edge 서버 위치에 수동으로 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="e1525-302">이 내보내기는 PowerShell을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="e1525-303">**비즈니스용 Skype 서버 관리 셸을**시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e1525-304">**비즈니스용 Skype 서버 관리 셸에서**다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="e1525-305">내보낸 파일을 외부 미디어 (예: Edge 서버의 위치에서 연결할 수 있는 USB 드라이브 또는 네트워크 공유)에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1525-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

