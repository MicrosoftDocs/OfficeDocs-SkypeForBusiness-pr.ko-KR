---
title: Skype 대화방 시스템 하이브리드 배포
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 하이브리드 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219678"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="29aa0-103">Skype 대화방 시스템 하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="29aa0-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="29aa0-104">하이브리드 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="29aa0-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="29aa0-105">하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="29aa0-105">Hybrid deployments</span></span>

<span data-ttu-id="29aa0-106">토폴로지에 비즈니스용 Skype 서버 및 Exchange Online이 있고 Exchange Online에서 Skype 대화방 시스템 리소스 사서함을 호스트 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="29aa0-107">이 섹션에서는 Exchange Online 및 Exchange Server가 모두 배포 된 하이브리드 시나리오에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="29aa0-108">설명을 위해 온라인 도메인에 대해 온-프레미스 도메인 및 LyncSample.ccstp.net에 대해 LyncSample.com를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="29aa0-109">Exchange Online Management에 설명 된 대로 exchange Online 관리 셸에 연결 하 여 LyncSample.ccsctp.net (Exchange 관리 센터)에서 리소스 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="29aa0-110">Lrstest5@LyncSample.ccsctp.net을 사용 하 여 로그인 할 때 OWA 연결을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="29aa0-111">Microsoft 365 또는 Office 365 Exchange 관리 센터에서 전자 메일 주소 lrstest5@LyncSample.com (프레미스 도메인)을 추가 하 고이를 회신 주소로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="29aa0-112">온-프레미스 Active Directory 사용자 lrstest5@LyncSample.com를 만들고, 전자 메일 주소를 lrstest5@LyncSample.com으로 설정 하 고, 대상 주소를 lrstest5@LyncSample.com로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="29aa0-113">디렉터리 동기화를 트리거하고 동기화가 완료 되 면 사용자가 AAD에서 병합 되 고 Microsoft 365 또는 Office 365 Exchange 관리 센터에서 받는 사람의 리소스에서 속성을 변경할 수 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="29aa0-114">Lrstest5@LyncSample.com을 사용 하 여 OWA 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="29aa0-115">(이전에는 온라인 도메인을 사용 하 여 OWA 연결을 확인 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="29aa0-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="29aa0-116">사서함을 만든 후에는 Exchange Online 관리 셸에서 설정-CalendarProcessing을 사용 하 여 사서함을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="29aa0-117">자세한 내용은 단일 포리스트 온-프레미스 배포의 3 ~ 6 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29aa0-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="29aa0-118">Exchange Server 및 Exchange Online을 사용 하는 하이브리드 환경이 있는 경우 Exchange 관리 셸 및 Enable-New-remotemailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net Room으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="29aa0-119">그런 다음 디렉터리 동기화를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="29aa0-120">Exchange Online에서 Skype 대화방 시스템 사서함을 호스트 하려면 이러한 Exchange 관리 셸 단계가 필요 하지 않으며 6 단계를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="29aa0-121">비즈니스용 skype 관리 셸에서 다음 cmdlet을 실행 하 여 비즈니스용 skype에 대해 Skype 대화방 시스템 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="29aa0-122">위의 시나리오에서 비즈니스용 Skype 서버 대신 비즈니스용 Skype Online이 있는 경우 Exchange 리소스 사서함을 구축한 후 비즈니스용 Skype Online 프로 비전에 설명 된 대로 비즈니스용 Skype 계정을 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="29aa0-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

