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
description: 이 항목에서는 Office 365에서 Skype 대화방 시스템 계정을 구축 하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 33c3acf2f0fffc69da55468e8c16902ec7fa4f88
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768751"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="45ce0-103">Office 365에서 Skype 대화방 시스템 계정 프로 비전</span><span class="sxs-lookup"><span data-stu-id="45ce0-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="45ce0-104">이 항목에서는 Office 365에서 Skype 대화방 시스템 계정을 구축 하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="45ce0-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="45ce0-105">다음 섹션에서는 Office 365 테 넌 트에 대 한 Skype 대화방 시스템 계정 프로비저닝에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="45ce0-106">Office 365 필수 조건</span><span class="sxs-lookup"><span data-stu-id="45ce0-106">Office 365 prerequisites</span></span>

<span data-ttu-id="45ce0-107">온라인 테 넌 트가 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="45ce0-108">Office 365 요금제에는 비즈니스용 Skype Online 요금제 2 또는 Office 365 E1, E3 또는 E5가 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="45ce0-109">비즈니스용 Skype Online 요금제에 대 한 자세한 내용은 [비즈니스용 Skype Online 서비스 설명을](https://technet.microsoft.com/library/jj822172.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce0-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="45ce0-110">테 넌 트에 비즈니스용 Skype의 회의 기능이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="45ce0-111">테 넌 트가 Exchange Online을 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="45ce0-112">테 넌 트 원격 관리자에 게는 다음과 같은 PowerShell 액세스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="45ce0-113">Exchange 원격 PowerShell 액세스</span><span class="sxs-lookup"><span data-stu-id="45ce0-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="45ce0-114">비즈니스용 Skype Online 원격 PowerShell 액세스</span><span class="sxs-lookup"><span data-stu-id="45ce0-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="45ce0-115">Windows PowerShell 용 windows Azure Active Directory 모듈을 사용 하 여 Office 365 디렉터리 액세스 액세스</span><span class="sxs-lookup"><span data-stu-id="45ce0-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="45ce0-116">Skype 채팅방 계정의 경우 다음 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="45ce0-117">Skype 모임을 활성화 하려면 비즈니스용 Skype Online 계획 2 또는 Office 365 E1 또는 E3 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="45ce0-118">전화 번호를 사용 하 여 공간을 사용할 수 있도록 엔터프라이즈 음성 기능을 사용 하 여 공간을 entitle 전화 시스템 라이선스가 있는 비즈니스용 Skype Online 계획 2 또는 Office 365 E5가 필요 합니다 (1).</span><span class="sxs-lookup"><span data-stu-id="45ce0-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="45ce0-119">모임에서 전화 접속 기능이 필요한 경우에는 오디오 회의 및 전화 시스템 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="45ce0-120">모임에서 전화 접속 기능이 필요한 경우 국내 또는 국내 및 국제 통화 요금제가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="45ce0-121">계정을 리소스 사서함 계정으로 구성 해야 하기 때문에 Skype 대화방 계정에 Exchange Online 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="45ce0-122">프로 비전 개요</span><span class="sxs-lookup"><span data-stu-id="45ce0-122">Provisioning overview</span></span>

<span data-ttu-id="45ce0-123">다음 다이어그램은 Office 365의 Skype 대화방 시스템 계정 프로비저닝 흐름에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 용 Skype 채팅방 시스템 프로비저닝 단계](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="45ce0-125">새 회의실 식별</span><span class="sxs-lookup"><span data-stu-id="45ce0-125">Identify a new conference room</span></span>

<span data-ttu-id="45ce0-126">Exchange에 일정 기능을 제공 하는 리소스 공간 사서함이 이미 있거나 Skype 대화방 시스템 배포를 용이 하 게 하기 위해 처음으로 리소스 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="45ce0-127">어떤 경우 든 테 넌 트에서 사용할 룸 계정을 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="45ce0-128">Exchange Online 제공 및 비즈니스용 Skype 프로 비전 섹션에서는 두 가지 계정에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="45ce0-129">예를 들어 다음 두 채팅방을 사용 하 고 있으며 두 가지 모두에 대해 Skype 채팅방 시스템을 배포 하 고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="45ce0-130">기존 리소스 사서함 계정: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="45ce0-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="45ce0-131">새 리소스 사서함 계정: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="45ce0-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="45ce0-132">Exchange Online 프로비저닝</span><span class="sxs-lookup"><span data-stu-id="45ce0-132">Exchange Online provisioning</span></span>

<span data-ttu-id="45ce0-133">먼저, [Exchange Online powershell에 연결](https://go.microsoft.com/fwlink/p/?LinkId=396554)항목의 지침에 따라 Exchange online powershell에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="45ce0-134">Skype 채팅방 시스템의 기존 리소스 공간 사서함 계정을 설정 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="45ce0-135">Skype 대화방 시스템용 새 Exchange 리소스 사서함 계정을 만들려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="45ce0-136">이전 명령은 계정을 사용 하 여 Skype 룸 시스템 사용에 대 한 새 Exchange 리소스 사서함 계정을 설정 하거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="45ce0-137">사서함을 만든 후 Exchange Online PowerShell의 집합-CalendarProcessing cmdlet을 사용 하 여 사서함을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="45ce0-138">자세한 내용은 단일 포리스트 온-프레미스 배포의 3 ~ 6 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce0-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="45ce0-139">비즈니스용 Skype Online 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="45ce0-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="45ce0-140">이제 비즈니스용 [office 365에 라이선스 할당 또는 제거](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 또는 비즈니스용 [skype 추가 기능 라이선스](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)에 설명 된 대로 Office 365 관리 포털을 사용 하 여 비즈니스용 skype online (계획 2) 또는 비즈니스용 skype online (계획 3) 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="45ce0-141">비즈니스용 Skype Online에 대 한 라이선스를 할당 한 후에는 로그인 하 고 비즈니스용 Skype 클라이언트를 사용 하 여 계정이 활성 상태 인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="45ce0-142">비즈니스용 Skype Online 프로 비전</span><span class="sxs-lookup"><span data-stu-id="45ce0-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="45ce0-143">이전에 표시 된 대로 리소스 공간 사서함 계정을 생성 하 고 사용 하도록 설정 하 고 비즈니스용 Skype Online에 대 한 계정을 사용 하도록 허가 받은 후에는이 계정이 Exchange Online 포리스트에서 비즈니스용 Skype Online 포리스트와 동기화 합니다. Windows Azure Active Directory 포리스트.</span><span class="sxs-lookup"><span data-stu-id="45ce0-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="45ce0-144">다음 단계는 비즈니스용 Skype Online 풀에서 Skype 채팅방 시스템 계정을 구축 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="45ce0-145">이러한 단계는 Exchange Online에서 사용 하도록 설정 된 경우와 동일한 방식으로 기존 리소스 사서함 계정 또는 새로 만든 계정 (confrm1 또는 confrm2) 모두에 대해 동일 합니다. 이러한 두 계정은 모두 비즈니스용 Skype Online에 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="45ce0-146">원격 PowerShell 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="45ce0-147">비즈니스용 Skype Online 커넥터 모듈 및 Microsoft Online Services 로그인 도우미를 다운로드 하 고 컴퓨터가 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="45ce0-148">자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce0-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="45ce0-149">비즈니스용 Skype에 대해 Skype 대화방 시스템 계정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="45ce0-150">다음 명령을 사용 하 여이 속성을 반환 하 여 기존 계정 중 하나에서 비즈니스용 Skype 사용자가 속한 RegistrarPool 주소를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="45ce0-151">Skype 대화방 시스템 계정에는 MFA (다단계 인증)가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="45ce0-152">비밀 번호 만료</span><span class="sxs-lookup"><span data-stu-id="45ce0-152">Password expiration</span></span>

<span data-ttu-id="45ce0-153">Office 365에서 다른 암호 만료 정책을 구성 하지 않는 한 모든 사용자 계정에 대 한 기본 암호 만료 정책은 90 일입니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="45ce0-154">Skype 대화방 시스템 계정의 경우 다음 단계에 따라 암호 사용 기간 제한 없음 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="45ce0-155">테 넌 트 전역 관리자 자격 증명을 사용 하 여 Windows Azure Active Directory 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="45ce0-156">다음 명령을 사용 하 여 이전에 만든 Skype 채팅방 시스템 룸 계정에 대 한 암호 사용 기간 제한 없음 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="45ce0-157">자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce0-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="45ce0-158">Validate</span><span class="sxs-lookup"><span data-stu-id="45ce0-158">Validate</span></span>

<span data-ttu-id="45ce0-159">유효성 검사를 위해 Skype for Business 클라이언트를 사용 하 여 만든 계정에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce0-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

