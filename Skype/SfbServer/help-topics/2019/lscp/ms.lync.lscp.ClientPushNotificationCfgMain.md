---
title: 모바일 클라이언트 푸시 알림 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 푸시 알림 및 Apple 푸시 알림을 구성 하려면 필요한 푸시 알림 유형을 정의 하는 정책을 만들어야 합니다.
ms.openlocfilehash: 0211b3a8306297bd68402ad47d3c243541adf2bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197108"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="88a97-103">모바일 클라이언트: 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="88a97-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="88a97-104">**Microsoft 푸시 알림** 및 **Apple 푸시 알림을**구성 하려면 필요한 푸시 알림 유형을 정의 하는 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="88a97-105">주 구성 화면에서 **새로 고침** 을 클릭 하 여 정책 목록을 새로 고친 다음 다시 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="88a97-106">표시 된 정책 목록의 범위를 좁히는 검색 상자가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="88a97-107">검색할 이름을 입력 하면 정책 목록이 자동으로 축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="88a97-108">하나의 정책 수준에서 적용 되는 정책 설정이 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="88a97-109">정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책 보다 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="88a97-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="88a97-110">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="88a97-111">두 가지 선택 항목을 정책 만들기 및 편집에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="88a97-112">**새로**만들기:를 클릭 하 여 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="88a97-113">적용할 정책의 사이트를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="88a97-114">그런 다음 푸시 알림에 대 한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="88a97-115">**푸시 알림 구성**의 경우 이미 만든 사이트에 대 한 정책만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="88a97-116">**편집**: 정책을 선택 하 고 편집을 클릭 하 여 드롭다운에서 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="88a97-117">이미 만든 사이트를 편집 하거나 전역 정책을 편집할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="88a97-118">**세부 정보 표시**...: 현재 선택한 정책에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="88a97-119">기존 정책을 변경할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="88a97-120">**모두 선택**: 정책이 여러 개 있고 모든 정책을 선택 해야 하는 경우 모두 선택을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="88a97-121">**Delete**: 선택한 정책이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="88a97-122">**모두 선택** 및 **삭제** 를 사용 하 여 모든 정책이 제거 됨</span><span class="sxs-lookup"><span data-stu-id="88a97-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="88a97-123">기본 **전역** 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="88a97-124">이를 삭제 하려고 하면 글로벌 정책이 기본값으로 (즉, 모든 설정이 지워짐), 정책을 제거할 수 없음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="88a97-125">새 정책 만들기 또는 기존 정책 편집은 두 가지 동작과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="88a97-126">**Commit** 커밋 작업은 정책을 만들거나 업데이트 하 고 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="88a97-127">**취소** 취소 작업을 수행 하면 마지막 커밋 작업 이후 변경 된 내용이 모두 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="88a97-128">취소 하면 변경한 내용이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="88a97-129">**푸시 알림 구성**에는 두 가지 설정이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="88a97-130">이 설정은 Microsoft 및 Apple 용 푸시 알림 서비스와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="88a97-131">서비스 이름 옆에 있는 확인란을 선택 하 여 두 서비스에 대해 푸시 알림을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="88a97-132">확인란을 선택 취소 하 여 선택을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="88a97-133">선택한 후에는 커밋하거나 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="88a97-134">커밋을 클릭 하면 정책의 변경 내용이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88a97-134">Clicking commit will save the changes to the policy.</span></span>
  

