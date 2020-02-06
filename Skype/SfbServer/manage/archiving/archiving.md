---
title: 비즈니스용 Skype 서버에서 보관 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '요약: 비즈니스용 Skype 서버용 보관을 관리 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819000"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="53893-103">비즈니스용 Skype 서버에서 보관 관리</span><span class="sxs-lookup"><span data-stu-id="53893-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="53893-104">**요약:** 비즈니스용 Skype 서버용 보관을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="53893-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="53893-105">조직의 보관을 배포 하는 경우 배포 중에 초기 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="53893-106">그러나 일 대 일 관리에 대 한 보관 지원을 구현 하는 방법이 나 조직의 새로운 요구 사항을 충족 하는 방법을 변경 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="53893-107">예를 들어 특정 사이트, 특정 풀 또는 조직 내의 특정 사용자에 대해 보관 지원을 다르게 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="53893-108">비즈니스용 Skype Server에 속한 사용자의 경우, 보관 구성 옵션 및 사용자 정책을 만들고 사용자 지정 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="53893-109">이 항목을 읽기 전에 비즈니스용 [Skype 서버에서 보관을 계획](../../plan-your-deployment/archiving/archiving.md) 하 고 비즈니스용 [skype 서버용 보관을 배포](../../deploy/deploy-archiving/deploy-archiving.md)하는 방법에 대 한 정보를 숙지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="53893-110">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 정책은 Exchange를 사용 하는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="53893-111">자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md) 및 비즈니스용 [skype 서버에 대 한 Exchange 저장소 통합 구성](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53893-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="53893-112">보관 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="53893-112">Archiving configuration options</span></span>

<span data-ttu-id="53893-113">보관 구성 옵션 다음 중 선택 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="53893-114">보관을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="53893-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="53893-115">IM 세션 보관</span><span class="sxs-lookup"><span data-stu-id="53893-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="53893-116">웹 회의 세션 보관</span><span class="sxs-lookup"><span data-stu-id="53893-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="53893-117">보관을 사용할 수 없는 경우 활동 차단</span><span class="sxs-lookup"><span data-stu-id="53893-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="53893-118">Exchange 통합 사용</span><span class="sxs-lookup"><span data-stu-id="53893-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="53893-119">데이터 제거 및 내보내기 설정</span><span class="sxs-lookup"><span data-stu-id="53893-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="53893-120">이러한 옵션은 전역, 사이트 또는 풀 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="53893-121">자세한 내용은 비즈니스용 [Skype 서버의 보관 옵션 관리](options.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53893-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="53893-122">보관 정책</span><span class="sxs-lookup"><span data-stu-id="53893-122">Archiving policies</span></span>

<span data-ttu-id="53893-123">보관 정책은 다음을 보관할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="53893-124">내부 통신</span><span class="sxs-lookup"><span data-stu-id="53893-124">Internal communications</span></span>
    
- <span data-ttu-id="53893-125">외부 통신</span><span class="sxs-lookup"><span data-stu-id="53893-125">External communications</span></span>
    
<span data-ttu-id="53893-126">이러한 정책은 전역, 사이트 또는 사용자 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="53893-127">자세한 내용은 비즈니스용 [Skype 서버에서 보관 정책 관리](policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53893-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="53893-128">제어판을 사용 하거나 Windows PowerShell을 사용 하 여 보관 관리</span><span class="sxs-lookup"><span data-stu-id="53893-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="53893-129">제어판을 사용 하거나 Windows PowerShell을 사용 하 여 보관을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="53893-130">다음 표에는 보관을 관리 하는 데 사용할 수 있는 cmdlet이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="53893-131">사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server Management Shell](../management-shell.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53893-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="53893-132">**은**</span><span class="sxs-lookup"><span data-stu-id="53893-132">**Cmdlet**</span></span>|<span data-ttu-id="53893-133">**설명**</span><span class="sxs-lookup"><span data-stu-id="53893-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53893-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="53893-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="53893-135">비즈니스용 Skype 서버 보관 데이터베이스에 저장 된 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="53893-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="53893-136">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="53893-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="53893-137">조직의 보관 구성 설정에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="53893-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="53893-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="53893-139">내부 및 외부 통신을 위한 조직의 보관 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="53893-140">부여-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="53893-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="53893-141">사용자 또는 사용자 집합에 IM (인스턴트 메시징) 세션 보관 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="53893-142">이러한 정책을 사용 하면 내부 사용자 간에 발생 하는 모든 IM 세션을 보관 하거나 내부 사용자와 외부 파트너 간에 발생 하는 모든 IM 세션을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="53893-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="53893-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="53893-144">보관 데이터베이스에서 레코드를 수동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="53893-145">새로운 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="53893-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="53893-146">메신저 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하 고 보관할 수 없는 모든 인스턴트 메시지를 차단 하는 데 사용할 수 있는 메신저 (인스턴트 메시징)의 새 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53893-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="53893-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="53893-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="53893-148">새 IM (인스턴트 메시징) 세션 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53893-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="53893-149">이러한 정책을 사용 하면 내부 사용자 간에 발생 하는 모든 IM 세션을 보관 하거나 내부 사용자와 외부 파트너 간에 발생 하는 모든 IM 세션을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="53893-150">제거-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="53893-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="53893-151">IM (인스턴트 메시징) 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하는 데 사용 되는 지정 된 보관 설정 컬렉션을 제거 하 고, 선택적으로 보관할 수 없는 인스턴트 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="53893-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="53893-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="53893-153">비즈니스용 Skype 서버가 내부 사용자와 페더레이션 파트너 간에 발생 하는 모든 im 세션을 자동으로 저장 하는지 여부를 결정 하는 지정 된 IM (인스턴트 메시징) 보관 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="53893-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="53893-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="53893-155">기존 IM (인스턴트 메시징) 보관 구성 옵션의 컬렉션을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="53893-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="53893-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="53893-157">기존 IM (인스턴트 메시징) 보관 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53893-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="53893-158">보관 정책을 통해 내부 사용자 간에 발생 하는 모든 IM 세션과 회의를 보관할 수 있습니다. 내부 사용자와 페더레이션 파트너 간에 발생 하는 세션만 보관할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="53893-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="53893-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="53893-160">하나 이상의 보관 서버에 대 한 새 데이터베이스 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53893-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

