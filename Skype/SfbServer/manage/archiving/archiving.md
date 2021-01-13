---
title: 비즈니스용 Skype 서버에서 보관 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '요약: 비즈니스용 Skype 서버의 보관을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817738"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="912a5-103">비즈니스용 Skype 서버에서 보관 관리</span><span class="sxs-lookup"><span data-stu-id="912a5-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="912a5-104">**요약:** 비즈니스용 Skype 서버의 보관을 관리하는 방법을 알아보는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="912a5-105">조직에 대한 보관을 배포할 때 배포 중에 초기 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="912a5-106">그러나 매일 관리하거나 조직의 새로운 요구 사항을 충족하기 위해 보관 지원을 구현하는 방법을 변경하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="912a5-107">예를 들어 조직 내의 특정 사이트, 특정 풀 또는 특정 사용자에 대해 보관 지원을 다르게 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="912a5-108">비즈니스용 Skype 서버에 있는 사용자의 경우 보관 구성 옵션 및 사용자 정책을 만들고 사용자 지정하여 이 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="912a5-109">이 항목을 읽기 전에 비즈니스용 Skype 서버의 보관 계획 및 비즈니스용 [Skype](../../plan-your-deployment/archiving/archiving.md) 서버용 보관 배포의 정보에 익숙해야 [합니다.](../../deploy/deploy-archiving/deploy-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="912a5-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="912a5-110">배포에 대해 Microsoft Exchange 통합을 사용하도록 설정하는 경우 Exchange 정책은 Exchange에 있으며 사서함이 보류된 사용자에 대해 보관을 사용할지 여부를 In-Place 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="912a5-111">자세한 내용은 비즈니스용 Skype 서버에서 보관 계획 및 비즈니스용 [Skype](../../plan-your-deployment/archiving/archiving.md) 서버용 Exchange 저장소와의 통합 [구성을 참조하세요.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="912a5-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="912a5-112">보관 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="912a5-112">Archiving configuration options</span></span>

<span data-ttu-id="912a5-113">보관 구성 옵션은 다음을 할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="912a5-114">보관을 활성화 또는 비활성화</span><span class="sxs-lookup"><span data-stu-id="912a5-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="912a5-115">IM 세션 보관</span><span class="sxs-lookup"><span data-stu-id="912a5-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="912a5-116">웹 회의 세션 보관</span><span class="sxs-lookup"><span data-stu-id="912a5-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="912a5-117">보관을 사용할 수 없는 경우 활동 차단</span><span class="sxs-lookup"><span data-stu-id="912a5-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="912a5-118">Exchange 통합 사용</span><span class="sxs-lookup"><span data-stu-id="912a5-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="912a5-119">데이터 제거 및 내보내기 설정</span><span class="sxs-lookup"><span data-stu-id="912a5-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="912a5-120">이러한 옵션은 전역, 사이트 또는 풀 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="912a5-121">자세한 내용은 비즈니스용 Skype 서버에서 보관 옵션 [관리를 참조하세요.](options.md)</span><span class="sxs-lookup"><span data-stu-id="912a5-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="912a5-122">보관 정책</span><span class="sxs-lookup"><span data-stu-id="912a5-122">Archiving policies</span></span>

<span data-ttu-id="912a5-123">보관 정책에 따라 다음을 보관할지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="912a5-124">내부 통신</span><span class="sxs-lookup"><span data-stu-id="912a5-124">Internal communications</span></span>
    
- <span data-ttu-id="912a5-125">외부 통신</span><span class="sxs-lookup"><span data-stu-id="912a5-125">External communications</span></span>
    
<span data-ttu-id="912a5-126">이러한 정책은 전역, 사이트 또는 사용자 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="912a5-127">자세한 내용은 비즈니스용 Skype 서버에서 보관 정책 [관리를 참조하세요.](policies.md)</span><span class="sxs-lookup"><span data-stu-id="912a5-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="912a5-128">제어판을 사용하여 또는 제어판을 사용하여 보관을 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="912a5-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="912a5-129">제어판을 사용하여 또는 보관을 사용하여 보관을 관리할 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="912a5-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="912a5-130">다음 표에서는 보관을 관리하는 데 사용할 수 있는 cmdlet을 요약하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="912a5-131">사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="912a5-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="912a5-132">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="912a5-132">**Cmdlet**</span></span>|<span data-ttu-id="912a5-133">**설명**</span><span class="sxs-lookup"><span data-stu-id="912a5-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="912a5-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="912a5-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="912a5-135">비즈니스용 Skype 서버 보관 데이터베이스에 저장된 레코드를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="912a5-136">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="912a5-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="912a5-137">조직의 보관 구성 설정에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="912a5-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="912a5-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="912a5-139">내부 및 외부 통신에 대한 조직의 보관 정책에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="912a5-140">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="912a5-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="912a5-141">사용자 또는 사용자 집합에 IM(인스턴트 메시징) 세션 보관 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="912a5-142">이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="912a5-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="912a5-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="912a5-144">보관 데이터베이스에서 레코드를 수동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="912a5-145">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="912a5-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="912a5-146">메신저 세션 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 차단하는 데 사용할 수 있는 새 IM(인스턴트 메시징) 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="912a5-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="912a5-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="912a5-148">새 IM(인스턴트 메시징) 세션 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="912a5-149">이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="912a5-150">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="912a5-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="912a5-151">IM(인스턴트 메시징) 세션의 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 선택적으로 차단하는 데 사용되는 보관 설정의 지정된 컬렉션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="912a5-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="912a5-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="912a5-153">비즈니스용 Skype 서버에서 내부 사용자 간에 수행되는 모든 메신저 세션 및/또는 내부 사용자와 페더링 파트너 간의 모든 메신저 세션을 자동으로 저장할지 여부를 결정하는 지정된 IM(인스턴트 메시징) 보관 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="912a5-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="912a5-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="912a5-155">IM(인스턴트 메시징) 보관 구성 옵션의 기존 컬렉션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="912a5-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="912a5-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="912a5-157">기존 메신저 대화 보관 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="912a5-158">보관 정책을 사용하면 내부 사용자 간에 수행되는 모든 메신저 대화 세션과 전화 회의를 보관하는 기능을 사용할 수 있고, 내부 사용자와 페더레이션 파트너 간에 수행되는 세션을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="912a5-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="912a5-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="912a5-160">하나 이상의 보관 서버에 대한 새 데이터베이스 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912a5-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

