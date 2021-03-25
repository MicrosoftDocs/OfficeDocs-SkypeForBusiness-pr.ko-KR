---
title: Microsoft Teams Rooms에 대한 계정 구성
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Exchange 및 비즈니스용 Skype에서 Microsoft Teams Rooms에 대한 계정을 구성하는 방법을 알아보고 이 항목을 참조하세요.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117476"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="85652-103">Microsoft Teams Rooms에 대한 계정 구성</span><span class="sxs-lookup"><span data-stu-id="85652-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="85652-104">이 항목에서 Microsoft Teams Rooms 및 Exchange 및 비즈니스용 Skype와 통합하는 방법에 대해 알아보고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="85652-105">이 항목에서는 Microsoft Exchange 및 비즈니스용 Skype에서 Microsoft Teams Rooms에서 사용하는 계정을 만드는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="85652-106">Microsoft Teams Rooms 디바이스에 대한 배포 지침은 Microsoft Teams Rooms 구성 [콘솔에 설명됩니다.](console.md)</span><span class="sxs-lookup"><span data-stu-id="85652-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="85652-107">인프라는 다음 구성 중 하나에 빠질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="85652-108">온라인 배포: 조직의 환경은 Microsoft 365 또는 Office 365에 전적으로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="85652-108">Online deployment: Your organization's environment is deployed entirely on Microsoft 365 or Office 365.</span></span> <span data-ttu-id="85652-109">자세한 내용은 [Microsoft 365 또는 Office 365를 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="85652-109">For more information, see [Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="85652-110">프레미스 배포: 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버가 호스팅되는 제어하는 서버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="85652-111">자세한 내용은 비즈니스용 [Skype 서버를 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="85652-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="85652-112">하이브리드 배포: 조직에는 Microsoft 365 또는 Office 365를 통해 호스팅된 일부 프레미스 및 일부 온라인 호스팅 서비스가 혼합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Microsoft 365 or Office 365.</span></span> <span data-ttu-id="85652-113">Microsoft Teams Rooms에서는 다음 하이브리드 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85652-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span>
    
  - <span data-ttu-id="85652-114">비즈니스용 Skype 서버온-프레미스와 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="85652-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="85652-115">자세한 내용은 [Exchange Online(하이브리드)을 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-exchange-online.md)</span><span class="sxs-lookup"><span data-stu-id="85652-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="85652-116">Microsoft Teams 또는 비즈니스용 Skype Online과 프레미스에서 교환합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="85652-117">자세한 내용은 [Exchange on-프레미스(하이브리드)를 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-exchange-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="85652-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="85652-118">디바이스 설정을 준비하는 방법에 영향을 줄 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="85652-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="85652-119">Microsoft Teams Rooms는 Active Directory, Exchange 및 비즈니스용 Skype에서 "디바이스 계정"을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="85652-120">이 계정은 모임 일정에 액세스하고 Microsoft Teams 또는 비즈니스용 Skype 연결을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85652-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="85652-121">사용자와 함께 모임을 예약하여 이 계정을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="85652-122">Microsoft Teams Rooms는 모임에 참가하고 모임 참석자들에게 다양한 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="85652-123">디바이스 계정이 없는 경우 이러한 기능은 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="85652-124">모든 디바이스 계정은 단일 Microsoft Teams Rooms 디바이스에 고유하며 몇 가지 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="85652-125">디바이스 계정을 올바르게 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="85652-126">Microsoft Teams Rooms가 디바이스 계정의 유효성을 검사하고 적절한 Microsoft 서비스에 도달할 수 있도록 인프라를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="85652-127">실제 하드웨어 설치에 앞서 계정 만들기를 잘하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="85652-128">이상적으로 계정 준비는 설치 2~3주 전에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="85652-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 

<span data-ttu-id="85652-129">Microsoft Teams Rooms에 사용되는 계정은 Microsoft Teams Rooms 인증에 Microsoft 365 또는 Office 365 인증이 필요하기 때문에 AAD(Azure Active Directory) 동기화에서 암호 동기화를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in Azure Active Directory (AAD) Sync because Microsoft Teams Rooms authentication requires Microsoft 365 or Office 365 authentication.</span></span> <span data-ttu-id="85652-130">계정을 설정할 때 계정의 SIP 주소가 AAD의 사용자 주체 이름(UPN)과 일치하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="85652-130">When setting up the account, make sure that the account's SIP address matches its User Principal Name (UPN) in AAD.</span></span> 
  
<span data-ttu-id="85652-131">디바이스 계정을 사람들이 회의실 또는 모임 공간의 계정으로 인식하는 리소스 계정으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-131">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="85652-132">해당 회의실을 사용하여 모임을 예약하려는 경우 해당 모임에 계정을 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-132">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="85652-133">Microsoft Teams Rooms를 가장 효과적으로 사용하려면 각각에 할당된 디바이스 계정과 동일한 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-133">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="85652-134">Microsoft Teams Rooms를 설치하는 모임 공간에 대해 리소스 사서함 계정이 이미 설정되어 있는 경우 해당 리소스 계정을 디바이스 계정으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-134">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="85652-135">완료되면 Microsoft Teams Rooms 디바이스에 디바이스 계정을 추가하기만하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85652-135">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="85652-136">아래 제공된 디바이스 계정 설정 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85652-136">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="85652-137">추가 구성을 통해 Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 계획, [Azure Monitor를](azure-monitor-plan.md)사용하여 [Microsoft Teams Rooms](azure-monitor-deploy.md)관리 배포 및 Azure [Monitor를](azure-monitor-manage.md)사용하여 Microsoft Teams Rooms 디바이스 관리에 설명된 바와 같이 Microsoft Azure Monitor를 사용하여 원격 관리가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-137">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="85652-138">기본 구성</span><span class="sxs-lookup"><span data-stu-id="85652-138">Basic configuration</span></span>

<span data-ttu-id="85652-139">이러한 속성은 디바이스 계정이 Microsoft Teams Rooms와 함께 작동하기 위한 최소 구성을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-139">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="85652-140">디바이스 계정에 추가 설정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-140">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="85652-141">**속성**</span><span class="sxs-lookup"><span data-stu-id="85652-141">**Property**</span></span>|<span data-ttu-id="85652-142">**목적**</span><span class="sxs-lookup"><span data-stu-id="85652-142">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85652-143">Exchange 사서함(Exchange 2013 SP1 이상 또는 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="85652-143">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="85652-144">Exchange 사서함을 사용하여 계정을 사용하도록 설정하면 디바이스 계정에 메일 및 모임 요청을 모두 수신하고 보내고 Microsoft Teams Rooms 디바이스에 모임 일정을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-144">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="85652-145">Microsoft Teams Room 사서함은 회의실 사서함이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-145">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="85652-146">비즈니스용 Skype가 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-146">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="85652-147">화상 통화, IM 및 화면 공유와 같은 다양한 회의 기능을 사용하려면 비즈니스용 Skype를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-147">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="85652-148">비즈니스용 Skype Online 및 비즈니스용 Skype 서버가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85652-148">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="85652-149">암호 사용</span><span class="sxs-lookup"><span data-stu-id="85652-149">Password-enabled</span></span>  <br/> |<span data-ttu-id="85652-150">디바이스 계정을 암호로 사용하도록 설정해야 합니다. 또는 Exchange 또는 비즈니스용 Skype 서버로 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-150">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="85652-151">고급 구성</span><span class="sxs-lookup"><span data-stu-id="85652-151">Advanced configuration</span></span>

<span data-ttu-id="85652-152">기본 구성에 대한 속성은 디바이스 계정을 간단한 환경에서 설정할 수 있도록 허용하지만 Microsoft Teams Rooms가 디바이스 계정을 성공적으로 사용하려면 사용자 환경에 충족해야 하는 디렉터리 계정에 대한 다른 제한 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-152">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="85652-153">**속성**</span><span class="sxs-lookup"><span data-stu-id="85652-153">**Property**</span></span>|<span data-ttu-id="85652-154">**목적**</span><span class="sxs-lookup"><span data-stu-id="85652-154">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85652-155">인증서 기반 인증</span><span class="sxs-lookup"><span data-stu-id="85652-155">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="85652-156">Exchange 및 비즈니스용 Skype 서버에 인증서가 모두 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-156">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="85652-157">인증서를 배포하려면 관리자로 로그인할 때 인증서를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-157">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="85652-158">디바이스 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 구성하는 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85652-158">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="85652-159">Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1디바이스 계정을 만들거나 호환되는 Microsoft Teams Rooms 디바이스 계정으로 전환하는 데 도움이 되는 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 스크립트인 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85652-159">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="85652-160">Microsoft 365 또는 Office 365 UI를 Windows PowerShell cmdlet을 통해 사용하려면 일부 단계를 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85652-160">If you prefer to use the Microsoft 365 or Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="85652-161">[Microsoft 365 또는 Office 365를](/surface-hub/create-a-device-account-using-office-365)사용하여 디바이스 계정 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85652-161">See [Creating a device account using Microsoft 365 or Office 365](/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85652-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85652-162">See also</span></span>

[<span data-ttu-id="85652-163">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="85652-163">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="85652-164">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="85652-164">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="85652-165">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="85652-165">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)