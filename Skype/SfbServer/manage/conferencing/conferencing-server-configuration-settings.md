---
title: 비즈니스용 Skype 서버에서 회의 서버 구성 설정 관리
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '요약: 비즈니스용 Skype 서버에서 회의 서버 구성 설정을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: db44ad62acb99bab32b732ea0686784b14c3b2b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099094"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="00451-103">비즈니스용 Skype 서버에서 회의 서버 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="00451-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="00451-104">**요약:** 비즈니스용 Skype 서버에서 회의 서버 구성 설정을 관리하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="00451-105">이 항목에서는 회의 구성 설정을 관리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="00451-106">회의를 계획하고 배포하는 방법에 대한 자세한 내용은 [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) 및 Deploy [conferencing in Skype for Business Server를 참조하십시오.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="00451-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="00451-107">회의 구성 설정은 모임 콘텐츠 및 유인물에 허용되는 최대 크기와 같은 내용을 확인합니다. 응용 프로그램 공유 회의 서비스의 최대 대역폭 양 저장소 제한 및 만료 기간 지원되는 클라이언트의 내부 및 외부 다운로드 URL 사용자가 회의 도움말 및 리소스를 얻을 수 있는 내부 및 외부 URL에 대한 포인터 및 응용 프로그램 공유, 클라이언트 오디오, 파일 전송 및 미디어 트래픽에 사용되는 포트</span><span class="sxs-lookup"><span data-stu-id="00451-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="00451-108">이러한 설정을 통해 실제 서버를 직접 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00451-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="00451-109">이러한 설정은 비즈니스용 Skype 서버 관리 셸을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00451-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="00451-110">비즈니스용 Skype 서버를 설치하면 시스템에서 단일 회의 구성 설정 컬렉션(전역 컬렉션)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="00451-111">사이트 또는 서비스의 사용자 지정 설정을 만들어야 하는 경우 **New-CsConferencingConfiguration** cmdlet을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00451-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="00451-112">새 설정은 사이트 또는 서비스 범위에서만 적용할 수 있습니다. 새 전역 회의 구성 설정 컬렉션을 만들 수는 없지만 **Set-CsConferencingConfiguration** cmdlet을 사용하여 전역 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00451-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="00451-113">또한 사이트 또는 서비스는 설정 컬렉션을 두 개 이상 호스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00451-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="00451-114">Redmond 사이트에 대한 새 설정을 만들려고 하여 Redmond 사이트에 회의 구성 설정 컬렉션이 이미 호스트되어 있는 경우 명령이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="00451-115">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="00451-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="00451-116">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 구성 설정을 관리하려면 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="00451-117">**회의 구성 설정**</span><span class="sxs-lookup"><span data-stu-id="00451-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="00451-118">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="00451-118">**Cmdlet**</span></span>|<span data-ttu-id="00451-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="00451-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="00451-120">Get-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="00451-120">Get-CsConferencingConfiguration</span></span>](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="00451-121">조직의 회의 구성 설정에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="00451-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="00451-122">New-CsConferencingConfiguration</span></span>](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="00451-123">회의 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00451-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="00451-124">Remove-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="00451-124">Remove-CsConferencingConfiguration</span></span>](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="00451-125">지정한 회의 구성 설정 컬렉션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="00451-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="00451-126">Set-CsConferencingConfiguration</span></span>](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="00451-127">전화 회의 구성 설정의 기존 컬렉션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="00451-128">다음 명령은 Redmond 사이트(site:Redmond)에 대한 새 회의 구성 설정 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00451-128">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond).</span></span> <span data-ttu-id="00451-129">이 예에서는 Organization 속성의 값을 Litwareinc로 설정하는 데 사용되는 추가 매개 변수(Organization)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00451-129">In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="00451-130">사이트당 이러한 컬렉션을 하나만 사용할 수 있으므로 Redmond 사이트에 이미 회의 구성 설정 컬렉션이 있는 경우 이 명령이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="00451-131">다음 예제에서는 처음에 메모리에 저장된 다음 나중에 Redmond 사이트에 적용되는 회의 구성 설정의 새 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="00451-132">첫 번째 명령은 **New-CsConferencingConfiguration** cmd $x let을 사용하여 새 메모리 내 설정 컬렉션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="00451-133">InMemory 매개 변수는 Redmond 사이트에 즉시 적용되는 것이 아니라 메모리에서 컬렉션을 만들어야 한다고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="00451-134">컬렉션을 만든 후에는 두 번째 명령이 Organization 속성 값을 Litwareinc로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="00451-135">마지막으로 세 번째 명령은 **Set-CsConferencingConfiguration** cmdlet을 사용하여 Redmond 사이트에 새 설정을 실제로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="00451-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="00451-136">**Set-CsConferencingConfiguration** cmdlet을 호출하지 않는 경우 새 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00451-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="00451-137">대신 세션을 종료하거나 변수를 삭제하는 Windows PowerShell 즉시 $x.</span><span class="sxs-lookup"><span data-stu-id="00451-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
