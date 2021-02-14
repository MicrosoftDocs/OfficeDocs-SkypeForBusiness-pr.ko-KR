---
title: 비즈니스용 Skype 서버에서 보관 옵션 관리
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '요약: 비즈니스용 Skype 서버의 보관 옵션을 구성하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817538"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="29ef4-103">비즈니스용 Skype 서버에서 보관 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="29ef4-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="29ef4-104">**요약:** 비즈니스용 Skype 서버에 대한 보관 옵션을 구성하는 방법을 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="29ef4-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="29ef4-105">처음에는 배포 시 보관을 구성하지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="29ef4-106">보관 옵션에 따라 다음을 할지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="29ef4-107">보관을 활성화 또는 비활성화</span><span class="sxs-lookup"><span data-stu-id="29ef4-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="29ef4-108">IM 세션 보관</span><span class="sxs-lookup"><span data-stu-id="29ef4-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="29ef4-109">웹 회의 세션 보관</span><span class="sxs-lookup"><span data-stu-id="29ef4-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="29ef4-110">보관을 사용할 수 없는 경우 활동 차단</span><span class="sxs-lookup"><span data-stu-id="29ef4-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="29ef4-111">Exchange 통합 사용</span><span class="sxs-lookup"><span data-stu-id="29ef4-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="29ef4-112">데이터 제거 및 내보내기 설정</span><span class="sxs-lookup"><span data-stu-id="29ef4-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="29ef4-113">다음 수준에서 구성 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="29ef4-114">비즈니스용 Skype 서버를 배포할 때 기본적으로 생성되는 전역 수준 구성</span><span class="sxs-lookup"><span data-stu-id="29ef4-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="29ef4-115">특정 사이트에 대해 보관을 구현하는 방법을 지정하는 선택적 사이트 수준 구성</span><span class="sxs-lookup"><span data-stu-id="29ef4-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="29ef4-116">특정 풀에 대해 보관을 구현하는 방법을 지정하는 선택적 풀 수준 구성</span><span class="sxs-lookup"><span data-stu-id="29ef4-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="29ef4-117">사이트 구성 또는 풀 구성은 삭제할 수 있지만 전역 구성은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="29ef4-118">전역 구성을 삭제하는 경우 자동으로 구성이 기본값으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="29ef4-119">보관 구성을 구현하는 방법 및 보관 구성의 계층 구조에 대한 자세한 내용은 비즈니스용 Skype 서버의 보관 [계획(Plan for archiving)을 참조하세요.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="29ef4-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="29ef4-120">제어판을 사용하여 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="29ef4-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="29ef4-121">다음과 같이 제어판을 사용하여 보관 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="29ef4-122">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="29ef4-123">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="29ef4-124">왼쪽 탐색 모음에서 보관 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="29ef4-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="29ef4-125">보관 옵션을 구성하는 방법을 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ef4-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="29ef4-126">또한 다음 표에 나열된 Windows PowerShell cmdlet을 사용하여 보관 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="29ef4-127">사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="29ef4-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="29ef4-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="29ef4-128">**Cmdlet**</span></span>|<span data-ttu-id="29ef4-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="29ef4-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29ef4-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="29ef4-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="29ef4-131">조직의 보관 구성 설정에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="29ef4-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="29ef4-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="29ef4-133">메신저 세션 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 차단하는 데 사용할 수 있는 새 IM(인스턴트 메시징) 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="29ef4-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="29ef4-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="29ef4-135">IM(인스턴트 메시징) 세션의 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 선택적으로 차단하는 데 사용되는 보관 설정의 지정된 컬렉션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="29ef4-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="29ef4-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="29ef4-137">IM(인스턴트 메시징) 보관 구성 옵션의 기존 컬렉션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
