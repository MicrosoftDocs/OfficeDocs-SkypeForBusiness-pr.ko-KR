---
title: 인터넷 연결 확인
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653554"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="f1a06-102">인터넷 연결 확인</span><span class="sxs-lookup"><span data-stu-id="f1a06-102">Check your Internet connection</span></span>

<span data-ttu-id="f1a06-103">Business Voice는 Microsoft 365에서 클라우드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="f1a06-104">Microsoft Teams와 Business Voice를 사용하는 모든 컴퓨터와 장치는 인터넷 연결을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="f1a06-105">Business Voice를 사용하여 최고의 환경을 활용 하려면 어느 특정 시간에 걸려올 수 있는 예상 전화의 수를 지원할 수 있는 광대역 인터넷 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="f1a06-106">또한 네트워크에 있는 컴퓨터에서 Microsoft 365 서버에 연결할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="f1a06-107">이 단계를 따르려면 다음의 구독 중 하나를 포함하는 테넌트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="f1a06-108">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="f1a06-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="f1a06-109">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="f1a06-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="f1a06-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="f1a06-110">Office 365 E1</span></span>
* <span data-ttu-id="f1a06-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="f1a06-111">Office 365 E3</span></span>
* <span data-ttu-id="f1a06-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="f1a06-112">Office 365 F1</span></span>
* <span data-ttu-id="f1a06-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="f1a06-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="f1a06-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="f1a06-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="f1a06-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="f1a06-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="f1a06-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f1a06-116">Microsoft 365 Business</span></span>

<span data-ttu-id="f1a06-117">이들 단계를 따르기 위해 Business Voice 라이선스가 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="f1a06-118">인터넷 연결 속도를 확인합니다</span><span class="sxs-lookup"><span data-stu-id="f1a06-118">Check your Internet connection speed</span></span>

<span data-ttu-id="f1a06-119">이 문서는 사용자의 인터넷 연결이 전화를 걸고 화상 회의를 호스팅하는 등의 작업을 수행해야 하는 사용자의 수를 수용하기에 충분히 빠른지를 확인하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="f1a06-120">사용자는 조직에 대한 정보를 입력하고 Teams와 Business Voice가 사용할 인터넷 연결의 용량이 포함된 보고서를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="f1a06-121">인터넷 연결 및 사용자에 대한 정보 받기</span><span class="sxs-lookup"><span data-stu-id="f1a06-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="f1a06-122">시작하기 전에 다음의 정보를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="f1a06-123">인터넷 연결 속도.</span><span class="sxs-lookup"><span data-stu-id="f1a06-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="f1a06-124">사무실에서 주로 Business Voice를 사용하는 사용자의 수.</span><span class="sxs-lookup"><span data-stu-id="f1a06-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="f1a06-125">홈 사무실과 같이 주로 원격 위치에서 Business Voice를 사용하는 사용자의 수.</span><span class="sxs-lookup"><span data-stu-id="f1a06-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="f1a06-126">네트워크 플래너에 사용자 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-126">Enter your information into the network planner</span></span>

<span data-ttu-id="f1a06-127">수행해야 하는 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="f1a06-128">브라우저를 열고 https://admin.teams.microsoft.com로 이동하여 전역 관리자 권한이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="f1a06-129">Office 365에 등록하는 데 사용한 계정에는 이러한 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="f1a06-130">**계획**을 열고 **네트워크 플래너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="f1a06-131">**네트워크 플랜**에서 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="f1a06-132">플랜에 이름을 지정하고 **적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="f1a06-133">네트워크 플랜은 다음과 같이 보여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-133">Your network plan should look like this:</span></span>

    ![네트워크 플래너의 메인 화면](../media/network-planner-main.png)
1. <span data-ttu-id="f1a06-135">네트워크 플랜의 이름을(위의 그림에서 **주 사무실**) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="f1a06-136">다음 페이지에서 **네트워크 사이트**탭의 **네트워크 사이트 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="f1a06-137">아래 스크린샷에 표시된 항목만 입력하고 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-137">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="f1a06-138">화면의 나머지 항목은 빈 칸으로 두고, **ExpressRoute**나 **WAN에 연결됨** 옵션은 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-138">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![네트워크 플래너 사이트 정보](../media/network-planner-site-info.png)
1. <span data-ttu-id="f1a06-140">**보고서** 탭에서 **보고서 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-140">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="f1a06-141">다음 정보를 입력하고 **보고서 생성**을 선택하면 Teams에서 필요한 대역폭을 보여주는 보고서가 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-141">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="f1a06-142">다음 항목에서 보고서를 해석하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-142">We'll show you how to read the report in the next section.</span></span>

    ![네트워크 플래너 보고서 정보](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="f1a06-144">최소 인터넷 연결 속도를 확인합니다</span><span class="sxs-lookup"><span data-stu-id="f1a06-144">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="f1a06-145">**보고서 작성**을 선택 시 Office 365에서 다음과 같이 표시되는 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-145">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![네트워크 플래너 보고서의 세부 정보](../media/network-planner-report.png)

<span data-ttu-id="f1a06-147">강조 표시된 숫자는 Teams와 Business Voice가 사용할 인터넷 연결의 용량을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-147">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="f1a06-148">이 숫자가 총 인터넷 연결 속도의 30%를 넘지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-148">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="f1a06-149">예를 들어 인터넷 연결 속도가 60Mbps인 경우 Teams와 Business Voice는 18Mbps 이상을 차지하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-149">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="f1a06-150">다음의 계산을 수행하여 최소 인터넷 연결 속도를 확인할 수 있습니다. `<highlighted number> / .3`.</span><span class="sxs-lookup"><span data-stu-id="f1a06-150">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="f1a06-151">위 그림에 강조 표시된 숫자를 사용하면 계산은 `4.6875 / .3 = 15.6`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-151">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="f1a06-152">즉, 최소 인터넷 연결 속도가 적어도 15.6Mbps가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-152">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="f1a06-153">Teams와 Business Voice에서 전체 인터넷 연결 속도의 30% 이상을 사용하는 경우 강조 표시된 숫자가 빨간색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-153">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="f1a06-154">이러한 경우 인터넷 연결을 업그레이드해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-154">If this happens, you might need to upgrade your Internet connection.</span></span>

![연결 속도 경고](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="f1a06-156">네트워크의 컴퓨터와 장치가 Microsoft 365에 연결될 수 있는지 확인합니다</span><span class="sxs-lookup"><span data-stu-id="f1a06-156">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="f1a06-157">제대로 작동하려면 Business Voice를 사용하려는 컴퓨터와 장치가 특정 네트워크 포트를 사용하 여 Microsoft 365 서버와 통신을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-157">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="f1a06-158">네트워크 포트는 기본적으로 네트워크 또는 인터넷을 통해 컴퓨터와 장치가 서로 통신할 수 있는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-158">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="f1a06-159">사용자의 방화벽은 네트워크의 컴퓨터 및 장치가 다음의 아웃바운드 네트워크 포트를 사용하 여 Microsoft 365에 연결될 수 있도록 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-159">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="f1a06-160">**TCP 포트** 80 및 443</span><span class="sxs-lookup"><span data-stu-id="f1a06-160">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="f1a06-161">**UDP 포트** 3478, 3479, 3480 및 3481</span><span class="sxs-lookup"><span data-stu-id="f1a06-161">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="f1a06-162">방화벽이 이들 네트워크 포트에서의 통신을 허용하는지를 확인하는 가장 쉬운 방법은 Teams를 사용하여 테스트를 해보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-162">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="f1a06-163">테스트를 수행하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-163">To make a test call, do the following:</span></span>

1. <span data-ttu-id="f1a06-164">네트워크의 컴퓨터에서 https://aka.ms/getteams로 이동하여 Teams를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-164">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="f1a06-165">스피커와 마이크가이 컴퓨터에 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-165">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="f1a06-166">Teams를 열고 Microsoft 365 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-166">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="f1a06-167">Teams에서 프로필 사진을 선택한 다음 **설정** > **장치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-167">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="f1a06-168">**오디오 장치**에서 **테스트 전화걸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-168">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="f1a06-169">프롬프트에 따라 메시지를 나가고 다시 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-169">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="f1a06-170">통화가 연결되고 메시지가 재생되는 것을 들을 수 있다면 방화벽이 제대로 설정된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-170">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="f1a06-171">통화가 연결되지만 프롬프트나 메시지가 재생되는 것을 듣지 못하는 경우 스피커와 마이크가 컴퓨터에서 제대로 설정되고 인식이 되는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-171">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="f1a06-172">다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="f1a06-172">Try again.</span></span>
* <span data-ttu-id="f1a06-173">통화가 연결되지 않거나 연결되어도 메시지가 ㅅ재생되는 것을 듣지 못하는 경우 위에 열거된 네트워크 포트를 허용하도록 방화벽을 업데이트해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="f1a06-174">네트워크 포트가 인터넷에 연결되도록 하는 방법에 대한 방화벽 문서를 확인하거나 IT 전문가에 게 도움을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-174">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="f1a06-175">사용자가 IT 전문가이고 Business Voice를 지원하기 위해 더욱 크거나 복잡한 네트워크를 준비하는 방법에 대한 자세한 정보를 필요로 하는 경우 [사용자 환경 평가](../3-envision-evaluate-my-environment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1a06-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="f1a06-176">[사용자 환경 평가](../3-envision-evaluate-my-environment.md) 문서는 대역폭, 프록시 및 방화벽 요구 사항에 대한 추가 정보를 제공 하고 또한 [네트워크 평가 도구](../3-envision-evaluate-my-environment.md#test-the-network)를 사용하여 네트워크를 테스트하는 방법도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a06-176">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
