---
title: Skype 룸 시스템 및 비즈니스용 Skype 페더러타트 파트너
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
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 이 항목을 읽고 비즈니스용 Skype 페더러타 파트너용 Skype 채팅방 시스템을 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820808"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="58246-103">Skype 룸 시스템 및 비즈니스용 Skype 페더러타트 파트너</span><span class="sxs-lookup"><span data-stu-id="58246-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="58246-104">이 항목을 읽고 비즈니스용 Skype 페더러타 파트너용 Skype 채팅방 시스템을 설정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58246-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="58246-105">Skype 룸 시스템 및 비즈니스용 Skype 페더러타트 파트너</span><span class="sxs-lookup"><span data-stu-id="58246-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="58246-106">Skype 룸 시스템은 일정 모임 요청에서 비즈니스용 Skype 모임 참가 링크를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58246-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="58246-107">참가 링크는 일반적으로 모임 요청 본문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58246-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="58246-108">그러나 Skype 채팅방 시스템은 이 링크가 메시지의 MAPI 속성에 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58246-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="58246-109">이 모임 요청이 원격 조직(비즈니스용 Skype 페더링 파트너)에게 전송될 경우 기본적으로 원격 조직의 Skype 룸 시스템은 일정에 모임 참가 링크를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58246-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="58246-110">실제로 원격 조직의 모든 Outlook 사용자는 일정 항목을 마우스 오른쪽 단추로 클릭하거나 모임 미리 알림 내에서 비즈니스용 Skype 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58246-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="58246-111">모임 초대를 열고 메시지 본문에서 비즈니스용 Skype 모임 참가를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58246-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="58246-112">이 제한의 이유는 Outlook과 Microsoft Exchange가 인터넷을 통해 메시지를 보내는 데 사용할 정보를 패키지하는 특수한 방법을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58246-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="58246-113">TNEF(Transport Neutral Encapsulation Format)라고 하는 이 메서드는 Exchange 조직에서 외부로 보낸 메시지에 대해 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58246-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="58246-114">모임 참가 링크가 원격 Skype 룸 시스템에 표시하려면 보내는 조직에서 다음 명령을 사용하여 TNEF를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58246-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="58246-115">원격 조직에 대해 TNEF를 사용하도록 설정하면 인터넷을 통해 조직으로 전송된 모든 메시지가 TNEF 형식의 첨부 파일로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="58246-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="58246-116">TNEF를 사용하도록 설정하면 비즈니스용 Skype 모임 요청이 비즈니스용 Skype 페더러타트 파트너로 전송되면 Skype 룸 시스템에서 비즈니스용 Skype 모임 참가를 렌더링할 수 있으며 원격 사용자는 비즈니스용 Skype 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58246-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
