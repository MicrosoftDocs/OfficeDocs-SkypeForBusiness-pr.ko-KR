---
title: 비즈니스용 Skype 서버의 보관 옵션 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 옵션을 구성 하는 방법을 알아보세요.'
ms.openlocfilehash: c7353c305125e8e35523c573150471821f53301e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188223"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="838ad-103">비즈니스용 Skype 서버의 보관 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="838ad-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="838ad-104">**요약:** 비즈니스용 Skype 서버용 보관 옵션을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="838ad-105">배포 후 처음으로 보관을 구성한 후에는 배포 후에 구성을 변경, 추가, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="838ad-106">보관 옵션에 따라 다음 중 어느 것이 선택 되는지 여부</span><span class="sxs-lookup"><span data-stu-id="838ad-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="838ad-107">보관을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="838ad-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="838ad-108">IM 세션 보관</span><span class="sxs-lookup"><span data-stu-id="838ad-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="838ad-109">웹 회의 세션 보관</span><span class="sxs-lookup"><span data-stu-id="838ad-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="838ad-110">보관을 사용할 수 없는 경우 활동 차단</span><span class="sxs-lookup"><span data-stu-id="838ad-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="838ad-111">Exchange 통합 사용</span><span class="sxs-lookup"><span data-stu-id="838ad-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="838ad-112">데이터 제거 및 내보내기 설정</span><span class="sxs-lookup"><span data-stu-id="838ad-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="838ad-113">다음과 같은 수준으로 구성 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="838ad-114">비즈니스용 Skype 서버를 배포할 때 기본적으로 만들어지는 전역 수준 구성</span><span class="sxs-lookup"><span data-stu-id="838ad-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="838ad-115">특정 사이트에 대해 보관을 구현 하는 방법을 지정 하는 선택적 사이트 수준 구성</span><span class="sxs-lookup"><span data-stu-id="838ad-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="838ad-116">특정 풀에 대해 보관을 구현 하는 방법을 지정 하는 선택적 풀 수준 구성</span><span class="sxs-lookup"><span data-stu-id="838ad-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="838ad-117">사이트 구성 또는 풀 구성을 삭제할 수 있지만, 전역 구성은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="838ad-118">전역 구성을 삭제 하면 자동으로 기본 값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="838ad-119">보관 구성을 구현 하는 방법과 보관 구성의 계층 구조에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="838ad-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="838ad-120">제어판을 사용 하 여 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="838ad-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="838ad-121">다음과 같이 제어판을 사용 하 여 보관 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="838ad-122">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="838ad-123">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="838ad-124">왼쪽 탐색 모음에서 **보관 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="838ad-125">Windows PowerShell을 사용 하 여 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="838ad-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="838ad-126">다음 표에 나열 된 Windows PowerShell cmdlet을 사용 하 여 보관 옵션을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="838ad-127">사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server Management Shell](../management-shell.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="838ad-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="838ad-128">**은**</span><span class="sxs-lookup"><span data-stu-id="838ad-128">**Cmdlet**</span></span>|<span data-ttu-id="838ad-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="838ad-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="838ad-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="838ad-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="838ad-131">조직의 보관 구성 설정에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="838ad-132">새로운 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="838ad-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="838ad-133">메신저 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하 고 보관할 수 없는 모든 인스턴트 메시지를 차단 하는 데 사용할 수 있는 메신저 (인스턴트 메시징)의 새 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="838ad-134">제거-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="838ad-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="838ad-135">IM (인스턴트 메시징) 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하는 데 사용 되는 지정 된 보관 설정 컬렉션을 제거 하 고, 선택적으로 보관할 수 없는 인스턴트 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="838ad-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="838ad-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="838ad-137">기존 IM (인스턴트 메시징) 보관 구성 옵션의 컬렉션을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ad-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
