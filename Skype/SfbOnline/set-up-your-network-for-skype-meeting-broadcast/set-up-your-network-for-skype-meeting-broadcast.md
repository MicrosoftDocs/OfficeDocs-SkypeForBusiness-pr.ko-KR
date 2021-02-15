---
title: Skype 모임 브로드캐스트의 네트워크 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 최대 10,000명까지 대규모 온라인 청중에게 모임이나 이벤트를 예약, 생성 및 브로드캐스트할 수 있는 비즈니스용 Skype Online의 Skype 모임 브로드캐스트 기능에 대해 자세히 배워보아야 합니다.
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865162"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="3bf46-103">Skype 모임 브로드캐스트의 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="3bf46-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="3bf46-104">Skype 모임 [브로드캐스트 Skype](enable-skype-meeting-broadcast.md) 모임 브로드캐스트를 사용하도록 설정한 후 네트워크를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="3bf46-105">비즈니스 외부 사용자에 대한 웨비나 및 기타 브로드캐스트를 보유하려는 경우 이 단계를 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bf46-106">비즈니스용 Skype Online은 2021년 7월 31일 사용이 중지됩니다. 그러면 서비스에 대한 액세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="3bf46-107">Microsoft 365에서 커뮤니케이션 및 팀워크를 위한 핵심 클라이언트인 Microsoft Teams로 업그레이드하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="3bf46-108">방화벽 구성에 경험이 없는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="3bf46-109">이 단계를 건너뛰고 다른 비즈니스를 브로드캐스트에 초대할 수 있도록 페더러에 다른 비즈니스를 추가하는 대신 사용자가 외부 비즈니스용 Skype 사용자에게 연락할 수 있도록 허용의 [단계를 따릅니다.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="3bf46-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="3bf46-110">1단계: 허용되는 도메인 설정</span><span class="sxs-lookup"><span data-stu-id="3bf46-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="3bf46-111">다음 **방법** 중 하나를 사용하여 허용되는 도메인을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="3bf46-112">**방법 1: 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="3bf46-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="3bf46-113">관리 센터로 이동한 다음 왼쪽으로 이동하여 **설정** 서비스 추가 기능을 클릭한 다음 비즈니스용  >  **&amp;** **Skype를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bf46-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="3bf46-114">도메인 **예외의** 외부 공유 페이지에서 모든 도메인이 차단된 것을 선택하고 **다음** 도메인을 콤마(,)로 구분하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="3bf46-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bf46-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="3bf46-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bf46-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="3bf46-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bf46-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="3bf46-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bf46-118">resources.lync.com</span></span>

3. <span data-ttu-id="3bf46-119">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="3bf46-120">**방법 2: 다음 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3bf46-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="3bf46-121">시작 **메뉴에서** 마우스 오른쪽 **단추로** Windows PowerShell 관리자 **권한으로 실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bf46-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="3bf46-122">Windows PowerShell **각** 줄을 입력하고 Enter를 누르십시오.</span><span class="sxs-lookup"><span data-stu-id="3bf46-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="3bf46-123">2단계: Skype 모임 브로드캐스트 도메인, URL 및 IP 주소 추가</span><span class="sxs-lookup"><span data-stu-id="3bf46-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="3bf46-124">설치 프로세스의 두 번째 단계는 먼저 필요한 도메인을 추가한 다음 Skype 모임 브로드캐스트가 작동하기 위해 필요한 IP 주소와 URL을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="3bf46-125">**여기에 필요한 비즈니스용 Skype Online** 엔드포인트 URL 및 IP 주소를 [추가합니다.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)</span><span class="sxs-lookup"><span data-stu-id="3bf46-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="3bf46-126">하이브리드 배포 및 조직에서 Skype 모임 브로드캐스트 설정</span><span class="sxs-lookup"><span data-stu-id="3bf46-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="3bf46-127">비즈니스용 Skype Online 조직과 Lync Server 2010, Microsoft Lync Server 2013 및 비즈니스용 Skype Server 2015의 온-프레미스 배포가 있으며 사용자가 온라인 및 온-프레미스 모두에 있는 경우, 온-프레미스 조직이 비즈니스용 Skype Online과 통신하고 모든 사용자가 Skype 모임 브로드캐스트에 참가할 수 있도록 하기 위해 위의 설정 단계 외에도 해야 하는 다른 설정 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf46-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="3bf46-128">이러한 요구 사항에 대한 자세한 내용은 Skype 모임 브로드캐스트에 대한 프레미스 배포 [구성을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=617070)</span><span class="sxs-lookup"><span data-stu-id="3bf46-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3bf46-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3bf46-129">Related topics</span></span>

[<span data-ttu-id="3bf46-130">Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="3bf46-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="3bf46-131">Office 365 URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="3bf46-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="3bf46-132">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="3bf46-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



