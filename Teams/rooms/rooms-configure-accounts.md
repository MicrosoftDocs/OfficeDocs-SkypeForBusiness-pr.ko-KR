---
title: Microsoft Teams 회의실에 대한 계정 구성
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
description: Exchange 및 비즈니스용 Skype에서 Microsoft Teams 회의실에 대한 계정을 구성하는 방법을 알아보는 이 항목을 참조하세요.
ms.openlocfilehash: e171ef22dd1733c06b03a4a9483f591d73d70cb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662523"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="44588-103">Microsoft Teams 회의실에 대한 계정 구성</span><span class="sxs-lookup"><span data-stu-id="44588-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="44588-104">Microsoft Teams 회의실 및 Exchange 및 비즈니스용 Skype와 통합하는 방법에 대해 알아보는 이 항목을 읽어보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="44588-105">이 항목에서는 Microsoft Exchange 및 비즈니스용 Skype에서 Microsoft Teams 회의실에서 사용하는 계정을 만드는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="44588-106">Microsoft Teams 회의실 장치에 대한 배포 지침은 Microsoft Teams 회의실 구성 [콘솔에서 설명합니다.](console.md)</span><span class="sxs-lookup"><span data-stu-id="44588-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="44588-107">인프라는 다음 구성 중 하나에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="44588-108">온라인 배포: 조직의 환경은 Microsoft 365 또는 Office 365에 전적으로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="44588-108">Online deployment: Your organization's environment is deployed entirely on Microsoft 365 or Office 365.</span></span> <span data-ttu-id="44588-109">자세한 내용은 [Microsoft 365 또는 Office 365를 통해 Microsoft Teams 회의실 배포를 참조하세요.](with-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="44588-109">For more information, see [Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="44588-110">프레미스 배포: 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버가 호스팅되는 제어하는 서버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="44588-111">자세한 내용은 비즈니스용 Skype Server를 통해 [Microsoft Teams 회의실 배포를 참조하세요.](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="44588-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="44588-112">하이브리드 배포: 조직에는 Microsoft 365 또는 Office 365를 통해 일부 호스트된 일부 및 온라인에서 호스팅된 일부 서비스가 혼합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Microsoft 365 or Office 365.</span></span> <span data-ttu-id="44588-113">Microsoft Teams 회의실에서는 다음과 같은 하이브리드 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="44588-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span>
    
  - <span data-ttu-id="44588-114">비즈니스용 Skype Server와의 Exchange Online을 프레미스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="44588-115">자세한 내용은 Exchange Online(하이브리드)을 통해 [Microsoft Teams 회의실 배포를 참조하세요.](with-exchange-online.md)</span><span class="sxs-lookup"><span data-stu-id="44588-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="44588-116">Microsoft Teams 또는 비즈니스용 Skype Online과 프레미스를 교환합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="44588-117">자세한 내용은 Exchange On-프레미스(하이브리드)에서 [Microsoft Teams 회의실 배포를 참조하세요.](with-exchange-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="44588-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="44588-118">디바이스 설정을 준비하는 방법에 영향을 주는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="44588-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="44588-119">Microsoft Teams 회의실은 Active Directory, Exchange 및 비즈니스용 Skype에서 "장치 계정"을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="44588-120">이 계정은 모임 일정에 액세스하고 Microsoft Teams 또는 비즈니스용 Skype 연결을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44588-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="44588-121">사람들이 모임을 예약하여 이 계정을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="44588-122">Microsoft Teams 회의실은 모임에 참가하고 모임 참석자들에게 다양한 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="44588-123">디바이스 계정이 없는 경우 이러한 기능은 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="44588-124">모든 장치 계정은 단일 Microsoft Teams Rooms 장치에 고유하며 몇 가지 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="44588-125">디바이스 계정을 올바르게 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="44588-126">Microsoft Teams 회의실에서 디바이스 계정의 유효성을 검사하고 적절한 Microsoft 서비스에 도달할 수 있도록 인프라를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="44588-127">실제 하드웨어 설치에 앞서 계정 생성을 잘 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="44588-128">설치하기 2~3주 전에 계정 준비가 시작하는 것이 가장 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="44588-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 

<span data-ttu-id="44588-129">Microsoft Teams Rooms 인증에는 Microsoft 365 또는 Office 365 인증이 필요하기 때문에 하이브리드 환경에서 Microsoft Teams 회의실에 사용되는 계정은 AAD(Azure Active Directory) 동기화에서 암호 동기화를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in Azure Active Directory (AAD) Sync because Microsoft Teams Rooms authentication requires Microsoft 365 or Office 365 authentication.</span></span> <span data-ttu-id="44588-130">계정을 설정할 때 계정의 SIP 주소가 AAD의 UPN(사용자 계정 이름)과 일치하는지 확인</span><span class="sxs-lookup"><span data-stu-id="44588-130">When setting up the account, make sure that the account's SIP address matches its User Principal Name (UPN) in AAD.</span></span> 
  
<span data-ttu-id="44588-131">장치 계정은 사람들이 회의실 또는 모임 공간의 계정으로 인식하는 리소스 계정으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-131">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="44588-132">해당 회의실을 사용하여 모임을 예약하려면 해당 모임에 계정을 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-132">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="44588-133">Microsoft Teams 회의실을 가장 효과적으로 사용하려면 각 팀에 할당된 장치 계정으로 동일한 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-133">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="44588-134">Microsoft Teams 회의실을 설치하는 모임 공간에 대해 리소스 사서함 계정이 이미 설정된 경우 해당 리소스 계정을 장치 계정으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-134">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="44588-135">완료되면 Microsoft Teams 회의실 장치에 장치 계정을 추가하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44588-135">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="44588-136">아래 제공된 디바이스 계정 설정 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44588-136">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="44588-137">추가 구성을 통해 Azure Monitor를 사용하여 Microsoft Teams 회의실 관리 계획에 설명된 Microsoft Azure [Monitor를](azure-monitor-plan.md)사용하여 원격 관리가 가능합니다. Azure [Monitor를](azure-monitor-deploy.md)사용하여 Microsoft Teams 회의실 관리를 배포하고, Azure Monitor를 사용하여 Microsoft Teams Rooms 디바이스를 관리할 [수 있습니다.](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="44588-137">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="44588-138">기본 구성</span><span class="sxs-lookup"><span data-stu-id="44588-138">Basic configuration</span></span>

<span data-ttu-id="44588-139">이러한 속성은 디바이스 계정이 Microsoft Teams 회의실과 작동하기 위한 최소 구성을 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44588-139">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="44588-140">디바이스 계정에 추가 설정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-140">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="44588-141">**속성**</span><span class="sxs-lookup"><span data-stu-id="44588-141">**Property**</span></span>|<span data-ttu-id="44588-142">**목적**</span><span class="sxs-lookup"><span data-stu-id="44588-142">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44588-143">Exchange 사서함(Exchange 2013 SP1 이상 또는 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="44588-143">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="44588-144">Exchange 사서함을 사용하여 계정을 사용하도록 설정하면 장치 계정에 메일 및 모임 요청을 수신 및 보내고 Microsoft Teams 회의실 장치에 모임 일정을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-144">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="44588-145">Microsoft Teams 회의실 사서함은 회의실 사서함이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-145">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="44588-146">비즈니스용 Skype가 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-146">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="44588-147">비디오 통화, IM, 화면 공유와 같은 다양한 회의 기능을 사용하려면 비즈니스용 Skype를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-147">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="44588-148">비즈니스용 Skype Online과 비즈니스용 Skype Server가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="44588-148">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="44588-149">암호 사용</span><span class="sxs-lookup"><span data-stu-id="44588-149">Password-enabled</span></span>  <br/> |<span data-ttu-id="44588-150">장치 계정은 암호로 사용하도록 설정해야 합니다. 또는 Exchange 또는 비즈니스용 Skype Server를 사용하여 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-150">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="44588-151">고급 구성</span><span class="sxs-lookup"><span data-stu-id="44588-151">Advanced configuration</span></span>

<span data-ttu-id="44588-152">기본 구성의 속성은 디바이스 계정을 간단한 환경에서 설정할 수 있도록 허용하지만 Microsoft Teams 회의실이 디바이스 계정을 성공적으로 사용하려면 사용자 환경에 디렉터리 계정에 대한 다른 제한 사항이 충족되어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-152">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="44588-153">**속성**</span><span class="sxs-lookup"><span data-stu-id="44588-153">**Property**</span></span>|<span data-ttu-id="44588-154">**목적**</span><span class="sxs-lookup"><span data-stu-id="44588-154">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44588-155">인증서 기반 인증</span><span class="sxs-lookup"><span data-stu-id="44588-155">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="44588-156">Exchange 및 비즈니스용 Skype Server 모두에 인증서가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-156">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="44588-157">인증서를 배포하려면 관리자로 로그인할 때 인증서를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-157">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="44588-158">디바이스 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 구성하는 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44588-158">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="44588-159">Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1계정을 만들거나 호환되는 Microsoft Teams 회의실 장치 계정으로 전환할 수 있도록 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 스크립트인 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44588-159">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="44588-160">Windows PowerShell cmdlet을 통해 Microsoft 365 또는 Office 365 UI를 사용하려면 일부 단계를 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44588-160">If you prefer to use the Microsoft 365 or Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="44588-161">[Microsoft 365 또는 Office 365를](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)사용하여 장치 계정 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44588-161">See [Creating a device account using Microsoft 365 or Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44588-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44588-162">See also</span></span>

[<span data-ttu-id="44588-163">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="44588-163">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="44588-164">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="44588-164">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="44588-165">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="44588-165">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

