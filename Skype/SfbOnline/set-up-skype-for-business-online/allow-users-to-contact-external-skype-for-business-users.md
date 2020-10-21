---
title: 사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용
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
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: '다른 조직의 사용자에 게 대화를 보내거나 외부 대화 상대와 대화를 나눌 수 있도록 비즈니스용 Skype를 구성 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625054"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="6d5b0-103">사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용</span><span class="sxs-lookup"><span data-stu-id="6d5b0-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="6d5b0-104">다음과 같은 경우이 문서에 나와 있는 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="6d5b0-105">비즈니스의 다른 도메인에 사용자가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="6d5b0-105">You have users on different domains in your business.</span></span> <span data-ttu-id="6d5b0-106">예를 Rob@ContosoEast.com 및 Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="6d5b0-107">조직의 사용자가 조직 외부의 특정 비즈니스 사용자에 게 연락할 수 있도록 비즈니스용 Skype를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="6d5b0-108">비즈니스용 Skype를 사용 하는 세계의 다른 사용자가 전자 메일 주소를 사용 하 여 사용자를 찾고 연락할 수 있도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="6d5b0-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="6d5b0-109">사용자가 기본 비즈니스용 Skype 설정을 사용 하는 경우 자동으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="6d5b0-110">그렇지 않은 경우에는 구성에서 사용자의 도메인을 차단 하 고 있지 않은지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="6d5b0-111">사용자에 대해 b2b 통신 사용</span><span class="sxs-lookup"><span data-stu-id="6d5b0-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="6d5b0-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5b0-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="6d5b0-113">이 통신을 수행 하려면 두 조직의 Microsoft 365 또는 Office 365에 [대 한 관리자 권한이](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="6d5b0-114">![](../images/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여** Microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="6d5b0-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="6d5b0-115">Microsoft 365 또는 Office 365 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="6d5b0-116">관리 센터에서 **관리 센터**  >  **팀**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![팀 관리자를 선택 합니다.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="6d5b0-118">**팀 센터**에서 **Skype** > **레거시 포털**을 선택 하세요 
  ![ SfB 레거시 포탈을 선택 합니다.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="6d5b0-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="6d5b0-119">**비즈니스용 Skype 관리 센터**에서 **조직** > **외부 통신**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="6d5b0-120">드롭다운 상자에서 특정 비즈니스 또는 다른 도메인의 사용자와의 통신을 설정하려면 **허용된 도메인에 대해서만**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="6d5b0-121">또는 비즈니스용 Skype 정책을 연 전세계의 모든 사용자와 통신을 사용 하도록 설정 하려면 **차단 된 도메인을 제외한**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="6d5b0-122">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-122">This is the default setting.</span></span>

6. <span data-ttu-id="6d5b0-123">**차단 되거나 허용 된 도메인**에서 **+** 허용 하려는 도메인의 이름을 선택 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="6d5b0-124">다른 조직의 관리자가 **비즈니스용 Skype 관리 센터**에서 동일한 단계를 수행 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="6d5b0-125">예를 들어 허용 된 **도메인** 목록에서 관리자는 자신의 비즈니스에 대 한 도메인을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="6d5b0-126">Windows 방화벽을 사용 중인 경우 비즈니스용 Skype는 필요한 포트를 자동으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="6d5b0-127">조직에서 다른 방화벽 솔루션을 사용 하 여 네트워크의 컴퓨터를 인터넷에 연결 하지 못하도록 제한 하는 경우 클라이언트 컴퓨터에서 다음 [Office 365 url 및 IP 주소 범위](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="6d5b0-128">방화벽 또는 프록시 인프라 구성의 아웃 바운드 허용 목록에 fqdn을 추가 해야 할 수 있습니다. \*\* \* api.skype.com\*\*, \* **users.storage.live.com**및 **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="6d5b0-129">방화벽에서 이러한 포트를 여는 방법에 대 한 자세한 내용은 함께 제공 된 설명서를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="6d5b0-130">열어야 할 모든 포트 목록은 [Office 365 url 및 IP 주소 범위](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="6d5b0-131">조직의 관리자도 다음 단계를 따랐는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="6d5b0-132">**테스트 하는 데 최대 24 시간까지 기다립니다**.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="6d5b0-133">외부 통신 설정을 변경 하는 경우 변경 내용이 모든 데이터 센터에 걸친 최대 24 시간이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="6d5b0-134">![Skype ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 를 이용 하시면 skype를 사용 하는 모든 사람과 메신저 대화를 사용자에 게 제공 하 여 무료 소비자 앱!</span><span class="sxs-lookup"><span data-stu-id="6d5b0-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="6d5b0-135">자세히 알아보려면 [비즈니스용 skype 사용자가 skype 연락처를 추가 하도록 허용](let-skype-for-business-users-add-skype-contacts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="6d5b0-136">테스트 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6d5b0-136">Test and troubleshoot</span></span>

<span data-ttu-id="6d5b0-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5b0-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="6d5b0-138">**B2b 통신을 설정할 때 발생 하는 가장 일반적인 문제로 인해 [Office 365 url 및 IP 주소 범위가](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) 적절 하 게 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6d5b0-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="6d5b0-139">설정을 테스트 하려면 회사 방화벽 뒤에 있지 않은 비즈니스용 Skype에 대 한 연락처가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="6d5b0-140">외부 통신 설정을 변경한 후에는 **24 시간까지 테스트를 기다립니다**.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="6d5b0-141">비즈니스용 Skype에서 비즈니스용 Skype에서 대화 상대를 검색 하 고 채팅 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="6d5b0-142">회사 정책 때문에 보낼 수 없다는 메시지가 표시 되는 경우 [Office 365 url 및 IP 주소 범위를 다시](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="6d5b0-143">Skype for Business 연락처에 게 채팅 요청을 보내십시오.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="6d5b0-144">요청을 받지 못한 경우 (방화벽 설정이 올바른지 이미 확인했다고 가정한다면) 방화벽 설정에 문제가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="6d5b0-145">문제가 방화벽에 속하지 않는 것을 테스트 하는 또 다른 방법은 커피숍과 같이 방화벽 뒤에 있지 않은 wifi 위치로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="6d5b0-146">비즈니스용 Skype를 사용 하 여 대화 상대에 게 채팅 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="6d5b0-147">메시지가 표시 되지만 작업 중에는 그렇지 않은 경우에는 방화벽이 문제가 되는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="6d5b0-148">다른 비즈니스에 연결할 때 발견 되는 다른 사용자를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="6d5b0-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="6d5b0-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5b0-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="6d5b0-150">다른 비즈니스용 Skype 사용자와 외부 통신을 사용 하도록 설정한 후 사용자는 로그인 이름을 검색 하 여 페더레이션된 Skype 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="6d5b0-151">예를 Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="6d5b0-152">그런 다음 연락처 목록에 사용자를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-152">Then they will need to add the person to their list of contacts.</span></span>
  
![페더레이션된 비즈니스에서 사용자를 찾으려면 해당 전자 메일 주소를 검색 해야 합니다 (일반적으로 로그인 이름 이기도 함).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="6d5b0-154">페더레이션된 비즈니스와의 통신 설정에 대 한 팁</span><span class="sxs-lookup"><span data-stu-id="6d5b0-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="6d5b0-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5b0-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="6d5b0-156">비즈니스용 Skype 2015 및 비즈니스용 Skype Online 간의 페더레이션을 구성 하려면이 문서: [비즈니스용 Skype online을 사용 하 여 페더레이션 구성](https://technet.microsoft.com/library/jj205126.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>

- <span data-ttu-id="6d5b0-157">Lync와 비즈니스용 Skype Online 간의 페더레이션을 구성 하려면이 문서에서는 [Lync Online 고객에 대 한 페더레이션 지원 구성을](https://technet.microsoft.com/library/hh202193.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>

- <span data-ttu-id="6d5b0-158">Microsoft 365 또는 Office 365에 있는 두 개의 비즈니스용 Skype 사용자 들이 별도의 도메인에서 서로 통신 하는 경우, 두 조직 모두에 설정 된 비즈니스용 Skype 기능 (예: 비디오 대화 또는 데스크톱 공유)만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="6d5b0-159">조직의 비즈니스용 Skype 사용자가 In-Place 또는 소송 보존에 저장 되어 있는 경우 해당 사용자와 다른 비즈니스용 Skype 또는 Skype 사용자 간 메신저 대화는 사서함에 **복구 가능한 항목** 으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="6d5b0-160">이러한 대화는 사서함의 **대화 내용** 폴더에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="6d5b0-161">특정 개인에 대 한 외부 통신 끄기</span><span class="sxs-lookup"><span data-stu-id="6d5b0-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="6d5b0-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5b0-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="6d5b0-163">전체 비즈니스에 대해 외부 통신을 사용 하도록 설정한 후에는 특정 개인에 대해서만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="6d5b0-164">Microsoft 365 또는 Office 365 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="6d5b0-165">관리 센터에서 **사용자**  >  **활성 사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="6d5b0-166">사용자 목록에서 사용자를 선택 하 고 **기타 설정**아래에 있는 **비즈니스용 Skype 속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![비즈니스용 Skype 선택](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="6d5b0-168">**비즈니스용 Skype 관리 센터**에서 **외부 통신**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="6d5b0-169">**옵션** 페이지에서 모든 선택 항목이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="6d5b0-170">사용 하지 않을 통신을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="6d5b0-171">다음 이미지는 Jakob이 다른 신뢰할 수 있는 회사의 사용자와 통신할 수 있지만 다른 Skype 사용자와는 통신 하지 못하는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![외부 연락처 선택](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="6d5b0-173">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6d5b0-174">변경 내용이 적용 되려면 최대 24 시간 동안 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="6d5b0-175">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6d5b0-175">Related topics</span></span>

<span data-ttu-id="6d5b0-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5b0-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="6d5b0-177">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="6d5b0-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="6d5b0-178">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="6d5b0-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  