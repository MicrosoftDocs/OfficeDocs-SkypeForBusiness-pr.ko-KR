---
title: Microsoft Teams 룸 비즈니스용 Skype 서버
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 비즈니스용 Skype 서버.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662263"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="cdabe-103">Microsoft Teams 룸 비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="cdabe-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="cdabe-104">이 항목에서는 단일 포리스트, Microsoft Teams 룸 배포할 때 디바이스 계정을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="cdabe-105">2013 SP1 이상 및 2013 SP1 이상 및 2015년 비즈니스용 Skype 서버 있는 단일 포리스트, Windows PowerShell 배포가 있는 경우 디바이스 계정을 만들 수 있습니다. Exchange</span><span class="sxs-lookup"><span data-stu-id="cdabe-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="cdabe-106">다중 포리스트 배포를 사용하는 경우 동일한 결과를 생성하는 동등한 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="cdabe-107">이러한 cmdlet은 이 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="cdabe-108">배포를 시작하기 전에 Microsoft Teams 룸 cmdlet을 실행할 수 있는 올바른 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="cdabe-109">$strExchangeServer 서버의 FQDN(완전 자격을 갖춘 도메인 이름)은 Exchange $strLyncFQDN 배포의 FQD 비즈니스용 Skype 서버N입니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="cdabe-110">세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 방 사서함에 대한 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="cdabe-111">이렇게 하면 계정이 인증할 수 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="cdabe-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="cdabe-112">기존 리소스 사서함을 변경하는 경우:</span><span class="sxs-lookup"><span data-stu-id="cdabe-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="cdabe-113">새 리소스 사서함을 만드는 경우:</span><span class="sxs-lookup"><span data-stu-id="cdabe-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="cdabe-114">디바이스 계정에 다양한 Exchange 속성을 설정하여 사용자에 대한 모임 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="cdabe-115">속성 섹션에서 어떤 속성을 설정해야 Exchange 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="cdabe-116">암호가 만료되지 않는 경우 cmdlet을 사용하여 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="cdabe-117">자세한 내용은 암호 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdabe-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="cdabe-118">Active Directory에서 계정을 사용하도록 설정하면 계정이 인증되어 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="cdabe-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="cdabe-119">다음 풀에서 비즈니스용 Skype 서버 Active Directory 계정을 Microsoft Teams 룸 사용하여 디바이스 계정을 비즈니스용 Skype 서버 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="cdabe-120">SIP(세션 시작 프로토콜) 주소 및 도메인 컨트롤러를 사용하여 Project</span><span class="sxs-lookup"><span data-stu-id="cdabe-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="cdabe-121">**선택 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="cdabe-121">**Optional.**</span></span> <span data-ttu-id="cdabe-122">또한 계정에 대한 Microsoft Teams 룸 사용하도록 설정하여 PSTN(공용 전환 전화 네트워크) 전화 통화를 Enterprise Voice 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="cdabe-123">Enterprise Voice 클라이언트에 대한 PSTN Microsoft Teams 룸 필요는 없지만 클라이언트에 대한 PSTN Microsoft Teams 룸하려면 다음을 사용하도록 설정하는 방법에 대해 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="cdabe-124">또한 제공된 도메인 컨트롤러 및 전화 번호 예제를 사용자만의 정보로 바야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-124">Again, you'll need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="cdabe-125">매개 변수 $true 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdabe-125">The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="cdabe-126">샘플: Exchange 및 비즈니스용 Skype 서버 룸 계정 설정</span><span class="sxs-lookup"><span data-stu-id="cdabe-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="cdabe-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cdabe-127">Related topics</span></span>

[<span data-ttu-id="cdabe-128">Microsoft Teams 룸</span><span class="sxs-lookup"><span data-stu-id="cdabe-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="cdabe-129">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="cdabe-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="cdabe-130">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="cdabe-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="cdabe-131">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="cdabe-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="cdabe-132">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="cdabe-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
