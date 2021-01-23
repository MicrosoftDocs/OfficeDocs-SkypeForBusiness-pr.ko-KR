---
title: Microsoft Teams의 Walkie Talkie 응용 프로그램
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin 관점에서 Microsoft Teams에서 Walkie Talkie 앱을 구성하는 방법
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63cd853b8a068e7acfc5752e3cd94b5d0102bc2f
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944593"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="52b7a-103">Microsoft Teams의 Walkie Talkie 앱</span><span class="sxs-lookup"><span data-stu-id="52b7a-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="52b7a-104">Teams의 Walkie Talkie 앱은 팀을 위한 PTT(즉시 푸시투 토크) 통신을 제공하며 이제 Android에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="52b7a-105">Walkie Talkie를 사용하면 사용자가 구성원인 동일한 기조 채널을 사용하여 팀과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="52b7a-106">채널에서 Walkie Talkie에 연결하는 사용자만 참가자가 되고 한 번씩 푸시-토크를 사용하여 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="52b7a-107">Teams에서 Walkie Talkie를 사용하여 일선 직원들은 부피가 큰 라디오를 수행하지 않고도 친숙한 PTT 환경과 안전하게 통신할 수 있으며, Walkie Talkie는 WiFi 또는 셀룰러 인터넷 연결을 통해 어디서나 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="52b7a-108">시작</span><span class="sxs-lookup"><span data-stu-id="52b7a-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="52b7a-109">Walkie Talkie 배포</span><span class="sxs-lookup"><span data-stu-id="52b7a-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="52b7a-110">현재 Walkie Talkie는 사전 설치되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="52b7a-111">조직의 사용자가 이 기능을 사용하도록 설정하려면 Teams 관리 센터에서 [](teams-app-setup-policies.md)사용자에게 할당된 앱 설정 정책에 Walkie Talkie를   [추가해야 합니다.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="52b7a-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="52b7a-112">사용하도록 설정하면 Walkie Talkie는 48시간 이내에 Android 앱에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="52b7a-113">앱 목록에 Walkie Talkie 추가</span><span class="sxs-lookup"><span data-stu-id="52b7a-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="52b7a-114">Microsoft Teams 관리 센터의 **Teams** 앱 설정 정책에서 사용자 고정 허용을 으로  >  설정해야 **합니다.** </span><span class="sxs-lookup"><span data-stu-id="52b7a-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="52b7a-115">그런 다음 고정된 앱 섹션에서 **+앱 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="52b7a-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="고정된 앱 섹션 및 선택될 앱 추가 단추를 보여줍니다.":::

<span data-ttu-id="52b7a-117">오른쪽에 **나타나는** 고정된 앱 추가 패널에서 검색  텍스트 상자를 사용하여 Walkie Talkie를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="52b7a-118">검색 결과로 있는 경우 이름  오른쪽에 있는 추가 단추를 클릭하여 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="검색 창에 Walkie가 입력된 고정된 앱 추가 사이드바와 검색 결과의 Walkie Talkie 앱 옆에 추가 단추가 표시됩니다.":::

<span data-ttu-id="52b7a-120">이제 Walkie Talkie 앱이 고정된 앱 목록에 표시되어 저장 단추를 클릭하면 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Walkie Talkie 앱이 추가된 고정된 앱 목록과 목록 아래에 저장 단추가 표시됩니다.":::

### <a name="network-documentation"></a><span data-ttu-id="52b7a-122">네트워크 설명서</span><span class="sxs-lookup"><span data-stu-id="52b7a-122">Network documentation</span></span>

<span data-ttu-id="52b7a-123">Teams의 Walkie Talkie는 인터넷 연결이 필요하며 최적의 환경을 위해서는 네트워크 조건 미만이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="52b7a-124">메트릭</span><span class="sxs-lookup"><span data-stu-id="52b7a-124">Metric</span></span> | <span data-ttu-id="52b7a-125">필수</span><span class="sxs-lookup"><span data-stu-id="52b7a-125">Required</span></span> |
|---|---|
|<span data-ttu-id="52b7a-126">RTT(대기 시간)</span><span class="sxs-lookup"><span data-stu-id="52b7a-126">Latency (RTT)</span></span> | <span data-ttu-id="52b7a-127">< 300ms</span><span class="sxs-lookup"><span data-stu-id="52b7a-127">< 300ms</span></span> |
|<span data-ttu-id="52b7a-128">지터</span><span class="sxs-lookup"><span data-stu-id="52b7a-128">Jitter</span></span> |<span data-ttu-id="52b7a-129">< 30ms</span><span class="sxs-lookup"><span data-stu-id="52b7a-129">< 30ms</span></span> |
|<span data-ttu-id="52b7a-130">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="52b7a-130">Packet Loss</span></span> |<span data-ttu-id="52b7a-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="52b7a-131">< 1%</span></span> |

<span data-ttu-id="52b7a-132">위에서 설명한 대로 IP 네트워크를 통해 실시간 미디어의 품질은 네트워크 연결의 품질에 크게 영향을 주지만, 특히 다음의 양에 의해 크게 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="52b7a-133">**대기 시간** - 네트워크의 지점 A에서 B 지점까지 IP 패킷을 수신하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="52b7a-134">이 네트워크 전파 지연은 기본적으로 다양한 라우터에서 취한 추가 오버헤드를 포함하여 두 지점 간의 물리적 거리와 광속에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="52b7a-135">대기 시간은 RTT(왕복 시간)로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="52b7a-136">**패킷 손실** - 종종 특정 기간에 손실되는 패킷의 백분율로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="52b7a-137">패킷 손실은 거의 영향을 주지 않고 개별 손실된 작은 패킷부터 전체 오디오를 차단하는 백백 버스트 손실까지 오디오 품질에 직접 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="52b7a-138">**지터** - 연속 패킷 간 지연의 평균 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="52b7a-139">Walkie Talkie의 예상 데이터 사용량은 오디오를 보내거나 받을 때 약 20KB/s입니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="52b7a-140">유휴 시 Walkie Talkie의 예상 데이터 사용량은 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="52b7a-141">Walkie Talkie 장치</span><span class="sxs-lookup"><span data-stu-id="52b7a-141">Walkie Talkie devices</span></span>

<span data-ttu-id="52b7a-142">일선 직원들은 종종 전화가 잠겨 있는 경우에도 Walkie Talkie 통화를 말하고 수신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="52b7a-143">이 환경은 전용 PTT 단추가 있는 특수 디바이스를 통해 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="52b7a-144">헤드셋</span><span class="sxs-lookup"><span data-stu-id="52b7a-144">Headsets</span></span>
  - <span data-ttu-id="52b7a-145">유선[헤드셋(Klein Electronics)](https://www.kleinelectronics.com/poc-accessories/mtwt/)</span><span class="sxs-lookup"><span data-stu-id="52b7a-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="52b7a-146">무선[헤드셋(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)</span><span class="sxs-lookup"><span data-stu-id="52b7a-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="52b7a-147">견고한 휴대폰</span><span class="sxs-lookup"><span data-stu-id="52b7a-147">Rugged phones</span></span>
  - <span data-ttu-id="52b7a-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="52b7a-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="52b7a-149">[추가 정보.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)</span><span class="sxs-lookup"><span data-stu-id="52b7a-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="52b7a-150">[설치 가이드.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)</span><span class="sxs-lookup"><span data-stu-id="52b7a-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="52b7a-151">이러한 장치는 Teams 인증이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-151">These devices are not Teams certified.</span></span> <span data-ttu-id="52b7a-152">Teams Walkie Talkie와 함께 작업하는 것이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="52b7a-153">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="52b7a-153">License requirements</span></span>

<span data-ttu-id="52b7a-154">Walkie Talkie 앱은 [Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)구독의 Teams의 모든 유료 라이선스에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="52b7a-155">Teams를 다운로드하는 방법에 대한 자세한 내용은 Microsoft Teams에 액세스하는 [방법을 확인하세요.](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="52b7a-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="52b7a-156">특정 고급 기능에는 추가 라이선스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="52b7a-157">예를 들어 Samsung Galaxy XCover Pro와 통합하려면 Knox 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="52b7a-158">추가 정보</span><span class="sxs-lookup"><span data-stu-id="52b7a-158">Further information</span></span>

- <span data-ttu-id="52b7a-159">ITAdmins는 앱 정책을 통해 Walkie Talkie를 사용하는 사용자에 대한 제어를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="52b7a-160">Frontline Worker가 모바일 데이터를 사용하여 Teams를 통해 통신하는 경우 Walkie Talkie는 동일한 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-160">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="52b7a-161">Walkie Talkie는 낮은 대역폭 상황에서 또는 스마트폰이 연결되어 작동되는 상황에서 잘 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="52b7a-162">Walkie Talkie는 연결이 없는 경우 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52b7a-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="52b7a-163">최종 사용자 경험에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52b7a-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="52b7a-164">Teams Walkie Talkie 시작</span><span class="sxs-lookup"><span data-stu-id="52b7a-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="52b7a-165">Walkie Talkie를 통해 팀과 의사소통</span><span class="sxs-lookup"><span data-stu-id="52b7a-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
