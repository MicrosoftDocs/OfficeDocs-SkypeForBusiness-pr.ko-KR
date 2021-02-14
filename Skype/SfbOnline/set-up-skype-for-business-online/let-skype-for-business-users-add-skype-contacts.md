---
title: 비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
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
- Setup
- LIL_Placement
description: '비즈니스용 Skype를 사용하는 사용자가 조직 외부의 비즈니스용 Skype 사용자에게 연락하여 연락처 목록에 추가하는 방법을 참조하세요. '
ms.openlocfilehash: 71282fe105c85cadca9aab341fc1b5e6ffbe47d2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164477"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="29e16-103">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="29e16-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="29e16-104">비즈니스용 Skype를 사용하여 사용자는 무료 앱인 Skype를 사용하는 모든 사용자와 함께 검색하고 IM을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="29e16-105">이 문서에서는 Skype 연락처를 추가할 수 있도록 해야 하는 작업을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="29e16-106">이 작업을 [위해](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) Microsoft 365 또는 Office 365에 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="29e16-107">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="29e16-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="29e16-108">Microsoft 365 또는 Office 365 관리자 계정으로 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="29e16-109">관리 센터에서 관리 센터  >  **비즈니스용 Skype로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="29e16-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![비즈니스용 Skype 관리 센터를 선택하세요.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="29e16-111">**비즈니스용 Skype 관리 센터** 에서 **조직** > **외부 통신** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="29e16-112">기본적으로 사용자는 비즈니스용 Skype를 사용하는 전 세계 모든 사용자와 통신할 수 있습니다(방화벽이 이를 허용하도록 구성되어 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="29e16-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![사람들이 비즈니스용 Skype를 사용하여 Skype와 통신할 수 있도록 선택하세요.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="29e16-114">사용자가 Skype 사용자와 채팅하도록 하려는데 비즈니스용 Skype를 사용하는 다른 사용자와 채팅하지 못하게 하려는 경우 허용된 도메인에 한해 **On을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="29e16-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="29e16-115">Skype 사용자와 연락할 수 있도록 설정하면 skype.com 도메인이 자동으로 허용되는 도메인으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="29e16-116">특정 도메인을 제외한 비즈니스용 Skype를 사용하여 전 세계 모든 비즈니스의 연락처를 허용하려면 차단된 도메인을 제외하고 On을 선택하고 해당 도메인을 추가하도록 **+** 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="29e16-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="29e16-117">해당 특정 도메인에 있는 사람을 제외한 모든 사람이 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="29e16-118">(예를 들어 소송 중일 때 다른 비즈니스와의 연락이 없는지 확인해야 하는 경우 이 옵션을 선택할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="29e16-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="29e16-119">사용자가 비즈니스용 Skype를 사용하여 조직 외부의 **Skype 사용자와 통신할 수 있도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="29e16-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="29e16-120">Windows 방화벽을 사용하는 경우 비즈니스용 Skype에서 필요한 포트가 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="29e16-121">조직에서 다른 솔루션을 사용하여 네트워크의 컴퓨터를 인터넷에 연결하지 못하도록 제한하는 경우 클라이언트 컴퓨터가 Skype 연결 및 Skype 디렉터리 검색을 위해 모든 IP 주소 및 [URL에](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="29e16-122">방화벽 또는 프록시 인프라 구성의 아웃바운드 허용 목록에 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="29e16-123">**테스트할 때까지 최대 24시간 동안 기다릴 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="29e16-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="29e16-124">외부 통신 설정을 변경할 때 변경 내용이 모든 데이터 센터에 채워지는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="29e16-125">비즈니스용 Skype 연락처 목록에 Skype 연락처를 찾아 추가하는 방법을 사용자에게 보여 주어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="29e16-126">비즈니스용 [Skype에서 사용자 검색을 하세요.](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)</span><span class="sxs-lookup"><span data-stu-id="29e16-126">Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="29e16-127">테스트 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="29e16-127">Test and troubleshoot</span></span>

<span data-ttu-id="29e16-128">설정을 테스트하려면 회사 방화벽 뒤에 있지 않은 Skype의 연락처가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="29e16-129">Gmail 계정, Outlook.com 또는 기타 유형의 전자 메일 계정을 사용하여 Skype에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="29e16-130">외부 통신 설정을 변경한 후 최대 **24시간 동안 기다렸다가 테스트합니다.**</span><span class="sxs-lookup"><span data-stu-id="29e16-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="29e16-131">비즈니스용 Skype에서 로그인한 다음 다시 로그인하여 Skype 디렉터리를 검색하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Skype 디렉터리가 강조 표시될 때 Skype 계정이 있는 사용자들을 검색할 수 있습니다.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="29e16-133">비즈니스용 Skype에서 Skype에서 연락처를 검색하고 채팅 요청을 보내면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="29e16-134">회사 정책으로 인해 보낼 수 없는 메시지가 표시될 경우 방화벽 설정을 다시 [확인해야 합니다.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="29e16-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="29e16-135">방화벽에 문제가 있는지 테스트하는 또 다른 방법은 커피숍과 같은 방화벽 뒤에 있지 않은 Wi-Fi 위치로 이동하고 비즈니스용 Skype를 사용하여 Skype 연락처에 채팅 요청을 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="29e16-136">**Skype 연락처에게** 요청을 보냈지만 요청을 받지 못했다면 채팅 요청을 보내달고 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="29e16-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="29e16-137">문제가 Skype와 비즈니스용 Skype 간에 연결을 설정하는 경우 자주 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="29e16-138">이제 메시지가 커피숍에서 진행되지만 직장에 있는 경우가 아니라면 방화벽에 문제가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="29e16-139">할 수 있는 일과 할 수 없는 일</span><span class="sxs-lookup"><span data-stu-id="29e16-139">What you can and can't do</span></span>

- <span data-ttu-id="29e16-140">**Mac의 비즈니스용 Skype에는** Skype 연락처를 검색하고 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="29e16-141">디렉터리 검색을 사용하도록 설정하면 Skype 및 비즈니스용 Skype 사용자를 검색하고 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="29e16-142">어떤 이유로 디렉터리를 검색하여 찾을 수 없는 경우 연락처 요청을 보낸 다음 Skype에 로그인하여 수락하게 하여 해당 사용자와 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="29e16-143">Google 또는 Facebook과 같은 다른 IM 공급자와의 IM 연결을 허용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="29e16-144">비즈니스용 Skype를 사용하여 휴대폰 문자 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="29e16-145">Skype 연락처와 비즈니스용 Skype 연락처 간에는 음성 또는 영상 통화를 녹음/녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="29e16-146">Skype 연락처를 추가할 때 사용할 수 있는 기능은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="29e16-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="29e16-147">Microsoft 계정(이전의 Windows Live ID)으로 로그인한 Skype 연락처는 비즈니스용 Skype 사용자와 대화할 때 일부 기능을 얻을 수 있지만, 일부 기능은 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29e16-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="29e16-148">**Skype 연락처에서 사용 가능**</span><span class="sxs-lookup"><span data-stu-id="29e16-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="29e16-149">**Skype 연락처에서 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="29e16-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="29e16-150">비디오 대화</span><span class="sxs-lookup"><span data-stu-id="29e16-150">Video conversations</span></span> <br/>  <span data-ttu-id="29e16-151">개인 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="29e16-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="29e16-152">현재 상태</span><span class="sxs-lookup"><span data-stu-id="29e16-152">Presence</span></span> <br/> | <span data-ttu-id="29e16-153">다자회 IM 대화</span><span class="sxs-lookup"><span data-stu-id="29e16-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="29e16-154">3명 이상과의 오디오 및 비디오 대화</span><span class="sxs-lookup"><span data-stu-id="29e16-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="29e16-155">데스크톱 및 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="29e16-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="29e16-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="29e16-156">Related topics</span></span>

[<span data-ttu-id="29e16-157">사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용</span><span class="sxs-lookup"><span data-stu-id="29e16-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="29e16-158">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="29e16-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
