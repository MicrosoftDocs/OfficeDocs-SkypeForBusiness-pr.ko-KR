---
title: Microsoft 팀 대화방 계정 구성
ms.author: v-lanac
author: lanachin
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
description: 이 항목에서는 Exchange 및 비즈니스용 Skype에서 Microsoft 팀 방에 대 한 계정을 구성 하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 98507b3c5fb2b2d9383bcbff6ddcbdda0de19b9f
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262485"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="21c10-103">Microsoft 팀 대화방 계정 구성</span><span class="sxs-lookup"><span data-stu-id="21c10-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="21c10-104">이 항목에서는 Microsoft 팀 대화방 및 Exchange 및 비즈니스용 Skype와 통합 하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="21c10-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="21c10-105">이 항목에서는 microsoft Exchange 및 비즈니스용 Skype에서 Microsoft 팀 대화방에 사용 되는 계정을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="21c10-106">Microsoft 팀 회의실 장치에 대 한 배포 지침은 [Microsoft 팀 대화방 콘솔 구성](console.md)에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="21c10-107">인프라는 다음 구성 중 하나에 해당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="21c10-108">온라인 배포: 조직의 환경은 전적으로 Microsoft 365 또는 Office 365에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-108">Online deployment: Your organization's environment is deployed entirely on Microsoft 365 or Office 365.</span></span> <span data-ttu-id="21c10-109">자세한 내용은 [microsoft 365 또는 Office 365을 사용 하 여 Microsoft 팀 대화방 배포](with-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21c10-109">For more information, see [Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="21c10-110">온-프레미스 배포: 조직에서 Active Directory, Exchange, 비즈니스용 Skype 서버가 호스팅되는 서버를 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="21c10-111">자세한 내용은 [비즈니스용 Skype 서버에 Microsoft 팀 대화방 배포](with-skype-for-business-server-2015.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21c10-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="21c10-112">하이브리드 배포: 조직에는 일부 서비스와 함께 온-프레미스 호스트와 Microsoft 365 또는 Office 365를 통해 온라인으로 호스팅되는 서비스가 혼합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Microsoft 365 or Office 365.</span></span> <span data-ttu-id="21c10-113">Microsoft 팀 대화방에서는 다음과 같은 하이브리드 시나리오가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span>
    
  - <span data-ttu-id="21c10-114">비즈니스용 Skype 서버 (온-프레미스)로 Exchange Online을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="21c10-115">자세한 내용은 [Exchange Online (하이브리드)을 사용 하 여 Microsoft 팀 대화방 배포](with-exchange-online.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21c10-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="21c10-116">Microsoft 팀 또는 비즈니스용 Skype Online을 사용 하 여 온-프레미스 Exchange</span><span class="sxs-lookup"><span data-stu-id="21c10-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="21c10-117">자세한 내용은 [Exchange를 온-프레미스에 Microsoft 팀 대화방 배포 (하이브리드)](with-exchange-on-premises.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21c10-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="21c10-118">사용 중인 구성은 장치 설정 준비 방법에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="21c10-119">Microsoft 팀 대화방에는 Active Directory, Exchange, 비즈니스용 Skype에서 "디바이스 계정"이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="21c10-120">이 계정은 모임 일정에 액세스 하 고 Microsoft 팀 또는 비즈니스용 Skype 연결을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="21c10-121">다른 사용자가이 계정을 사용 하 여 모임을 예약 하 여 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="21c10-122">Microsoft 팀 대화방은 해당 모임에 참가 하 고 모임 참석자에 게 다양 한 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="21c10-123">장치 계정이 없으면 이러한 기능 중 어떤 것도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="21c10-124">모든 장치 계정은 단일 Microsoft 팀 대화방 장치에 고유 하며, 몇 가지 설정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="21c10-125">디바이스 계정이 올바르게 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="21c10-126">Microsoft 팀 대화방에서 디바이스 계정의 유효성을 검사 하 고 해당 Microsoft 서비스에 연결할 수 있도록 인프라를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="21c10-127">실제 하드웨어 설치 전에 계정 만들기를 잘 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="21c10-128">계정 준비는 설치 전에 2-3 주 동안 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 

<span data-ttu-id="21c10-129">하이브리드 환경에서 microsoft 팀 대화방 인증에 Microsoft 365 또는 Office 365 인증이 필요 하므로 Microsoft 팀 대화방에 사용 되는 계정에는 AAD (Azure Active Directory) 동기화에서 암호 동기화가 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in Azure Active Directory (AAD) Sync because Microsoft Teams Rooms authentication requires Microsoft 365 or Office 365 authentication.</span></span> <span data-ttu-id="21c10-130">계정을 설정할 때 계정의 SIP 주소가 AAD의 UPN (사용자 계정 이름)과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-130">When setting up the account, make sure that the account's SIP address matches its User Principal Name (UPN) in AAD.</span></span> 
  
<span data-ttu-id="21c10-131">장치 계정은 사용자가 회의실 또는 모임 공간의 계정으로 인식 하는 리소스 계정 이라고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-131">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="21c10-132">해당 회의실을 사용 하 여 모임을 예약 하려면 계정을 해당 모임에 초대 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-132">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="21c10-133">Microsoft 팀 회의실을 가장 효율적으로 사용 하기 위해 각각에 게 할당 된 디바이스 계정에 대해 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-133">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="21c10-134">Microsoft 팀 대화방을 설치 하는 모임 공간에 대해 이미 리소스 사서함 계정이 설정 되어 있는 경우 해당 리소스 계정을 디바이스 계정으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-134">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="21c10-135">작업을 완료 한 후에는 Microsoft 팀 대화방 장치에 디바이스 계정을 추가 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-135">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="21c10-136">아래에서 제공 하는 디바이스 계정 설정 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21c10-136">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="21c10-137">추가 구성을 사용 하는 경우 azure monitor를 사용 하 여 [Microsoft 팀 공간 관리 계획](azure-monitor-plan.md), [Azure 모니터로 microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md), microsoft [팀 공간 장치를 azure Monitor를 사용](azure-monitor-manage.md)하 여 관리에 설명 된 대로 microsoft Azure Monitor를 사용 하 여 원격 관리를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-137">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="21c10-138">기본 구성</span><span class="sxs-lookup"><span data-stu-id="21c10-138">Basic configuration</span></span>

<span data-ttu-id="21c10-139">이러한 속성은 Microsoft 팀 대화방에서 사용할 수 있는 디바이스 계정에 대 한 최소 구성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-139">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="21c10-140">디바이스 계정에 추가 설정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-140">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="21c10-141">**속성**</span><span class="sxs-lookup"><span data-stu-id="21c10-141">**Property**</span></span>|<span data-ttu-id="21c10-142">**것**</span><span class="sxs-lookup"><span data-stu-id="21c10-142">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21c10-143">Exchange 사서함 (Exchange 2013 SP1 이상 또는 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="21c10-143">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="21c10-144">Exchange 사서함을 사용 하 여 계정을 사용 하도록 설정 하면 디바이스 계정에 전자 메일 및 모임 요청을 받고 보낼 수 있고 Microsoft 팀 대화방 장치에 모임 일정을 표시 하는 기능이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-144">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="21c10-145">Microsoft 팀 대화방 사서함은 회의실 사서함 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-145">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="21c10-146">비즈니스용 Skype 사용 가능</span><span class="sxs-lookup"><span data-stu-id="21c10-146">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="21c10-147">비디오 통화, 메신저 대화, 화면 공유 등 다양 한 회의 기능을 사용 하려면 비즈니스용 Skype를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-147">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="21c10-148">비즈니스용 Skype Online 및 비즈니스용 Skype 서버를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-148">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="21c10-149">암호 사용</span><span class="sxs-lookup"><span data-stu-id="21c10-149">Password-enabled</span></span>  <br/> |<span data-ttu-id="21c10-150">장치 계정은 암호로 설정 되어 있거나, Exchange 또는 비즈니스용 Skype 서버를 사용 하 여 인증 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-150">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="21c10-151">고급 구성</span><span class="sxs-lookup"><span data-stu-id="21c10-151">Advanced configuration</span></span>

<span data-ttu-id="21c10-152">기본 구성의 속성은 장치 계정을 간단한 환경에서 설정할 수 있지만, 사용자 환경에는 Microsoft 팀 대화방에서 디바이스 계정을 사용 하기 위해 충족 해야 하는 디렉터리 계정에 대 한 기타 제한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-152">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="21c10-153">**속성**</span><span class="sxs-lookup"><span data-stu-id="21c10-153">**Property**</span></span>|<span data-ttu-id="21c10-154">**것**</span><span class="sxs-lookup"><span data-stu-id="21c10-154">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21c10-155">인증서 기반 인증</span><span class="sxs-lookup"><span data-stu-id="21c10-155">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="21c10-156">Exchange 및 비즈니스용 Skype 서버 모두에 대 한 인증서가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-156">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="21c10-157">인증서를 배포 하려면 관리자로 로그인 할 때이를 로드 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-157">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="21c10-158">디바이스 계정을 설정 하는 가장 쉬운 방법은 원격 Windows PowerShell을 사용 하 여 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-158">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="21c10-159">Microsoft는 새 디바이스 계정을 만드는 데 도움이 되는 스크립트 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)또는 호환 되는 Microsoft 팀 대화방 디바이스 계정으로 전환 하는 데 도움이 되는 기존 리소스 계정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-159">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="21c10-160">Windows PowerShell cmdlet을 통해 Microsoft 365 또는 Office 365 UI를 사용 하려는 경우 몇 가지 단계를 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c10-160">If you prefer to use the Microsoft 365 or Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="21c10-161">[Microsoft 365 또는 Office 365를 사용 하 여 디바이스 계정 만들기를](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21c10-161">See [Creating a device account using Microsoft 365 or Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21c10-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21c10-162">See also</span></span>

[<span data-ttu-id="21c10-163">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="21c10-163">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="21c10-164">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="21c10-164">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="21c10-165">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="21c10-165">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

