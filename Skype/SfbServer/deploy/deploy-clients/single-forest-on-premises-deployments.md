---
title: Skype 룸 시스템 단일 포리스트-프레미스 배포
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
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 이 항목을 읽고 단일 포리스트에 Skype 룸 시스템을 배포하는 방법을 배워야 합니다.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820758"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="77e7f-103">Skype 룸 시스템 단일 포리스트-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="77e7f-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="77e7f-104">이 항목을 읽고 단일 포리스트에 Skype 룸 시스템을 배포하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="77e7f-105">이 섹션에서는 단일 포리스트의 Exchange Server 배포에서 호스팅되는 비즈니스용 Skype 서버에서 Skype 채팅방 시스템 계정을 프로비전하는 단계를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="77e7f-106">단일 포리스트 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="77e7f-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="77e7f-107">회의 공간에 대한 리소스 사서함 계정이 이미 있는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="77e7f-108">그렇지 않으면 새 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="77e7f-109">PowerShell(Exchange 관리 셸)을 사용할 수도 Exchange 관리 콘솔 사서함 계정을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="77e7f-110">Skype 룸 시스템에는 새(이전 사서함 삭제 및 다시 만들기) 리소스 사서함을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="77e7f-111">Outlook 클라이언트를 사용하여 사서함 데이터를 삭제하기 전에 백업한 다음 다시 만든 사서함으로 내보낼 수 있습니다(자세한 내용은 메시지, 일정, 작업 및 연락처 내보내기 또는 백업 참조).</span><span class="sxs-lookup"><span data-stu-id="77e7f-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="77e7f-112">사서함을 삭제하여 손실된 모임을 복원하려면 삭제된 사서함 연결 또는 [복원을 참조합니다.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="77e7f-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="77e7f-113">기존 리소스 사서함 계정(예: LRS-01)을 사용하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="77e7f-114">다음 Exchange 관리 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="77e7f-115">새 사서함을 만들 계획인 경우 단일 포리스트의 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="77e7f-116">위의 예에서는 Active Directory에 사용 가능한 사용자 계정과 회의실 사서함을 만들며, 이 예에서는 Exchange 조직에 있는 회의실을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="77e7f-117">RoomMailboxPassword 매개 변수는 사용자 계정에 대한 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="77e7f-118">모임을 수락/거부하여 충돌을 자동으로 해결하도록 계정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="77e7f-119">Exchange의 Skype 회의실 시스템이 탑재된 회의실 계정은 개인이 관리할 수 있지만, 개인이 모임을 수락할 때까지 Skype 룸 시스템 홈 화면 일정에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="77e7f-120">사용 가능한 전체 명령 집합은 Set-CalendarProcessing을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77e7f-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="77e7f-121">모임 이끌이가 Outlook에서 온라인 비즈니스용 Skype 모임으로 만들 수 있도록 미리 알리기 위해 다음 명령을 실행하여 새 계정에 대한 메일 설명을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="77e7f-122">다음 명령을 사용하여 지역화된 문자열을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="77e7f-123">조직에서 필요한 경우 사용자 지정 번역을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="77e7f-124">선택 사항: 사용자에게 비즈니스용 Skype 회의실에 대한 정보와 모임을 예약하고 참가할 때 예상할 수 있는 정보를 제공하는 모임 수락 텍스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="77e7f-125">Active Directory에서 리소스 사서함 계정 확인</span><span class="sxs-lookup"><span data-stu-id="77e7f-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="77e7f-126">위의 1단계에서 Exchange에서 만든 회의실 사서함 계정은 Active Directory에서 비활성화된 사용자 개체일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="77e7f-127">계정을 Active Directory에서 사용하지 않도록 설정한 경우 Skype 채팅방 시스템은 Kerberos/NTLM 인증을 사용하여 로그인하거나 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="77e7f-128">Skype 채팅방 시스템 클라이언트는 일정 설정을 검색하기 위해 Exchange 웹 서비스에 대해 인증할 수 있어야 하며 화이트보드 콘텐츠가 있는 전자 메일을 보낼 수도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="77e7f-129">따라서 계정을 사용하지 않도록 설정한 경우 다음을 수행하여 Active Directory에서 이 계정을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="77e7f-130">Active Directory에서 다음 명령을 실행하여 계정 로그온을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="77e7f-131">이 명령을 실행하면 현재 암호를 입력하라는 메시지가 표시되고 확인을 위해 암호를 두 번 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="77e7f-132">암호를 설정한 후 다음 명령을 실행하여 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="77e7f-133">비즈니스용 Skype에 대해 Skype 룸 시스템 계정 사용</span><span class="sxs-lookup"><span data-stu-id="77e7f-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="77e7f-134">이 섹션에서는 Skype 룸 시스템에서 구성되는 회의실 계정에 대해 비즈니스용 Skype를 사용하도록 설정하는 데 필요한 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="77e7f-135">회의 회의실에 대한 리소스 사서함 계정을 만든 후 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서비스에 대해 Skype 룸 시스템 계정을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77e7f-136">다음 절차에서는 Active Directory에서 Skype 룸 시스템 계정을 사용하도록 설정했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="77e7f-137">다음 명령을 실행하여 비즈니스용 Skype 서버 풀에서 Skype 룸 시스템 계정을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="77e7f-138">선택 사항: 이 계정을 사용하여 PSTN 전화 통화를 걸고 받을 수 있도록 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="77e7f-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="77e7f-139">Enterprise Voice 채팅방 시스템에는 이 기능이 필요하지 않지만 이 기능을 Enterprise Voice Skype 채팅방 시스템 클라이언트는 PSTN 전화 걸기 기능을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="77e7f-140">Skype 회의실 Enterprise Voice 계정을 사용하도록 설정하는 경우 조직에 적합한 제한된 음성 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="77e7f-141">비즈니스용 Skype 회의실이 공개적으로 사용 가능한 리소스인 경우 누구나 이 리소스를 사용하여 예약된 모임 또는 애드업으로 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="77e7f-142">모임에 참가한 후 어떤 번호로도 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="77e7f-143">비즈니스용 Skype 서버에서 전화 접속 기능은 사용자의 음성 정책(이 경우 모임에 참가하는 데 사용되는 Skype 채팅방 시스템 계정)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="77e7f-144">이전 버전의 Lync Server에서는 이끌이의 음성 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="77e7f-145">따라서 이전 버전의 Lync Server 사용자가 회의실을 예약하고 Skype 회의실 계정을 초대하는 경우 이끌이가 해당 번호로 전화를 걸 수 있는 한 누구나 비즈니스용 Skype 회의실을 사용하여 모임에 참가하고 모든 국가/지역 또는 국제 전화 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e7f-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

