---
title: Business Voice에 대한 인터넷 연결 확인
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 473c053036b766ef475c3aed5f0bba2d24dd9e6c
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824886"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="5bb29-102">Business Voice에 대한 인터넷 연결 확인</span><span class="sxs-lookup"><span data-stu-id="5bb29-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="5bb29-103">Business Voice는 Microsoft 365에서 클라우드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="5bb29-104">Microsoft Teams 및 Business Voice를 사용하는 모든 장치는 인터넷 연결을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-104">Every device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="5bb29-105">최적의 Business Voice 환경을 위해 어느 특정 시간에 조직에서 사용할 수 있는 최대 전화 통화의 수를 지원할 수 있도록 광대역 인터넷 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-105">To get the best Business Voice experience, you need a broadband Internet connection that can support the maximum number of phone calls that your organization might make at any one time.</span></span> <span data-ttu-id="5bb29-106">또한 사용자의 네트워크의 컴퓨터가 Microsoft 365 서버에 연결할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-106">You also need to make sure that the computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="5bb29-107">이 단계를 따르려면 다음의 구독 중 하나를 포함하는 테넌트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="5bb29-108">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="5bb29-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="5bb29-109">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="5bb29-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="5bb29-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="5bb29-110">Office 365 E1</span></span>
* <span data-ttu-id="5bb29-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="5bb29-111">Office 365 E3</span></span>
* <span data-ttu-id="5bb29-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="5bb29-112">Office 365 F1</span></span>
* <span data-ttu-id="5bb29-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="5bb29-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="5bb29-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="5bb29-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="5bb29-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="5bb29-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="5bb29-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="5bb29-116">Microsoft 365 Business</span></span>

<span data-ttu-id="5bb29-117">이들 단계를 따르기 위해 Business Voice 라이선스가 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="5bb29-118">인터넷 연결 속도를 확인합니다</span><span class="sxs-lookup"><span data-stu-id="5bb29-118">Check your Internet connection speed</span></span>

<span data-ttu-id="5bb29-119">이 문서는 사용자의 인터넷 연결이 전화를 걸고 화상 회의를 호스팅해야 하는 사용자의 수를 수용하기에 충분히 빠른지를 확인하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-119">This article helps determine whether your Internet connection is fast enough for the number of people who need to make phone calls and host video conferences.</span></span> <span data-ttu-id="5bb29-120">사용자는 조직에 대한 정보를 제공하고 Teams 및 Business Voice로 인해 사용될 인터넷 연결의 용량을 보여주는 보고서를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-120">You'll provide information about your organization and get back a report that shows how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="5bb29-121">인터넷 연결 및 사용자에 대한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="5bb29-121">Gather information about your Internet connection and users</span></span>

<span data-ttu-id="5bb29-122">시작하기 전에 다음의 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-122">Before you start, you need the following information:</span></span>

* <span data-ttu-id="5bb29-123">인터넷 연결 속도.</span><span class="sxs-lookup"><span data-stu-id="5bb29-123">The speed of your Internet connection</span></span>
* <span data-ttu-id="5bb29-124">사무실에서 Business Voice를 주로 사용하는 사용자의 수</span><span class="sxs-lookup"><span data-stu-id="5bb29-124">How many people will use Business Voice mainly from your office</span></span>
* <span data-ttu-id="5bb29-125">홈 사무실과 같이 주로 원격 위치에서 Business Voice를 사용하는 사용자의 수</span><span class="sxs-lookup"><span data-stu-id="5bb29-125">How many people will use Business Voice mainly from a remote location, such as a home office</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="5bb29-126">네트워크 플래너에 사용자 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-126">Enter your information into the network planner</span></span>

<span data-ttu-id="5bb29-127">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="5bb29-127">Follow these steps:</span></span>

1. <span data-ttu-id="5bb29-128">브라우저에서 https://admin.teams.microsoft.com로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="5bb29-129">전역 관리자 권한이 있는 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="5bb29-130">Office 365에 등록하기 위해 사용한 계정에는 이러한 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-130">The account that you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="5bb29-131">**계획**을 열고 **네트워크 플래너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-131">Open **Planning** and select **Network planner**.</span></span>
3. <span data-ttu-id="5bb29-132">**네트워크 플랜**에서 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="5bb29-133">플랜에 이름을 입력하고 **적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="5bb29-134">네트워크 플랜은 다음과 같이 보여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-134">Your network plan should look like this:</span></span>

    ![네트워크 플래너의 메인 화면](../media/network-planner-main.png)
1. <span data-ttu-id="5bb29-136">네트워크 플랜의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-136">Select the name of your network plan.</span></span> <span data-ttu-id="5bb29-137">(이전 그림에서 **기본 office**입니다.)</span><span class="sxs-lookup"><span data-stu-id="5bb29-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="5bb29-138">다음 페이지에서 **네트워크 사이트**탭의 **네트워크 사이트 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-138">On the next page, select **Add a network site** on the **Network sites** tab.</span></span>
3. <span data-ttu-id="5bb29-139">다음의 스크린샷에 표시된 항목만 입력하고 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-139">Fill in only the fields that are indicated in the following screenshot, and then select **Save**.</span></span> <span data-ttu-id="5bb29-140">화면의 나머지 항목은 빈 칸으로 두고, **ExpressRoute**나 **WAN에 연결됨** 옵션은 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-140">Leave the other fields on this screen blank, and don't select the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![네트워크 플래너 사이트 정보](../media/network-planner-site-info.png)
1. <span data-ttu-id="5bb29-142">**보고서** 탭에서 **보고서 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-142">On the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="5bb29-143">다음 정보를 입력하고 **보고서 생성**을 선택하면 Teams에서 필요한 대역폭을 보여주는 보고서가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-143">Enter the following information, and then select **Generate report** to create a report that shows the bandwidth requirements for Teams.</span></span> <span data-ttu-id="5bb29-144">다음 항목에서 보고서를 보는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-144">We show you how to read the report in the next section.</span></span>

    ![네트워크 플래너 보고서 정보](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="5bb29-146">최소 인터넷 연결 속도를 확인합니다</span><span class="sxs-lookup"><span data-stu-id="5bb29-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="5bb29-147">**보고서 작성**을 선택 시 Office 365에서 다음과 같이 표시되는 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![네트워크 플래너 보고서의 세부 정보](../media/network-planner-report.png)

<span data-ttu-id="5bb29-149">강조 표시된 숫자는 Teams와 Business Voice가 사용할 인터넷 연결의 용량을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="5bb29-150">이 숫자가 총 인터넷 연결 속도의 30%를 넘지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-150">We recommend that this number is no more than 30 percent of your total Internet connection speed.</span></span> <span data-ttu-id="5bb29-151">예를 들어 인터넷 연결 속도가 60Mbps인 경우 Teams 및 Business Voice는 18Mbps 이상을 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-151">For example, if your Internet connection is 60 Mbps, Teams and Business Voice should use no more than 18 Mbps.</span></span>

<span data-ttu-id="5bb29-152">다음 수식을 사용하여 최소 인터넷 연결 속도를 확인합니다. *\<강조 표시된 숫자>/0.3*.</span><span class="sxs-lookup"><span data-stu-id="5bb29-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="5bb29-153">이전 이미지에서 강조 표시된 번호를 사용하면 계산은 *4.6875/0.3 = 15.6*이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="5bb29-154">이 경우 인터넷 연결 속도는 적어도 15.6Mbps이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="5bb29-155">Teams 및 Business Voice에서 전체 인터넷 연결 속도의 30% 이상을 사용하는 경우 강조 표시된 숫자가 빨간색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-155">If Teams and Business Voice will use more than 30 percent of your total Internet connection speed, the highlighted number will appear red.</span></span> <span data-ttu-id="5bb29-156">이 경우 인터넷 연결을 업그레이드해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-156">In that case, you may need to upgrade your Internet connection.</span></span>

![연결 속도 경고](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="5bb29-158">사용자의 네트워크의 컴퓨터 및 장치가 Microsoft 365에 연결될 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-158">Make sure the computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="5bb29-159">Business Voice를 사용하는 컴퓨터 및 장치는 특정 네트워크 포트를 사용하여 Microsoft 365 서버와 통신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="5bb29-160">이러한 포트는 기본적으로 네트워크 또는 인터넷을 통해 모든 장치가 서로 통신할 수 있는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-160">These ports are essentially doors through which devices talk to each other over a network or the Internet.</span></span> <span data-ttu-id="5bb29-161">사용자의 방화벽은 네트워크의 장치가 다음의 *아웃바운드* 네트워크 포트를 사용하여 Microsoft 365에 연결될 수 있도록 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-161">Your firewall needs to allow devices on your network to reach Microsoft 365 through the following *outbound* network ports:</span></span>

* <span data-ttu-id="5bb29-162">**TCP 포트** 80 및 443</span><span class="sxs-lookup"><span data-stu-id="5bb29-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="5bb29-163">**UDP 포트** 3478, 3479, 3480 및 3481</span><span class="sxs-lookup"><span data-stu-id="5bb29-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="5bb29-164">사용자의 방화벽이 이러한 네트워크 포트에서의 통신을 허용하는지를 확인하는 가장 쉬운 방법은 Teams에서 테스트 통화를 해보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call in Teams:</span></span>

1. <span data-ttu-id="5bb29-165">사용자의 네트워크의 컴퓨터에서 https://aka.ms/getteams로 이동하여 Teams를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-165">Go to https://aka.ms/getteams on a computer on your network and install Teams.</span></span> <span data-ttu-id="5bb29-166">컴퓨터에 스피커와 마이크가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="5bb29-167">Teams를 열고 Microsoft 365 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-167">Open Teams and sign in by using a Microsoft 365 account.</span></span>
3. <span data-ttu-id="5bb29-168">Teams에서 프로필 사진을 선택하고 **설정** > **장치**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-168">In Teams, select your profile picture, and then go to **Settings** > **Devices**.</span></span>
4. <span data-ttu-id="5bb29-169">**오디오 장치**에서 **테스트 통화**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="5bb29-170">단계를 따라 메시지를 남기고 사용자에게 다시 재생되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-170">Follow the steps to leave a message and have it played back to you.</span></span>

   * <span data-ttu-id="5bb29-171">통화가 연결되고 메시지가 들린다면 방화벽이 제대로 설정된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-171">If the call connects and you hear your message, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="5bb29-172">통화가 연결되지만 안내 음성이나 메시지가 들리지 않으면 스피커 및 마이크가 컴퓨터에서 제대로 설정되었는지 확인하고 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-172">If the call connects, but you can't hear the instructions or your message, make sure that your speakers and microphone are set up correctly, and then try again.</span></span>
   * <span data-ttu-id="5bb29-173">통화가 연결되지 않거나 연결되지만 메시지가 들리지 않으면 필요한 네트워크 포트에 액세스를 허용하도록 방화벽을 업데이트해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-173">If the call doesn't connect or it connects but you can't hear your message, you might need to update your firewall to allow access to the required network ports.</span></span> <span data-ttu-id="5bb29-174">방화벽 설명서를 확인하거나 IT 전문가에게 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="5bb29-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="5bb29-175">사용자가 IT 전문가이고 Business Voice를 지원하기 위해 더욱 크거나 복잡한 네트워크를 준비하는 방법에 대한 자세한 정보를 필요로 하는 경우 [사용자 환경 평가](../3-envision-evaluate-my-environment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bb29-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, see [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="5bb29-176">이 문서는 대역폭, 프록시 및 방화벽 요구 사항에 정보를 제공하고 또한 [네트워크 평가 도구](../3-envision-evaluate-my-environment.md#test-the-network)를 사용하여 네트워크를 테스트하는 방법도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb29-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

