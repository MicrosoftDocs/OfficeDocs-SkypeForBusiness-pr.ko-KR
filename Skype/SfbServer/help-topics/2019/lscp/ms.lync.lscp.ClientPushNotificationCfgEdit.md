---
title: 모바일 클라이언트 푸시 알림 구성 만들기 또는 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: 푸시 알림 및 PNCH(푸시 알림 클리어링 하우스)는 모바일 기능의 두 가지 주요 부분입니다. 푸시 알림은 메시지가 PNCH로 전송되는 프로세스입니다. 메시지는 모바일 클라이언트로 배달될 수 있거나 제한 시간이 만료될 때까지 PNCH에 보관됩니다.
ms.openlocfilehash: 3c72c5b123a906d74cfeb0a1fef5c1e765fe030c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808748"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="67103-105">모바일 클라이언트: 푸시 알림 구성 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="67103-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="67103-106">푸시 알림 및 PNCH(푸시 알림 클리어링 하우스)는 모바일 기능의 두 가지 주요 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="67103-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="67103-107">푸시 알림은 메시지가 PNCH로 전송되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="67103-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="67103-108">메시지는 모바일 클라이언트로 배달될 수 있거나 제한 시간이 만료될 때까지 PNCH에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="67103-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="67103-109">기간은 푸시 알림 클리어링 하우스에서 설정되며, 배포 관리자 또는 사용자가 구성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67103-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="67103-110">푸시 알림을 사용하도록 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67103-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="67103-111">**범위:** 이 정책의 범위를 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="67103-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="67103-112">이 배포의 모든 사용자에게 적용되는 **Global** 또는 지정된 사이트의 홈 서버에 할당된 사용자만 적용되는 **사이트일** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67103-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="67103-113">한 정책 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67103-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="67103-114">정책 우선 순위는 사용자 정책(가장 큰 영향)이 사이트 정책을 다시 설정한 다음 사이트 정책이 글로벌 정책(최소 영향)을 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="67103-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="67103-115">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="67103-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="67103-116">다음 확인란을 클릭하여 사용하도록 설정할 푸시 알림 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67103-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="67103-117">**Microsoft 푸시 알림을** 사용하도록 설정하면 비즈니스용 Skype 앱을 사용하여 Windows Phone용 클라우드 기반 PNCH에 대한 푸시 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67103-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="67103-118">**Apple 푸시** 알림을 사용하도록 설정하면 Apple의 iOS(예: iPhone, iPad)를 실행하고 비즈니스용 Skype 앱을 사용하는 장치에 대해 Apple PNCH에 대한 푸시 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67103-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="67103-p105">정책 편집을 완료한 후 **커밋** 을 클릭하여 변경 내용을 저장합니다. 적용한 변경 내용을 삭제해야 하는 경우 **취소** 를 선택합니다. 그러면 변경 내용이 정책에 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67103-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

