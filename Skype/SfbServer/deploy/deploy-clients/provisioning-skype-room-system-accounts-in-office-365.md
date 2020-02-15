---
title: Office 365에서 Skype 대화방 시스템 계정 프로 비전
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Office 365에서 Skype 대화방 시스템 계정을 프로 비전 하는 방법에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037728"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="6b3b9-103">Office 365에서 Skype 대화방 시스템 계정 프로 비전</span><span class="sxs-lookup"><span data-stu-id="6b3b9-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="6b3b9-104">Office 365에서 Skype 대화방 시스템 계정을 프로 비전 하는 방법에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="6b3b9-105">다음 섹션에서는 Office 365 테 넌 트에 대 한 Skype 대화방 시스템 계정 프로 비전에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="6b3b9-106">Office 365 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6b3b9-106">Office 365 prerequisites</span></span>

<span data-ttu-id="6b3b9-107">온라인 테 넌 트가 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="6b3b9-108">Office 365 계획에는 비즈니스용 Skype Online 계획 2 또는 Office 365 E1, E3 또는 E5가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="6b3b9-109">비즈니스용 Skype Online 계획에 대 한 자세한 내용은 [비즈니스용 Skype Online 서비스 설명을](https://technet.microsoft.com/library/jj822172.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="6b3b9-110">테 넌 트에 비즈니스용 Skype의 회의 기능이 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="6b3b9-111">테 넌 트에서 Exchange Online을 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="6b3b9-112">테 넌 트 원격 관리자에 게는 다음 PowerShell 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="6b3b9-113">Exchange 원격 PowerShell 액세스</span><span class="sxs-lookup"><span data-stu-id="6b3b9-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="6b3b9-114">비즈니스용 Skype Online 원격 PowerShell 액세스</span><span class="sxs-lookup"><span data-stu-id="6b3b9-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="6b3b9-115">Office 365 디렉터리 액세스에 액세스 하기 위한 windows PowerShell 용 windows Azure Active Directory 모듈</span><span class="sxs-lookup"><span data-stu-id="6b3b9-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="6b3b9-116">Skype 대화방 계정의 경우 다음 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="6b3b9-117">Skype 모임을 사용 하도록 설정 하려면 비즈니스용 Skype Online 계획 2 또는 Office 365 E1 또는 E3 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="6b3b9-118">전화 번호를 사용 하 여 대화방을 사용할 수 있도록 Enterprise Voice 기능을 사용 하 여 대화방을 entitle 전화 시스템 라이선스 또는 Office 365 E5가 있는 비즈니스용 Skype Online 계획 2가 필요 합니다 (1).</span><span class="sxs-lookup"><span data-stu-id="6b3b9-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="6b3b9-119">모임에서 전화 접속 기능을 사용 해야 하는 경우에는 오디오 회의 및 전화 시스템 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="6b3b9-120">모임에서 전화 걸기 기능이 필요한 경우 국내 또는 국내 및 국제 통화 요금제가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="6b3b9-121">계정을 리소스 사서함 계정으로 구성 해야 하므로 Skype 대화방 계정에 Exchange Online 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="6b3b9-122">프로 비전 개요</span><span class="sxs-lookup"><span data-stu-id="6b3b9-122">Provisioning overview</span></span>

<span data-ttu-id="6b3b9-123">다음 다이어그램은 Office 365에서 Skype 대화방 시스템 계정 프로 비전 흐름에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365에 대 한 Skype 대화방 시스템 프로 비전 단계](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="6b3b9-125">새 회의실 확인</span><span class="sxs-lookup"><span data-stu-id="6b3b9-125">Identify a new conference room</span></span>

<span data-ttu-id="6b3b9-126">Exchange에 일정 기능을 제공 하는 리소스 대화방 사서함이 이미 있거나 Skype 대화방 시스템 배포를 촉진 하기 위해 처음으로 리소스 사서함을 만드는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="6b3b9-127">모든 경우에는 테 넌 트에서 사용할 대화방 계정을 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="6b3b9-128">Exchange Online 프로 비전 및 비즈니스용 Skype 프로 비전 섹션에서는 두 가지 계정 유형에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="6b3b9-129">예를 들어 다음과 같은 두 개의 대화방을 사용 하 고 있으며 두 채팅방을 모두에 대해 Skype 대화방 시스템을 배포 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="6b3b9-130">기존 리소스 사서함 계정: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6b3b9-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="6b3b9-131">새 리소스 사서함 계정: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6b3b9-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="6b3b9-132">Exchange Online 구축</span><span class="sxs-lookup"><span data-stu-id="6b3b9-132">Exchange Online provisioning</span></span>

<span data-ttu-id="6b3b9-133">먼저, [Exchange Online powershell에 연결](https://go.microsoft.com/fwlink/p/?LinkId=396554)항목의 지침에 따라 Exchange online powershell에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="6b3b9-134">Skype 대화방 시스템에 대 한 기존 리소스 대화방 사서함 계정을 설정 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="6b3b9-135">Skype 대화방 시스템에 대 한 새 Exchange 리소스 사서함 계정을 만들려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="6b3b9-136">이전 명령은 계정을 사용 하 여 Skype 대화방 시스템 사용에 대 한 새 Exchange 리소스 사서함 계정을 설정 하거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="6b3b9-137">사서함을 만든 후에 Exchange Online PowerShell에서 설정-CalendarProcessing cmdlet을 사용 하 여 사서함을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="6b3b9-138">자세한 내용은 단일 포리스트 온-프레미스 배포의 3 ~ 6 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="6b3b9-139">비즈니스용 Skype 온라인 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6b3b9-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="6b3b9-140">이제 비즈니스용 Skype Online (요금제 2) 또는 비즈니스용 skype Online (요금제 3)에 설명 된 대로 office 365 관리 포털을 사용 하 여 microsoft에 대 한 라이선스 [할당 또는 365 제거](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) (비즈니스용 skype [추가 기능 라이선스](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7))를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="6b3b9-141">비즈니스용 Skype Online에 대 한 라이선스를 할당 하면 로그인 하 여 비즈니스용 Skype 클라이언트를 사용 하 여 계정이 활성 상태 인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="6b3b9-142">비즈니스용 Skype Online 프로 비전</span><span class="sxs-lookup"><span data-stu-id="6b3b9-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="6b3b9-143">리소스 대화방 사서함 계정을 만들어 이전에 표시 된 대로 사용 하도록 설정 했으며 비즈니스용 Skype Online에 대 한 계정을 사용 하도록 허가 받은 후에는 다음을 통해 계정으로 Exchange Online 포리스트에서 비즈니스용 Skype Online 포리스트와 동기화 됩니다. Windows Azure Active Directory 포리스트</span><span class="sxs-lookup"><span data-stu-id="6b3b9-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="6b3b9-144">비즈니스용 Skype Online 풀에서 Skype 대화방 시스템 계정을 구축 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="6b3b9-145">이러한 단계는 Exchange Online에서 사용 하도록 설정 된 경우 동일한 방식으로 비즈니스용 Skype Online에 동기화 되는 기존 리소스 사서함 계정 또는 새로 만든 계정 (confrm1 또는 confrm2)에 대해 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="6b3b9-146">원격 PowerShell 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="6b3b9-147">비즈니스용 Skype 온라인 커넥터 모듈 및 Microsoft Online Services 로그인 도우미를 다운로드 하 고 컴퓨터가 구성 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="6b3b9-148">자세한 내용은 [Windows PowerShell을 사용할 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="6b3b9-149">비즈니스용 Skype에 대해 Skype 대화방 시스템 계정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="6b3b9-150">다음 명령을 사용 하 여이 속성을 반환 하 여 비즈니스용 Skype 사용자가 속해 있는 RegistrarPool 주소를 기존 계정 중 하나로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="6b3b9-151">Skype 대화방 시스템 계정에 대해서는 MFA (multi-factor Authentication)가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="6b3b9-152">암호 만료</span><span class="sxs-lookup"><span data-stu-id="6b3b9-152">Password expiration</span></span>

<span data-ttu-id="6b3b9-153">Office 365에서 다른 암호 만료 정책을 구성 하지 않으면 모든 사용자 계정에 대 한 기본 암호 만료 정책이 90 일입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="6b3b9-154">Skype 대화방 시스템 계정에 대해 다음 단계를 수행 하 여 암호 사용 기간 제한 없음 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="6b3b9-155">테 넌 트 전역 관리자 자격 증명을 사용 하 여 Windows Azure Active Directory 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="6b3b9-156">다음 명령을 사용 하 여 이전에 만든 Skype 대화방 시스템 대화방 계정의 암호 사용 기간 제한 없음 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="6b3b9-157">자세한 내용은 [Windows PowerShell을 사용할 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="6b3b9-158">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="6b3b9-158">Validate</span></span>

<span data-ttu-id="6b3b9-159">유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용 하 여 만든 계정에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

