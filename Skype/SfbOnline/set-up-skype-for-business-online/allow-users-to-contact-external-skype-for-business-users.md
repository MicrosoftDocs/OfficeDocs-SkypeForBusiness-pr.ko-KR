---
title: 사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: '사용자가 다른 조직의 사용자에 게 대화를 보내거나 외부 연락처를 사용할 수 있도록 비즈니스용 Skype를 구성 하는 방법을 알아봅니다. '
ms.openlocfilehash: 570861f532371dc8eca253956ffdd200e60f5990
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642657"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="2f715-103">사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="2f715-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="2f715-104">비즈니스용 Skype 페더레이션은 21Vianet 및 Office 365 독일 조직이 운영 하는 Office 365에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="2f715-105">다음과 같은 경우이 문서에 나와 있는 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="2f715-106">비즈니스의 다른 도메인에 사용자가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="2f715-106">You have users on different domains in your business.</span></span> <span data-ttu-id="2f715-107">예를 Rob@ContosoEast.com 및 Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="2f715-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="2f715-108">조직의 사용자가 조직 외부의 특정 비즈니스 사용자에 게 연락할 수 있도록 비즈니스용 Skype를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="2f715-109">비즈니스용 Skype를 사용 하는 세계의 다른 사용자가 전자 메일 주소를 사용 하 여 사용자를 찾고 연락할 수 있도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="2f715-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="2f715-110">사용자가 기본 비즈니스용 Skype 설정을 사용 하는 경우 자동으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="2f715-111">그렇지 않은 경우에는 구성에서 사용자의 도메인을 차단 하 고 있지 않은지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="2f715-112">사용자에 대해 b2b 통신 사용</span><span class="sxs-lookup"><span data-stu-id="2f715-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="2f715-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2f715-113"></span></span>

<span data-ttu-id="2f715-114">이 작업을 수행 하려면 두 조직의 Office 365에 [대 한 관리자 권한이](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="2f715-115">![](../images/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여** Microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="2f715-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="2f715-116">Office 365 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="2f715-117">관리 센터에서 **관리 센터** > **팀**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-117">In the admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![팀 관리자를 선택 합니다.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="2f715-119">**팀 센터**에서 **Skype** > **레거시 포털** 
 ![을 선택 하세요 SfB 레거시 포탈을 선택 합니다.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="2f715-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="2f715-120">**비즈니스용 Skype 관리 센터** 에서 **조직** > **외부 통신**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="2f715-121">특정 비즈니스 또는 다른 도메인에 있는 사용자와의 통신을 설정 하려면 드롭다운 상자에서 **허용 된 도메인에만**설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="2f715-122">또는 비즈니스용 Skype 정책을 연 전세계의 모든 사용자와 통신을 사용 하도록 설정 하려면 **차단 된 도메인을 제외한**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-122">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="2f715-123">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-123">This is the default setting.</span></span>
    
6. <span data-ttu-id="2f715-124">**차단 되거나 허용 된 도메인**에서 허용 **+** 하려는 도메인의 이름을 선택 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="2f715-125">다른 조직의 관리자가 **비즈니스용 Skype 관리 센터**에서 동일한 단계를 수행 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="2f715-126">예를 들어 허용 된 **도메인** 목록에서 관리자는 자신의 비즈니스에 대 한 도메인을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="2f715-127">Windows 방화벽을 사용 중인 경우 비즈니스용 Skype는 필요한 포트를 자동으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="2f715-128">조직에서 다른 방화벽 솔루션을 사용 하 여 네트워크의 컴퓨터를 인터넷에 연결 하지 못하도록 제한 하는 경우 클라이언트 컴퓨터에서 다음 [Office 365 url 및 IP 주소 범위](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="2f715-129">방화벽 또는 \*프록시 인프라 구성 \*\* \*\*\* 의 아웃 바운드 허용 목록에 fqdn을 추가 해야 할 수 있습니다. api.skype.com, **users.storage.live.com**및 **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="2f715-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="2f715-130">방화벽에서 이러한 포트를 여는 방법에 대 한 자세한 내용은 함께 제공 된 설명서를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f715-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="2f715-131">열어야 할 모든 포트 목록은 [Office 365 url 및 IP 주소 범위](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f715-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="2f715-132">조직의 관리자도 다음 단계를 따랐는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="2f715-133">**테스트 하는 데 최대 24 시간까지 기다립니다**.</span><span class="sxs-lookup"><span data-stu-id="2f715-133">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="2f715-134">외부 통신 설정을 변경할 때마다 변경 내용이 모든 데이터 센터에 걸친 24 시간이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-134">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="2f715-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 를 이용 하시면 skype를 사용 하는 모든 사람과 메신저 대화를 사용자에 게 제공 하 여 무료 소비자 앱!</span><span class="sxs-lookup"><span data-stu-id="2f715-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="2f715-136">자세히 알아보려면 [비즈니스용 skype 사용자가 skype 연락처를 추가 하도록 허용](let-skype-for-business-users-add-skype-contacts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f715-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="2f715-137">테스트 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2f715-137">Test and troubleshoot</span></span>
<span data-ttu-id="2f715-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2f715-138"></span></span>

 <span data-ttu-id="2f715-139">**B2b 통신을 설정할 때 발생 하는 가장 일반적인 문제로 인해 [Office 365 url 및 IP 주소 범위가](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) 적절 하 게 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="2f715-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="2f715-140">설정을 테스트 하려면 회사 방화벽 뒤에 있지 않은 비즈니스용 Skype에 대 한 연락처가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="2f715-141">외부 통신 설정을 변경한 후에는 **24 시간까지 테스트를 기다립니다**.</span><span class="sxs-lookup"><span data-stu-id="2f715-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="2f715-142">비즈니스용 Skype에서 비즈니스용 Skype에서 대화 상대를 검색 하 고 채팅 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="2f715-143">회사 정책 때문에 보낼 수 없다는 메시지가 표시 되는 경우 [Office 365 url 및 IP 주소 범위를 다시](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="2f715-144">Skype for Business 연락처에 게 채팅 요청을 보내십시오.</span><span class="sxs-lookup"><span data-stu-id="2f715-144">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="2f715-145">요청을 받지 못한 경우 해당 방화벽 설정이 올바른 것으로 확인 되었다고 가정 하 여 문제가 방화벽 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-145">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="2f715-146">문제가 방화벽에 해당 하는지 여부를 테스트 하는 또 다른 방법은 커피숍과 같이 방화벽 뒤에 있지 않은 wifi 위치로 이동 하 여 비즈니스용 Skype를 사용 하 여 대화 상대에 게 채팅 요청을 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-146">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="2f715-147">메시지가 표시 되지만 작업 중에는 그렇지 않은 경우에는 방화벽이 문제가 되는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="2f715-148">다른 비즈니스에 연결할 때 발견 되는 다른 사용자를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="2f715-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="2f715-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2f715-149"></span></span>

<span data-ttu-id="2f715-150">다른 비즈니스용 Skype 사용자와 외부 통신을 사용 하도록 설정한 후 사용자는 로그인 이름 (예: Rob@contoso.com)을 검색 하 여 비즈니스용 Skype 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="2f715-151">그런 다음 연락처 목록에 사용자를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-151">Then they will need to add the person to their list of contacts.</span></span>
  
![페더레이션된 비즈니스에서 사용자를 찾으려면 해당 전자 메일 주소를 검색 해야 합니다 (일반적으로 로그인 이름 이기도 함).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="2f715-153">페더레이션된 비즈니스와의 통신 설정에 대 한 팁</span><span class="sxs-lookup"><span data-stu-id="2f715-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="2f715-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2f715-154"></span></span>

- <span data-ttu-id="2f715-155">비즈니스용 Skype 2015 및 비즈니스용 Skype Online 간의 페더레이션을 구성 하려면이 문서: [비즈니스용 Skype online을 사용 하 여 페더레이션 구성](https://technet.microsoft.com/en-us/library/jj205126.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f715-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="2f715-156">Lync와 비즈니스용 Skype Online 간의 페더레이션을 구성 하려면이 문서에서는 [Lync Online 고객에 대 한 페더레이션 지원 구성을](https://technet.microsoft.com/en-us/library/hh202193.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f715-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="2f715-157">Office 365에 있는 두 개의 비즈니스용 Skype 사용자 들이 별도의 도메인에 서로 통신 하는 경우, 두 조직 모두에서 사용 하도록 설정 된 비즈니스용 Skype 기능 (예: 비디오 대화 또는 데스크톱 공유)만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="2f715-158">조직의 비즈니스용 Skype 사용자가 현재 위치 또는 소송 유지에 포함 되는 경우 해당 사용자와 다른 비즈니스용 Skype 또는 Skype 사용자 간 메신저 대화는 사서함에 **복구 가능한 항목** 으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="2f715-159">이러한 대화는 사서함의 **대화 내용** 폴더에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="2f715-160">특정 개인에 대 한 외부 통신 끄기</span><span class="sxs-lookup"><span data-stu-id="2f715-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="2f715-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2f715-161"></span></span>

<span data-ttu-id="2f715-162">전체 비즈니스에 대해 외부 통신을 사용 하도록 설정한 후에는 특정 개인에 대해서만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="2f715-163">Office 365 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="2f715-164">관리 센터에서 **사용자** > **활성 사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-164">In the admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="2f715-165">사용자 목록에서 사용자를 선택 하 고 **기타 설정**아래에 있는 **비즈니스용 Skype 속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![비즈니스용 Skype 선택](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="2f715-167">**비즈니스용 Skype 관리 센터**에서 **외부 통신**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="2f715-168">**옵션** 페이지에서 모든 선택 항목이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="2f715-169">사용 하지 않을 통신을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="2f715-170">다음 이미지는 Jakob이 다른 신뢰할 수 있는 회사의 사용자와 통신할 수 있지만 다른 Skype 사용자와는 통신 하지 못하는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![외부 연락처 선택](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="2f715-172">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2f715-173">변경 내용이 적용 되려면 최대 24 시간 동안 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f715-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="2f715-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2f715-174">Related topics</span></span>
<span data-ttu-id="2f715-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2f715-175"></span></span>

[<span data-ttu-id="2f715-176">비즈니스용 Skype Online 설정</span><span class="sxs-lookup"><span data-stu-id="2f715-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="2f715-177">비즈니스용 Skype 사용자가 Skype 연락처를 추가 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="2f715-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
