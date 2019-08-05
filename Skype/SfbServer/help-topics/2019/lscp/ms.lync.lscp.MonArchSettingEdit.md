---
title: 보관 구성 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 보관 구성을 사용하여 배포에 대한 보관 옵션을 제어합니다. 보관 구성에는 전역 구성과 하나 이상의 사이트 및 풀 구성(선택 사항)이 포함됩니다.
ms.openlocfilehash: 68d5de88fc56441989e8ffc9ceabfd3236179d1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196185"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="fe8b6-104">보관 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="fe8b6-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="fe8b6-p102">보관 구성을 사용하여 배포에 대한 보관 옵션을 제어합니다. 보관 구성에는 전역 구성과 하나 이상의 사이트 및 풀 구성(선택 사항)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-p102">You use Archiving configurations to control archiving options for your deployment. Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="fe8b6-107">**전역 구성** 전역 구성은 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="fe8b6-108">전역 구성을 편집할 수는 있지만 이 보관 구성을 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="fe8b6-109">구성을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="fe8b6-110">**사이트 구성 (선택 사항)** 특정 사이트에 대 한 보관 옵션을 제어 하도록 구성할 수 있는 하나 이상의 사이트 보관 구성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="fe8b6-111">사이트 구성은 보관 사이트 구성에 지정된 사이트에 한해 전역 구성에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="fe8b6-112">사이트 구성은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="fe8b6-113">**풀 구성 (선택 사항)** 특정 풀에 대 한 보관 옵션을 제어 하는 풀 보관 구성을 하나 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="fe8b6-114">풀 구성은 보관 풀 구성에 지정된 풀에 한해 전역 구성 및 사이트 구성에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="fe8b6-115">풀 구성은 편집하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe8b6-116">보관 구성은 비즈니스용 Skype 서버에 있는 사용자에 게 적용 되며, exchange를 사용 하 여 microsoft exchange에 보관 데이터를 저장 하는 경우 Exchange를 통해 사용자에 게 microsoft exchange 통합 옵션을 사용할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange.</span></span> <span data-ttu-id="fe8b6-117">그러나 다음 섹션에 설명 된 것 처럼 Exchange에 속한 사용자에 게 약간 다르게 구현 되는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-117">However, some options are implemented slightly differently for users homed on Exchange, as described in the next section.</span></span> 
  
<span data-ttu-id="fe8b6-118">새 보관 구성 또는 기존 보관 구성의 설정을 구성하려면 다음 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="fe8b6-119">**이름** 각 보관 구성에는 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="fe8b6-120">이름은 추가 하거나 편집 하는 구성 유형에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="fe8b6-121">**전역 구성** 기본 이름은 전역입니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="fe8b6-122">예를 들면 '한미 교역 북미 조직'과 같은 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="fe8b6-123">**사이트 구성** 목록에는 배포에서 사용할 수 있는 사이트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="fe8b6-124">사이트 하나를 클릭하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-124">Click a single site to select it.</span></span> <span data-ttu-id="fe8b6-125">예를 들면 'Redmond 데이터 센터'와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="fe8b6-126">**풀 구성** 적절 한 이름을 지정 합니다. 배포에서 특정 프런트 엔드 풀 또는 Standard Edition 서버의 이름이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="fe8b6-127">예를 들면 '마케팅 부문'과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="fe8b6-128">**설명** 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-128">**Description** This is optional.</span></span> <span data-ttu-id="fe8b6-129">이 기능을 사용 하 여 구성 범위 또는 사용 등의 추가 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="fe8b6-130">예를 들어 다른 사이트의 법률 부서를 사용 하 여 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="fe8b6-131">**보관 설정** 옵션에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="fe8b6-132">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="fe8b6-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="fe8b6-133">**IM 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="fe8b6-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="fe8b6-134">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="fe8b6-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="fe8b6-135">**보관에 실패 하는 경우 메신저 대화 (인스턴트 메시징) 또는 웹 회의 세션 차단** 오류에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="fe8b6-136">**IM** 실패는 저장소 서비스에 대 한 전체 데이터베이스 또는 문제일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="fe8b6-137">이 경우 보관을 사용하도록 설정된 사용자에 대해 메신저가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="fe8b6-138">**회의** 오류가 발생 하 여 파일 공유를 사용할 수 없거나 저장소 서비스의 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="fe8b6-139">이 경우 실패 시 풀에서 호스팅되는 모든 활성 회의가 제한 모드로 전환되며 새 회의를 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="fe8b6-140">오류가 수정된 다음에는 메신저 및 회의 모두 자동으로 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="fe8b6-141">**Microsoft Exchange 통합** Exchange에 속한 사용자가 있는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange.</span></span> <span data-ttu-id="fe8b6-142">이 옵션을 사용 하면 사서함이 원본 위치 유지에 배치 된 경우 Exchange가 해당 사용자의 데이터를 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-142">With this option, Exchange is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="fe8b6-143">모든 사용자가 Exchange에 속한 경우에는 데이터 보관을 위해 별도의 SQL Server 데이터베이스를 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-143">If all your users are homed on Exchange, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="fe8b6-144">**보관 데이터 제거 사용** 제거를 사용 하도록 설정 하 고 다음을 포함 하는 제거 옵션을 지정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="fe8b6-145">지정한 특정 기간(일) 후 삭제</span><span class="sxs-lookup"><span data-stu-id="fe8b6-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="fe8b6-146">보관 데이터를 내보낸 후 제거 (Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange에 업로드 된 데이터 포함)</span><span class="sxs-lookup"><span data-stu-id="fe8b6-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fe8b6-147">Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange에 속한 사용자 및 사서함이 원본 위치 유지에 배치 된 상태에서 Exchange가 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="fe8b6-148">유일한 예외는 Lync Server 파일 공유에 저장 된 회의 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="fe8b6-149">이러한 파일은 보관 데이터를 내보낸 후 데이터를 삭제하는 옵션을 선택하는 경우에는 파일을 내보내 해당 파일이 Exchange에 업로드된 후에, 그리고 최대 보존 기간(일)을 지정하는 경우에는 지정된 최대 기간(일) 후에 파일 공유에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8b6-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="fe8b6-150">Exchange 통합을 포함 하 여 보관 기능 및 기능에 대 한 자세한 내용은 비즈니스용 skype [서버에서 보관 계획](../../../plan-your-deployment/archiving/archiving.md), 비즈니스용 [skype server 용 보관 배포](../../../deploy/deploy-archiving/deploy-archiving.md)및 비즈니스용 [skype에서 보관 관리를 참조 하세요. 서버](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="fe8b6-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

