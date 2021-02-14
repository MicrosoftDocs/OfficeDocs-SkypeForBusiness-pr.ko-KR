---
title: 모바일 클라이언트 푸시 알림 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Microsoft 푸시 알림 및 Apple 푸시 알림을 구성하려면 필요한 푸시 알림의 유형을 정의하는 정책을 만들어야 합니다.
ms.openlocfilehash: 493c8138e7c5dcaeab154ce1a44054cc082d1672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810878"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="b2ebc-103">모바일 클라이언트: 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="b2ebc-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="b2ebc-104">**Microsoft 푸시 알림** 및 **Apple 푸시 알림** 을 구성하려면 필요한 푸시 알림의 유형을 정의하는 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="b2ebc-p101">기본 구성 화면에서 **새로 고침** 을 클릭하여 정책 목록을 새로 고치고 다시 채울 수 있습니다. 표시되는 정책 목록의 범위를 좁힐 수 있도록 검색 상자가 제공됩니다. 검색하려는 이름을 입력하면 정책 목록 범위가 자동으로 좁혀집니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b2ebc-108">한 정책 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="b2ebc-109">정책 우선 순위는 사용자 정책(가장 큰 영향)이 사이트 정책을 다시 설정한 다음 사이트 정책이 글로벌 정책(최소 영향)을 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="b2ebc-110">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="b2ebc-111">정책 만들기 및 편집을 위해 두 가지 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="b2ebc-p103">**새로 만들기**: 새 정책을 만들려면 클릭합니다. 정책을 적용할 사이트를 지정해야 합니다. 그런 다음 푸시 알림을 위한 설정을 구성합니다. **푸시 알림 구성** 의 경우 이미 만든 사이트에 대해서만 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="b2ebc-p104">**편집**: 정책을 선택하고 편집을 클릭하여 드롭다운에서 동작을 선택합니다. 이미 만든 사이트를 편집하거나 글로벌 정책을 편집하는 동작만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="b2ebc-p105">**자세한 정보 표시...**: 현재 선택되어 있는 정책에 대한 정보를 표시합니다. 기존 정책을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="b2ebc-120">**모두 선택**: 여러 정책을 모두 선택해야 하는 경우 모두 선택을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="b2ebc-p106">**삭제**: 선택되어 있는 정책이 제거됩니다. **모두 선택** 과 **삭제** 를 사용하면 모든 정책을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="b2ebc-p107">기본 **글로벌** 정책은 삭제할 수 없습니다. 해당 정책을 삭제하려고 하면 글로벌 정책이 기본값으로 되돌아갔다는 알림이 표시되지만(모든 설정이 지워짐) 정책을 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="b2ebc-125">새 정책 만들기 또는 기존 정책 편집은 다음의 두 가지 동작과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="b2ebc-126">**커밋** 커밋 작업이 정책을 생성하거나 업데이트하고 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="b2ebc-127">**취소** 취소 작업은 마지막 커밋 작업 이후 적용된 모든 변경 내용을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="b2ebc-128">취소하면 변경한 내용이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="b2ebc-p109">**푸시 알림 구성** 에는 두 가지 설정을 사용할 수 있습니다. 이러한 설정은 Microsoft 및 Apple의 푸시 알림 서비스와 연결됩니다. 서비스 이름 옆의 확인란을 선택하여 각 서비스에 대해 푸시 알림을 사용하도록 설정합니다. 확인란을 다시 선택하면 선택을 취소할 수 있습니다. 원하는 대로 선택한 후에 커밋 또는 취소할 수 있습니다. 커밋을 클릭하면 정책에 대한 변경 내용이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ebc-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

