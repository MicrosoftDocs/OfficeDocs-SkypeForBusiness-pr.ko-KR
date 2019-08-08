---
title: 비즈니스용 Skype 서버를 사용 하 여 Microsoft 팀 회의실 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 비즈니스용 Skype 서버를 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 95b8240d67de801bd63983b37abd92180511b389
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243215"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="359c9-103">비즈니스용 Skype 서버를 사용 하 여 Microsoft 팀 회의실 배포</span><span class="sxs-lookup"><span data-stu-id="359c9-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="359c9-104">이 항목에서는 단일 포리스트, 온-프레미스 배포를 사용 하는 경우 Microsoft 팀 대화방에 대 한 디바이스 계정을 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="359c9-105">Exchange 2013 SP1 이상 및 비즈니스용 Skype Server 2015 이상에서 단일 포리스트, 온-프레미스 배포를 사용 하는 경우 제공 된 Windows PowerShell 스크립트를 사용 하 여 디바이스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="359c9-106">다중 포리스트 배포를 사용 하는 경우 동일한 결과를 생성 하는 동일한 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="359c9-107">이 섹션에서는 이러한 cmdlet에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="359c9-108">Microsoft 팀 회의실 배포를 시작 하기 전에 연결 된 cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="359c9-109">$StrExchangeServer는 Exchange server의 FQDN (정규화 된 도메인 이름)이 고 $strLyncFQDN는 비즈니스용 Skype 서버 배포의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="359c9-110">세션을 설정한 후 새 사서함을 만들고이를 RoomMailboxAccount 사용 하도록 설정 하거나 기존 회의실 사서함에 대 한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="359c9-111">이렇게 하면 계정이 Microsoft 팀 방에 대 한 인증을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="359c9-112">기존 리소스 사서함을 변경 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="359c9-113">새 리소스 사서함을 만드는 경우:</span><span class="sxs-lookup"><span data-stu-id="359c9-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="359c9-114">디바이스 계정에서 다양 한 Exchange 속성을 설정 하 여 사용자의 모임 환경을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="359c9-115">Exchange 속성 섹션에서 설정 해야 하는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="359c9-116">암호가 만료 되지 않도록 결정 한 경우에는 Windows PowerShell cmdlet을 사용 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="359c9-117">자세한 내용은 암호 관리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="359c9-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="359c9-118">Active Directory에서 계정을 사용 하도록 설정 하 여 Microsoft 팀 대화방에 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="359c9-119">비즈니스용 Skype 서버 풀에서 Microsoft 팀 회의실 Active Directory 계정을 사용 하도록 설정 하 여 비즈니스용 Skype 서버에서 디바이스 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="359c9-120">프로젝트에 대 한 SIP (세션 시작 프로토콜) 주소 및 도메인 컨트롤러를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="359c9-121">**).**</span><span class="sxs-lookup"><span data-stu-id="359c9-121">**Optional.**</span></span> <span data-ttu-id="359c9-122">또한 Microsoft 팀 대화방에서 계정에 엔터프라이즈 음성을 사용 하도록 설정 하 여 일반 PSTN (교환 전화 네트워크) 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="359c9-123">엔터프라이즈 음성은 Microsoft 팀 방에 대 한 요구 사항이 아니지만 Microsoft 팀원에 게 PSTN 전화 접속 기능을 설정 하려면 다음 방법을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="359c9-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="359c9-124">또한 제공 된 도메인 컨트롤러 및 전화 번호 예제를 자신의 정보로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-124">Again, you'll need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="359c9-125">매개 변수 값 $true 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="359c9-125">The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="359c9-126">샘플: Exchange 및 비즈니스용 Skype Server (온-프레미스)의 채팅방 계정 설정</span><span class="sxs-lookup"><span data-stu-id="359c9-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a><span data-ttu-id="359c9-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="359c9-127">See also</span></span>

[<span data-ttu-id="359c9-128">Microsoft 팀 대화방 계정 구성</span><span class="sxs-lookup"><span data-stu-id="359c9-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="359c9-129">Microsoft 팀 회의실 계획</span><span class="sxs-lookup"><span data-stu-id="359c9-129">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="359c9-130">Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="359c9-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="359c9-131">Microsoft 팀 대화방 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="359c9-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="359c9-132">Microsoft 팀 대화방 관리</span><span class="sxs-lookup"><span data-stu-id="359c9-132">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
