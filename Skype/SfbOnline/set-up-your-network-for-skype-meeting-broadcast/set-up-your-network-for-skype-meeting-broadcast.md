---
title: Skype 모임 브로드캐스트를 위한 네트워크 설정
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
f1keywords: None
ms.custom:
- SMB
description: 최대 1만 참석자를 대상으로 하는 대규모 온라인 사용자에 게 모임 또는 이벤트를 예약, 생성, 브로드캐스트 하는 데 사용할 수 있는 비즈니스용 Skype Online의 Skype 모임 브로드캐스트 기능에 대해 알아봅니다.
ms.openlocfilehash: 443810772eeb8bf11721825b06b6a87ccb2c97c8
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642750"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="d5f9d-103">Skype 모임 브로드캐스트를 위한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="d5f9d-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="d5f9d-104">[Skype 모임 브로드캐스트](enable-skype-meeting-broadcast.md) Skype 모임 브로드캐스트를 사용 하도록 설정한 후에는 네트워크를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="d5f9d-105">비즈니스 외부 사용자에 대 한 웹 세미나 진행 및 기타 브로드캐스트를 유지 하려는 경우이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="d5f9d-106">방화벽 구성에 대 한 경험이 없는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="d5f9d-107">이 단계를 건너뛰고 대신 페더레이션에 다른 비즈니스를 추가 하 여 브로드캐스트에 초대할 수 있도록 하려면 [사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="d5f9d-108">1 단계: 허용 된 도메인 설정</span><span class="sxs-lookup"><span data-stu-id="d5f9d-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="d5f9d-109">허용 된 도메인을 설정 하려면 다음 방법 **중 하나** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="d5f9d-110">**방법 1: 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="d5f9d-110">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="d5f9d-111">관리 센터로 이동한 다음 왼쪽 탐색 창에서 **설정** > **서비스 &amp; 추가 기능**을 클릭 하 고 비즈니스용 **Skype**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-111">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="d5f9d-112">**외부 공유** 페이지의 **도메인 예외**에서 다음을 **제외한 모든 도메인이 차단 됨**을 선택 하 고 쉼표 (,)로 구분 하 여 다음 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="d5f9d-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d5f9d-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="d5f9d-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d5f9d-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="d5f9d-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d5f9d-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="d5f9d-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="d5f9d-116">resources.lync.com</span></span>

3. <span data-ttu-id="d5f9d-117">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="d5f9d-118">**방법 2: Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="d5f9d-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="d5f9d-119">**시작 메뉴**에서 **Windows PowerShell** 을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="d5f9d-120">**Windows PowerShell** 창에서 각 줄을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="d5f9d-121">2 단계: Skype 모임 브로드캐스트 도메인, Url 및 IP 주소 추가</span><span class="sxs-lookup"><span data-stu-id="d5f9d-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="d5f9d-122">설치 프로세스의 두 번째 단계는 먼저 필요한 도메인을 추가 하 고 Skype 모임 브로드캐스트에 필요한 IP 주소와 Url을 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="d5f9d-123">필요한 **비즈니스용 Skype Online 끝점 url 및 IP 주소를 여기에서 필요한 항목을 확인 하 여 추가** [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)합니다.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="d5f9d-124">하이브리드 배포 및 조직에서 Skype 모임 브로드캐스트 설정</span><span class="sxs-lookup"><span data-stu-id="d5f9d-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="d5f9d-125">비즈니스용 Skype Online 조직이 있고 Lync Server 2010, Microsoft Lync Server 2013, 비즈니스용 Skype Server 2015 및 사용자가 온라인 및 온-프레미스를 모두 보유 하 고 있는 경우에는 다른 설치 단계가 필요 합니다. 온-프레미스 조직이 비즈니스용 Skype Online과 통신 하 고 모든 사용자가 Skype 모임 브로드캐스트에 참가할 수 있도록 하려면 위의 항목에 추가 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="d5f9d-126">이러한 요구 사항을 보려면 [Skype 모임 브로드캐스트에 대 한 온-프레미스 배포 구성을](https://go.microsoft.com/fwlink/?LinkId=617070)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5f9d-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5f9d-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d5f9d-127">Related topics</span></span>

[<span data-ttu-id="d5f9d-128">Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="d5f9d-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="d5f9d-129">Office 365 Url 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="d5f9d-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="d5f9d-130">비즈니스용 Skype Online 설정</span><span class="sxs-lookup"><span data-stu-id="d5f9d-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



