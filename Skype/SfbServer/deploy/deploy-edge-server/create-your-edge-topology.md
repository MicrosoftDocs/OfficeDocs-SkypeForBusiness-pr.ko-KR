---
title: 비즈니스용 Skype 서버에 대한 에지 토폴로지 만들기
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
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: '요약: 비즈니스용 Skype 서버에서 에지 서버 토폴로지 작성, 게시 및 내보내는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 8dff318b5d198eb1e8d59ef465bf648125f31327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804398"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="3c30a-103">비즈니스용 Skype 서버에 대한 에지 토폴로지 만들기</span><span class="sxs-lookup"><span data-stu-id="3c30a-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="3c30a-104">**요약:** 비즈니스용 Skype 서버에서 에지 서버 토폴로지 작성, 게시 및 내보내기 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="3c30a-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="3c30a-105">토폴로지 작성기에서는 비즈니스용 Skype 서버의 토폴로지 구성 요소에 사용되는 에지 서버 토폴로지 빌드에 필요한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="3c30a-106">아래 단계를 수행하기 전에 하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="3c30a-107">이 문서에서는 다음 항목에 대해 다듬습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="3c30a-108">에지 서버 토폴로지 빌드</span><span class="sxs-lookup"><span data-stu-id="3c30a-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="3c30a-109">에지 서버 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="3c30a-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="3c30a-110">에지 서버 토폴로지 내보내기</span><span class="sxs-lookup"><span data-stu-id="3c30a-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="3c30a-111">아래 단계를 수행하려면 아래 언급된 도메인 서버에 다음 도메인 그룹의 구성원인 사용자로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="3c30a-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3c30a-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="3c30a-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="3c30a-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="3c30a-114">에지 서버 토폴로지 빌드</span><span class="sxs-lookup"><span data-stu-id="3c30a-114">Build your Edge Server topology</span></span>

<span data-ttu-id="3c30a-115">첫 번째 배포 단계는 세 가지 옵션 중 하나로 구성된 비즈니스용 Skype 서버 에지 서버 토폴로지 구축입니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="3c30a-116">단일 에지 서버</span><span class="sxs-lookup"><span data-stu-id="3c30a-116">A single Edge Server</span></span>
    
- <span data-ttu-id="3c30a-117">DNS 부하가 균형 있는 에지 풀(하나 이상의 서버)</span><span class="sxs-lookup"><span data-stu-id="3c30a-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="3c30a-118">하드웨어 부하가 균형 잡힌 에지 풀(하나 이상의 서버)</span><span class="sxs-lookup"><span data-stu-id="3c30a-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="3c30a-119">필요한 것이 확실하지 않은 경우 이러한 단계를 수행하기 전에 계획 설명서를 참조하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-119">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation.</span></span> <span data-ttu-id="3c30a-120">그렇지 않은 경우 먼저 시작해보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-120">Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="3c30a-121">단일 에지 서버에 대한 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="3c30a-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="3c30a-122">비즈니스용 Skype 서버 Standard Edition 서버 또는 비즈니스용 Skype 서버 프런트 엔드 풀에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="3c30a-123">그런 다음 **비즈니스용 Skype 서버 토폴로지 작성기 를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="3c30a-124">콘솔 트리에서 에지 서버를 배포할 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="3c30a-125">에지 풀을 마우스 오른쪽 **단추로 클릭한** 다음 새 에지 **풀을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="3c30a-126">새 **에지** 풀 정의 화면에서 **다음을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="3c30a-127">에지 풀 FQDN 정의 화면에서 에지 서버에서 사용할 내부 **FQDN(FQDN)을** 입력하고 단일 컴퓨터 풀을 선택하고 **완료하면** 다음을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="3c30a-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="3c30a-128">기능 **선택 화면에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="3c30a-129">SIP 액세스 서비스, 비즈니스용 Skype 서버 웹 회의 서비스 및 A/V 에지 서비스에 동일한 FQDN 및 IP 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="3c30a-130">그렇다면 단일 **FQDN** 및 IP 주소 확인란을 선택해야 합니다(아래 9단계에 대해 유의).</span><span class="sxs-lookup"><span data-stu-id="3c30a-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="3c30a-131">페더전을 사용하도록 설정하려면 이 에지 풀(포트 **5061)에** 대해 페더ation 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="3c30a-132">다음을 클릭하면 **IP** 옵션 화면이 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="3c30a-132">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="3c30a-133">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-133">Your options are as follows:</span></span>
    
   - <span data-ttu-id="3c30a-134">내부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="3c30a-135">내부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="3c30a-136">외부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="3c30a-137">외부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="3c30a-138">이러한 주소는 IPv4 또는 IPv6 주소를 사용하며 에지 서버에서 내부 또는 외부적으로 이러한 주소를 적용하는지 여부를 잘 알 수 있습니다(10단계에서는 이 점에 유의해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="3c30a-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="3c30a-139">또한 외부 IP 주소에 NAT(Network Address Translation) 주소를 사용하기 위해 에지 서버 또는 에지 풀을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="3c30a-140">이 작업을 위해 이 에지 풀의 외부 IP 주소가 **NAT** 확인란으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="3c30a-141">준비되면 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="3c30a-142">외부 FQDNs 화면에서 선택은 위의 7단계에서 선택한 대로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="3c30a-143">**단일 FQDN** 및 IP 주소 사용 확인란을 선택한 경우 **SIP 액세스** 상자에 단일 외부 FQDN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="3c30a-144">그런 다음 각 에지 서비스에 대해 서로 다른 포트 번호를 입력하여 모두 독립적으로 연결할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="3c30a-145">**SIP** 액세스 에지 서비스의 경우 5061, 웹  회의 에지 서비스의 경우 444, **A/V** 에지 서비스의 경우 443을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="3c30a-146">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="3c30a-147">단일 **FQDN** 및 IP 주소 사용 확인란을 선택하지 않은 경우 **이제 SIP** 액세스 에지 서비스, 웹 회의  에지 서비스 및 **A/V** 에지 서비스에 대해 세 개의 외부 FQDN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="3c30a-148">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="3c30a-149">이제 내부 IP 주소 정의 **화면이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="3c30a-150">8단계에서 선택한 선택에 따라 내부 **IPv4** 주소 및 내부 **IPv6** 주소 텍스트 상자에 에지 서버의 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="3c30a-151">준비되면 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="3c30a-152">외부 **IP** 주소 정의 화면에서 이전 선택에 따라 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="3c30a-153">모든 서비스에 단일 FQDN을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="3c30a-154">그렇다면 외부 IPv4 또는 IPv6 주소(사용 중)를 **SIP 액세스** 텍스트 상자에 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="3c30a-155">서비스에 세 개의 개별 FQDN 및 IP 주소를 사용하기로 선택한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="3c30a-156">이 경우 **SIP** 액세스 에지 서비스, 웹 회의 에지 서비스 및 **A/V** 에지 서비스의 외부 IPv4 또는 IPv6 주소를 입력하고 다음을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="3c30a-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c30a-157">이전에 IPv6 주소 지정을 사용하도록 설정하고 할당하지 않은 경우 이 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-157">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="3c30a-158">정상입니다. 다음 단계로 이동하면됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-158">That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="3c30a-159">8단계에서 NAT를 다시 사용하기로 선택한 경우 이제 공용 IP 주소 텍스트 상자가 있는 **화면이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="3c30a-160">NAT에서 변환하려면 A/V 에지 서비스에 대해 설정한 공용 IPv4 및/또는 IPv6 주소를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="3c30a-161">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="3c30a-162">다음 화면은 다음 **홉 정의입니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="3c30a-163">다음 **홉 풀** 상자에서 프런트 엔드 풀 또는 독립 실행형 풀일 수 있는 내부 풀의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="3c30a-164">환경에 있는 감독이 있는 경우 감독을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="3c30a-165">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="3c30a-166">프런트  엔드 풀 연결 화면에서 이 에지 서버와 연결하려면 하나 이상의 내부 풀(프런트 엔드 풀 및 Standard Edition Server 포함)을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="3c30a-167">이 에지 서버를 사용하여 지원되는 외부 사용자와 통신할 내부 풀의 이름을 선택하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="3c30a-168">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c30a-169">내부 풀 또는 독립 실행형 서버가 이미 다른 비즈니스용 Skype 서버 에지 서버를 사용하고 있는 경우 여러 개의 연결은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="3c30a-170">해당 상황에 있는 내부 풀 또는 독립 실행형 서버를 선택하면 다른 에지 서버에 대한 경고가 표시되고 계속할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="3c30a-171">이 새 연결을 진행하면 다른 에지 서버에 대한 연결이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="3c30a-172">다음 **화면에서 마친을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="3c30a-173">이제 이 업데이트된 기술을 게시하고 비즈니스용 Skype 서버에서 [에지](deploy-edge-servers.md) 서버 배포의 지침에 따라 여기에서 에지 서버에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="3c30a-174">DNS 부하가 균형 있는 에지 서버 풀에 대한 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="3c30a-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="3c30a-175">비즈니스용 Skype 서버 Standard Edition 서버 또는 비즈니스용 Skype 서버 프런트 엔드 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="3c30a-176">그런 다음 **비즈니스용 Skype 서버 토폴로지 작성기 를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="3c30a-177">콘솔 트리에서 에지 서버를 배포할 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="3c30a-178">에지 풀을 마우스 오른쪽 **단추로 클릭한** 다음 새 에지 **풀을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="3c30a-179">새 **에지** 풀 정의 화면에서 **다음을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="3c30a-180">에지 풀 FQDN 정의 화면에서 에지 풀에서 사용할 내부 **FQDN(FQDN)을** 입력하고 여러 컴퓨터 풀을 선택하고 완료 **시** 다음을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="3c30a-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="3c30a-181">기능 **선택 화면에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="3c30a-182">SIP 액세스 서비스, 비즈니스용 Skype 서버 웹 회의 서비스 및 A/V 에지 서비스에 동일한 FQDN 및 IP 주소를 사용하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="3c30a-183">그렇다면 단일 **FQDN** 및 IP 주소 확인란을 선택해야 합니다(아래 9단계에 대해 유의).</span><span class="sxs-lookup"><span data-stu-id="3c30a-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="3c30a-184">페더전을 사용하도록 설정하려면 이 에지 풀(포트 **5061)에** 대해 페더ation 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="3c30a-185">다음을 클릭하면 **IP** 옵션 화면이 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="3c30a-185">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="3c30a-186">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-186">Your options are as follows:</span></span>
    
    - <span data-ttu-id="3c30a-187">내부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="3c30a-188">내부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="3c30a-189">외부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="3c30a-190">외부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="3c30a-191">이러한 주소는 IPv4 또는 IPv6 주소를 사용하며 에지 서버에서 내부 또는 외부적으로 이러한 주소를 적용하는지 여부를 잘 알 수 있습니다(11단계에서는 이 점에 유의해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="3c30a-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="3c30a-192">또한 외부 IP 주소에 NAT(Network Address Translation) 주소를 사용하기 위해 에지 서버 또는 에지 풀을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="3c30a-193">이 작업을 위해 이 에지 풀의 외부 IP 주소가 **NAT** 확인란으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="3c30a-194">준비되면 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="3c30a-195">외부 FQDNs 화면에서 선택은 위의 7단계에서 선택한 대로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="3c30a-196">**단일 FQDN** 및 IP 주소 사용 확인란을 선택한 경우 **SIP 액세스** 상자에 단일 외부 FQDN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="3c30a-197">그런 다음 각 에지 서비스에 대해 서로 다른 포트 번호를 입력하여 모두 독립적으로 연결할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="3c30a-198">**SIP** 액세스 에지 서비스의 경우 5061, 웹  회의 에지 서비스의 경우 444, **A/V** 에지 서비스의 경우 443을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="3c30a-199">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="3c30a-200">단일 **FQDN** 및 IP 주소 사용 확인란을 선택하지 않은 경우 **이제 SIP** 액세스 에지 서비스, 웹 회의  에지 서비스 및 **A/V** 에지 서비스에 대해 세 개의 외부 FQDN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="3c30a-201">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="3c30a-202">이제 이 풀 화면의 컴퓨터 **정의에 도달했습니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="3c30a-203">추가 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="3c30a-204">이제 내부 IP 주소 정의 **화면이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="3c30a-205">8단계에서 선택한 선택에 따라 내부 **IPv4** 주소 및 내부 **IPv6** 주소 텍스트 상자에 에지 서버의 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="3c30a-206">준비되면 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="3c30a-207">외부 **IP** 주소 정의 화면에서 이전 선택에 따라 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="3c30a-208">모든 서비스에 단일 FQDN을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="3c30a-209">그렇다면 외부 IPv4 또는 IPv6 주소(사용 중)를 **SIP 액세스** 텍스트 상자에 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="3c30a-210">서비스에 세 개의 개별 FQDN 및 IP 주소를 사용하기로 선택한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="3c30a-211">이 경우 **SIP** 액세스 에지 서비스, 웹 회의 에지 서비스 및 **A/V** 에지 서비스의 외부 IPv4 또는 IPv6 주소를 입력하고 다음을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="3c30a-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c30a-212">이전에 IPv6 주소 지정을 사용하도록 설정하고 할당하지 않은 경우 이 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-212">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="3c30a-213">정상입니다. 다음 단계로 이동하면됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-213">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="3c30a-214">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-214">Click **Finish**.</span></span> <span data-ttu-id="3c30a-215">방금 만든 에지 서버가  이 풀의 컴퓨터 정의 대화 상자에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="3c30a-216">이 풀  화면의 컴퓨터 정의 화면에서  추가 단추를 다시 클릭하고 이 풀에 사용하려는 모든 에지 서버를 추가할 때까지 11~13단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="3c30a-217">완료된 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="3c30a-218">8단계에서 NAT를 다시 사용하기로 선택한 경우 이제 공용 IP 주소 텍스트 상자가 있는 **화면이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="3c30a-219">NAT에서 변환하려면 A/V 에지 서비스에 대해 설정한 공용 IPv4 및/또는 IPv6 주소를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="3c30a-220">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="3c30a-221">다음 화면은 다음 **홉 정의입니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="3c30a-222">다음 **홉 풀** 상자에서 프런트 엔드 풀 또는 독립 실행형 풀일 수 있는 내부 풀의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="3c30a-223">환경에 있는 감독이 있는 경우 감독을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="3c30a-224">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="3c30a-225">프런트  엔드 풀 연결 화면에서 이 에지 서버와 연결하려면 하나 이상의 내부 풀(프런트 엔드 풀 및 Standard Edition 풀 포함)을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="3c30a-226">이 에지 서버를 사용하여 지원되는 외부 사용자와 통신할 내부 풀의 이름을 선택하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="3c30a-227">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c30a-228">내부 풀 또는 독립 실행형 서버가 이미 다른 비즈니스용 Skype 서버 에지 서버를 사용하고 있는 경우 여러 개의 연결은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="3c30a-229">해당 상황에 있는 내부 풀 또는 독립 실행형 서버를 선택하면 다른 에지 서버에 대한 경고가 표시되고 계속할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="3c30a-230">이 새 연결을 진행하면 다른 에지 서버에 대한 연결이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="3c30a-231">다음 **화면에서 마친을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="3c30a-232">이제 이 업데이트된 기술을 게시하고 비즈니스용 Skype 서버에서 [에지](deploy-edge-servers.md) 서버 배포의 지침에 따라 여기에서 에지 서버에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="3c30a-233">하드웨어 부하가 균형 있는 에지 서버 풀에 대한 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="3c30a-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="3c30a-234">비즈니스용 Skype 서버 Standard Edition 서버 또는 비즈니스용 Skype 서버 프런트 엔드 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="3c30a-235">그런 다음 **비즈니스용 Skype 서버 토폴로지 작성기 를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="3c30a-236">콘솔 트리에서 에지 서버를 배포할 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="3c30a-237">에지 풀을 마우스 오른쪽 **단추로 클릭한** 다음 새 에지 **풀을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="3c30a-238">새 **에지** 풀 정의 화면에서 **다음을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="3c30a-239">에지 풀 FQDN 정의 화면에서 에지 풀에서 사용할 내부 **FQDN(FQDN)을** 입력하고 여러 컴퓨터 풀을 선택하고 완료 **시** 다음을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="3c30a-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="3c30a-240">기능 **선택 화면에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="3c30a-241">SIP 액세스 서비스, 비즈니스용 Skype 서버 웹 회의 서비스 및 A/V 에지 서비스에 동일한 FQDN 및 IP 주소를 사용하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="3c30a-242">그렇다면 단일 **FQDN** 및 IP 주소 확인란을 선택해야 합니다(아래 9단계에 대해 유의).</span><span class="sxs-lookup"><span data-stu-id="3c30a-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="3c30a-243">페더전을 사용하도록 설정하려면 이 에지 풀(포트 **5061)에** 대해 페더ation 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="3c30a-244">다음을 클릭하면 **IP** 옵션 화면이 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="3c30a-244">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="3c30a-245">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-245">Your options are as follows:</span></span>
    
   - <span data-ttu-id="3c30a-246">내부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="3c30a-247">내부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="3c30a-248">외부 인터페이스에서 IPv4 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="3c30a-249">외부 인터페이스에서 IPv6 사용</span><span class="sxs-lookup"><span data-stu-id="3c30a-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="3c30a-250">이러한 주소는 IPv4 또는 IPv6 주소를 사용하며 에지 서버에서 내부 또는 외부적으로 이러한 주소를 적용하는지 여부를 잘 알 수 있습니다(11단계에서는 이 점에 유의해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="3c30a-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="3c30a-251">다른 두 토폴로지 옵션과 달리 하드웨어 부하  균형 조정 기능을 사용하는 경우 에지 풀의 외부 IP 주소가 NAT로 변환되는 옵션을 선택하지 **말아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="3c30a-252">지원되지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="3c30a-253">외부 FQDNs 화면에서 선택은 위의 7단계에서 선택한 대로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="3c30a-254">**단일 FQDN** 및 IP 주소 사용 확인란을 선택한 경우 **SIP 액세스** 상자에 단일 외부 FQDN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="3c30a-255">그런 다음 각 에지 서비스에 대해 서로 다른 포트 번호를 입력하여 모두 독립적으로 연결할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="3c30a-256">**SIP** 액세스 에지 서비스의 경우 5061, 웹  회의 에지 서비스의 경우 444, **A/V** 에지 서비스의 경우 443을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="3c30a-257">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="3c30a-258">단일 **FQDN** 및 IP 주소 사용 확인란을 선택하지 않은 경우 **이제 SIP** 액세스 에지 서비스, 웹 회의  에지 서비스 및 **A/V** 에지 서비스에 대해 세 개의 외부 FQDN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="3c30a-259">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="3c30a-260">이제 이 풀 화면의 컴퓨터 **정의에 도달했습니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="3c30a-261">추가 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="3c30a-262">이제 내부 IP 주소 정의 **화면이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="3c30a-263">8단계에서 선택한 선택에 따라 내부 **IPv4** 주소 및 내부 **IPv6** 주소 텍스트 상자에 에지 서버의 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="3c30a-264">준비되면 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="3c30a-265">외부 **IP** 주소 정의 화면에서 이전 선택에 따라 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="3c30a-266">모든 서비스에 단일 FQDN을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="3c30a-267">그렇다면 외부 IPv4 또는 IPv6 주소(사용 중)를 **SIP 액세스** 텍스트 상자에 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="3c30a-268">서비스에 세 개의 개별 FQDN 및 IP 주소를 사용하기로 선택한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="3c30a-269">이 경우 **SIP** 액세스 에지 서비스, 웹 회의 에지 서비스 및 **A/V** 에지 서비스의 외부 IPv4 또는 IPv6 주소를 입력하고 다음을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="3c30a-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c30a-270">이전에 IPv6 주소 지정을 사용하도록 설정하고 할당하지 않은 경우 이 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-270">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="3c30a-271">정상입니다. 다음 단계로 이동하면됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-271">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="3c30a-272">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-272">Click **Finish**.</span></span> <span data-ttu-id="3c30a-273">방금 만든 에지 서버가  이 풀의 컴퓨터 정의 대화 상자에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="3c30a-274">이 풀  화면의 컴퓨터 정의 화면에서  추가 단추를 다시 클릭하고 이 풀에 사용하려는 모든 에지 서버를 추가할 때까지 11~13단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="3c30a-275">완료된 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="3c30a-276">다음 화면은 다음 **홉 정의입니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="3c30a-277">다음 **홉 풀** 상자에서 프런트 엔드 풀 또는 독립 실행형 풀일 수 있는 내부 풀의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="3c30a-278">환경에 있는 감독이 있는 경우 감독을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="3c30a-279">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="3c30a-280">프런트  엔드 풀 연결 화면에서 이 에지 서버와 연결하려면 하나 이상의 내부 풀(프런트 엔드 풀 및 Standard Edition 풀 포함)을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="3c30a-281">이 에지 서버를 사용하여 지원되는 외부 사용자와 통신할 내부 풀의 이름을 선택하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="3c30a-282">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c30a-283">내부 풀 또는 독립 실행형 서버가 이미 다른 비즈니스용 Skype 서버 에지 서버를 사용하고 있는 경우 여러 개의 연결은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="3c30a-284">해당 상황에 있는 내부 풀 또는 독립 실행형 서버를 선택하면 다른 에지 서버에 대한 경고가 표시되고 계속할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="3c30a-285">이 새 연결을 진행하면 다른 에지 서버에 대한 연결이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="3c30a-286">다음 **화면에서 마친을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="3c30a-287">이제 이 업데이트된 기술을 게시하고 비즈니스용 Skype 서버에서 [에지](deploy-edge-servers.md) 서버 배포의 지침에 따라 여기에서 에지 서버에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="3c30a-288">에지 서버 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="3c30a-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="3c30a-289">위의 단계를 완료한 후 이 새 토폴로지가 게시됩니다. 그러면 비즈니스용 Skype 서버 에지 서버 또는 에지 풀로 토폴로지도 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="3c30a-290">아래 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="3c30a-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="3c30a-291">**토폴로지 작성기** 시작(이전 절차에서 아직 시작되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="3c30a-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="3c30a-292">**토폴로지 작성기의** 콘솔 트리에서 비즈니스용 **Skype** 서버를 마우스 오른쪽 단추로 클릭한 다음 비즈니스용 Skype 서버 토폴로지 **작성기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="3c30a-293">마법사의 **시작** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="3c30a-294">**다른 데이터베이스 만들기** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="3c30a-295">상태가 데이터베이스 만들기가 성공했다고 표시되면 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="3c30a-296">로그를 보려면 **로그 보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="3c30a-297">마법사를 닫으려면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="3c30a-298">에지 서버 토폴로지 내보내기</span><span class="sxs-lookup"><span data-stu-id="3c30a-298">Export your Edge Server topology</span></span>

<span data-ttu-id="3c30a-299">성공적으로 배포하기 위해 비즈니스용 Skype 서버 배포 마법사는 중앙 관리 저장소 데이터에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="3c30a-300">도메인 또는 포리스트의 내부 서버의 경우 일반적으로 이 작업은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="3c30a-301">에지 서버는 도메인 외부에 있으므로 일반적으로 실제 미디어에서 에지 서버 위치로 토폴로지 파일을 수동으로 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="3c30a-302">이 내보내기는 PowerShell을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="3c30a-303">비즈니스용 **Skype 서버 관리 셸을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c30a-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3c30a-304">비즈니스용 **Skype 서버 관리 셸에서** 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="3c30a-305">내보낼 파일을 외부 미디어(예: 에지 서버의 위치에서 연결할 수 있는 USB 드라이브 또는 네트워크 공유)에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3c30a-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

