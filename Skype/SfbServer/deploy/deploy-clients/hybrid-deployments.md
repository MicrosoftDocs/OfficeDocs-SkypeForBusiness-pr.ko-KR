---
title: Skype 룸 시스템 하이브리드 배포
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 이 항목을 읽고 하이브리드 환경에서 Skype 룸 시스템을 배포하는 방법을 배워 읽습니다.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805898"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="ecbf2-103">Skype 룸 시스템 하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="ecbf2-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="ecbf2-104">이 항목을 읽고 하이브리드 환경에서 Skype 룸 시스템을 배포하는 방법을 배워 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="ecbf2-105">하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="ecbf2-105">Hybrid deployments</span></span>

<span data-ttu-id="ecbf2-106">토폴로지에 비즈니스용 Skype 서버 및 Exchange Online이 있으며 Exchange Online에서 Skype 룸 시스템 리소스 사서함을 호스트하려는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="ecbf2-107">이 섹션에서는 Exchange Online과 Exchange Online을 모두 배포한 하이브리드 시나리오에 Exchange Server 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="ecbf2-108">예를 들어, LyncSample.com 도메인에 대해 LyncSample.ccstp.net 도메인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="ecbf2-109">Exchange Online 프로비전에 설명된 LyncSample.ccsctp.net Exchange 관리 셸에 연결하여 Exchange 관리 센터(LyncSample.ccsctp.net)에서 리소스 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="ecbf2-110">로그인할 때 OWA 연결을 lrstest5@LyncSample.ccsctp.net 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="ecbf2-111">Microsoft 365 또는 Office 365 Exchange 관리 센터에서 전자 메일 주소(lrstest5@LyncSample.com 도메인)를 추가하고 회신 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="ecbf2-112">프레미스 Active Directory 사용자 lrstest5@LyncSample.com 전자 메일 주소를 lrstest5@LyncSample.com 주소로 설정하고 대상 주소를 lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="ecbf2-113">디렉터리 동기화를 트리거하고 동기화가 완료된 후 사용자가 AAD에서 병합하는지와 Microsoft 365 또는 Office 365 Exchange 관리 센터의 받는 사람 리소스에서 속성을 변경할 수 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="ecbf2-114">다음을 사용하여 OWA 연결을 lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="ecbf2-115">(앞에서 온라인 도메인을 사용하여 OWA 연결을 확인했습니다.)</span><span class="sxs-lookup"><span data-stu-id="ecbf2-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="ecbf2-116">사서함을 만들고 나면 Exchange Online 관리 Set-CalendarProcessing 사서함을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="ecbf2-117">자세한 내용은 단일 포리스트 On-prem 배포에서 3-6단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="ecbf2-118">Exchange Server 및 Exchange Online이 있는 하이브리드 환경인 경우 Exchange 관리 셸로 이동하여 Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room으로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="ecbf2-119">그런 다음 디렉터리 동기화를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="ecbf2-120">Exchange Online에서 Skype 채팅방 시스템 사서함을 호스트하려는 경우 이러한 Exchange 관리 셸 단계가 필요하지 않습니다. 6단계로 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="ecbf2-121">비즈니스용 Skype 관리 셸에서 다음 cmdlet을 실행하여 비즈니스용 Skype에 대해 Skype 룸 시스템 계정을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ecbf2-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="ecbf2-122">위의 시나리오에서 비즈니스용 Skype 서버 대신 비즈니스용 Skype Online이 있는 경우 Exchange 리소스 사서함을 프로비전한 후 비즈니스용 Skype Online 프로비전에 설명된 대로 비즈니스용 Skype 계정을 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="ecbf2-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

