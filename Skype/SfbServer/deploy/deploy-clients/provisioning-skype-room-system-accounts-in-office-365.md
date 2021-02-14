---
title: Microsoft 365 및 Office 365에서 Skype 룸 시스템 계정 프로비전
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 이 항목을 읽고 Microsoft 365 또는 Office 365에서 Skype 룸 시스템 계정을 프로비전하는 방법을 배워야 합니다.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820848"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="8f10e-103">Microsoft 365 및 Office 365에서 Skype 룸 시스템 계정 프로비전</span><span class="sxs-lookup"><span data-stu-id="8f10e-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="8f10e-104">이 항목을 읽고 Microsoft 365 또는 Office 365에서 Skype 룸 시스템 계정을 프로비전하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="8f10e-105">다음 섹션에서는 Skype 룸 시스템 계정 프로비전에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="8f10e-106">Microsoft 365 및 Office 365의 선행 준비</span><span class="sxs-lookup"><span data-stu-id="8f10e-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="8f10e-107">온라인 테넌트는 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="8f10e-108">Microsoft 365 또는 Office 365 요금제에는 비즈니스용 Skype Online 계획 2 또는 Office 365 E1, E3 또는 E5가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="8f10e-109">비즈니스용 Skype Online 계획에 대한 자세한 내용은 비즈니스용 [Skype Online 서비스 설명을 참조하세요.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="8f10e-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="8f10e-110">테넌트에 비즈니스용 Skype의 회의 기능이 활성화되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="8f10e-111">테넌트에서 Exchange Online을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="8f10e-112">테넌트 원격 관리자에게는 다음 PowerShell 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="8f10e-113">Exchange 원격 PowerShell 액세스</span><span class="sxs-lookup"><span data-stu-id="8f10e-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="8f10e-114">비즈니스용 Skype Online 원격 PowerShell 액세스</span><span class="sxs-lookup"><span data-stu-id="8f10e-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="8f10e-115">Windows Azure Microsoft 365 또는 Office 365 디렉터리 Windows PowerShell 액세스하기 위한 Active Directory 모듈 구성</span><span class="sxs-lookup"><span data-stu-id="8f10e-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="8f10e-116">Skype 룸 계정의 경우 다음 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="8f10e-117">Skype 모임을 사용하도록 설정하려면 비즈니스용 Skype Online 계획 2 또는 Office 365 E1 또는 E3 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="8f10e-118">전화 번호로 채팅방을 사용할 수 있도록 Enterprise Voice 기능을 사용하여 방에 자격을 부여하려면 전화 시스템 라이선스가 있는 비즈니스용 Skype Online 계획 2 또는 Office 365 E5가 필요합니다(1).</span><span class="sxs-lookup"><span data-stu-id="8f10e-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="8f10e-119">모임에서 전화 접속 기능이 필요한 경우 오디오 회의 및 전화 시스템 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="8f10e-120">모임에서 전화 접속 기능이 필요한 경우 국내 또는 국내 및 국제 통화 플랜이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="8f10e-121">계정을 리소스 사서함 계정으로 구성해야 한다고 하여 Skype 룸 계정에는 Exchange Online 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="8f10e-122">프로비저닝 개요</span><span class="sxs-lookup"><span data-stu-id="8f10e-122">Provisioning overview</span></span>

<span data-ttu-id="8f10e-123">다음 다이어그램에서는 Skype 룸 시스템 계정 프로비전 흐름에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Skype 룸 시스템 프로비전 단계](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="8f10e-125">새 회의실 식별</span><span class="sxs-lookup"><span data-stu-id="8f10e-125">Identify a new conference room</span></span>

<span data-ttu-id="8f10e-126">Exchange에 이미 계획 기능을 제공하는 리소스 공간 사서함이 있을 수 있습니다. 또는 Skype 룸 시스템 배포를 용이하게 하기 위해 리소스 사서함을 처음으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="8f10e-127">어떤 경우든 테넌트에서 사용할 방 계정을 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="8f10e-128">Exchange Online 프로비전 및 비즈니스용 Skype 프로비전 섹션에서는 두 종류의 계정에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="8f10e-129">예를 들어 다음 두 방이 있으며 이 두 방 모두에 대해 Skype 룸 시스템을 배포하고자 하는 경우를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="8f10e-130">기존 리소스 사서함 계정: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8f10e-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="8f10e-131">새 리소스 사서함 계정: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8f10e-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="8f10e-132">Exchange Online 프로비전</span><span class="sxs-lookup"><span data-stu-id="8f10e-132">Exchange Online provisioning</span></span>

<span data-ttu-id="8f10e-133">먼저 Exchange Online PowerShell에 연결 항목의 지침에 따라 [Exchange Online PowerShell에 연결합니다.](https://go.microsoft.com/fwlink/p/?LinkId=396554)</span><span class="sxs-lookup"><span data-stu-id="8f10e-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="8f10e-134">Skype 룸 시스템에 대한 기존 리소스 공간 사서함 계정을 설정하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="8f10e-135">Skype 룸 시스템에 대한 새 Exchange 리소스 사서함 계정을 만들하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="8f10e-136">이전 명령은 계정을 사용하도록 설정하여 Skype 룸 시스템 사용에 대한 새 Exchange 리소스 사서함 계정을 설정하거나 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="8f10e-137">사서함을 만들고 나면 Exchange Online PowerShell의 Set-CalendarProcessing cmdlet을 사용하여 사서함을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="8f10e-138">자세한 내용은 단일 포리스트의 단일 포리스트 배포에서 3-6단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f10e-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="8f10e-139">비즈니스용 Skype Online 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8f10e-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="8f10e-140">이제 비즈니스용 Microsoft 365 또는 비즈니스용 Skype 추가 기능 라이선스 할당 또는 제거에 설명된 바와 같이 [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 관리 포털을 사용하여 비즈니스용 Skype Online(계획 2) 또는 비즈니스용 [Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Online(계획 3) 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="8f10e-141">비즈니스용 Skype Online에 대한 라이선스를 할당한 후 로그인하고 비즈니스용 Skype 클라이언트를 사용하여 계정이 활성 상태임이 확인될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="8f10e-142">비즈니스용 Skype Online 프로비전</span><span class="sxs-lookup"><span data-stu-id="8f10e-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="8f10e-143">리소스 공간 사서함 계정을 생성하고 사용하도록 설정하고 비즈니스용 Skype Online에 대한 계정에 라이선스를 부여한 후 계정이 Exchange Online 포리스트에서 비즈니스용 Skype Online 포리스트로 동기화될 Windows Azure Active Directory 포리스트를 사용하여 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="8f10e-144">비즈니스용 Skype Online 풀에서 Skype 룸 시스템 계정을 프로비전하려면 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="8f10e-145">이러한 단계는 기존 리소스 사서함 계정 또는 새로 만든 계정(confrm1 또는 confrm2)에 대해 동일합니다. Exchange Online에서 사용하도록 설정하면 두 계정이 동일한 방식으로 비즈니스용 Skype Online과 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="8f10e-146">원격 PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="8f10e-147">비즈니스용 Skype Online 커넥터 모듈 및 Microsoft Online Services Sign-In 도우미를 다운로드하고 컴퓨터가 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="8f10e-148">자세한 내용은 [다음을 위해](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)컴퓨터 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f10e-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="8f10e-149">비즈니스용 Skype에 대해 Skype 룸 시스템 계정을 사용하도록 설정하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="8f10e-150">다음 명령을 사용하여 이 속성을 반환하면 비즈니스용 Skype 사용자가 있는 등록자 주소를 기존 계정 중 하나에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="8f10e-151">Skype 룸 시스템 계정에는 MFA(Multi-Factor Authentication)가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="8f10e-152">암호 만료</span><span class="sxs-lookup"><span data-stu-id="8f10e-152">Password expiration</span></span>

<span data-ttu-id="8f10e-153">Microsoft 365 또는 Office 365에서 다른 암호 만료 정책을 구성하지 않는 한 모든 사용자 계정에 대한 기본 암호 만료 정책은 90일입니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-153">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="8f10e-154">Skype 채팅방 시스템 계정의 경우 다음 단계에 따라 암호 사용 기간이 만료되지 않는 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="8f10e-155">테넌트 Windows Azure 관리자 자격 증명을 사용하여 Active Directory 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="8f10e-156">다음 명령을 사용하여 이전에 만든 Skype 채팅방 계정의 암호 사용 기간이 만료되지 않는 설정 설정</span><span class="sxs-lookup"><span data-stu-id="8f10e-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="8f10e-157">자세한 내용은 [다음을 위해](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)컴퓨터 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f10e-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="8f10e-158">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8f10e-158">Validate</span></span>

<span data-ttu-id="8f10e-159">유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용하여 만든 계정에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f10e-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

