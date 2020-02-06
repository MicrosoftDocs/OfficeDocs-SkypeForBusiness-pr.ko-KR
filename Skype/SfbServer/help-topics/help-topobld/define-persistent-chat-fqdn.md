---
title: 영구 채팅 FQDN 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 새 영구 채팅 풀 정의 마법사를 사용 하 여 새 영구 채팅 서버 또는 영구 채팅 서버 풀을 만듭니다. 다중 컴퓨터 풀 또는 단일 컴퓨터 풀 중 하나를 선택합니다. 단일 컴퓨터 풀을 선택했는데 나중에 다중 컴퓨터 풀이 필요한 경우 단일 컴퓨터 풀을 제거하고 다중 컴퓨터 풀을 정의해야 합니다.
ms.openlocfilehash: 12b5a648de211086d33624afad56ce069493b135
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820200"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="605a4-105">영구 채팅 FQDN 정의</span><span class="sxs-lookup"><span data-stu-id="605a4-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="605a4-106">**새 영구 채팅 풀 정의** 마법사를 사용 하 여 새 영구 채팅 서버 또는 영구 채팅 서버 풀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="605a4-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="605a4-107">**다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀** 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="605a4-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="605a4-108">단일 컴퓨터 풀을 선택했는데 나중에 다중 컴퓨터 풀이 필요한 경우 단일 컴퓨터 풀을 제거하고 다중 컴퓨터 풀을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="605a4-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="605a4-109">또한 영구 채팅 서버 또는 영구 채팅 서버 풀에 대해 **풀 FQDN** 을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="605a4-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="605a4-110">단일 컴퓨터 풀에 대한 풀 FQDN(정규화된 도메인 이름)은 단일 서버 풀을 구성하는 컴퓨터의 FQDN과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="605a4-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="605a4-111">다중 컴퓨터 풀의 경우 FQDN은 이 다중 컴퓨터 풀을 나타내도록 선택하는 이름이어야 하며, 호스트 A(IPv6을 사용 중인 경우 AAAA) 레코드에 의해 DNS에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="605a4-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="605a4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="605a4-112">See also</span></span>

[<span data-ttu-id="605a4-113">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="605a4-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="605a4-114">비즈니스용 Skype Server 2015 토폴로지에 영구 채팅 서버 추가</span><span class="sxs-lookup"><span data-stu-id="605a4-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
