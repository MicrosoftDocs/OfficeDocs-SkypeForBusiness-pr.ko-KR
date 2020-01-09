---
title: 비즈니스용 Skype 서버에서 회의 서버 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '요약: 비즈니스용 Skype 서버에서 회의 서버 구성 설정을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: be6ccb094cc19a29534d1ca78eb2cae1457d6512
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991903"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d02b3-103">비즈니스용 Skype 서버에서 회의 서버 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="d02b3-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d02b3-104">**요약:** 비즈니스용 Skype 서버에서 회의 서버 구성 설정을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d02b3-105">이 항목에서는 회의 구성 설정을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="d02b3-106">회의를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 계획](../../plan-your-deployment/conferencing/conferencing.md) 및 비즈니스용 [skype 서버에서 회의 배포](../../deploy/deploy-conferencing/deploy-conferencing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d02b3-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="d02b3-107">회의 구성 설정에서는 모임 콘텐츠 및 유인물에 허용 되는 최대 크기와 같은 항목을 결정 합니다. 응용 프로그램 공유 회의 서비스에 대 한 최대 대역폭 양 저장소 용량 한도 및 만료 기간 지원 되는 클라이언트의 내부 및 외부 다운로드에 대 한 Url입니다. 사용자가 회의 도움말 및 리소스를 얻을 수 있는 내부 및 외부 Url에 대 한 포인터 응용 프로그램 공유, 클라이언트 오디오, 파일 전송 및 미디어 트래픽에 사용 되는 포트.</span><span class="sxs-lookup"><span data-stu-id="d02b3-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="d02b3-108">이러한 설정을 통해 실제 서버 자체를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="d02b3-109">이 설정은 비즈니스용 Skype 서버 관리 셸을 사용 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="d02b3-110">비즈니스용 Skype 서버를 설치 하면 시스템에서 하나의 회의 구성 설정 (전역 컬렉션) 모음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="d02b3-111">사이트 또는 서비스에 대 한 사용자 지정 설정을 만들어야 하는 경우 **CsConferencingConfiguration** cmdlet을 사용 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="d02b3-112">새 설정은 사이트 또는 서비스 범위에만 적용할 수 있습니다. 새 회의 구성 설정 집합을 만들 수는 없지만 **CsConferencingConfiguration** cmdlet을 사용 하 여 전역 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="d02b3-113">또한 사이트 또는 서비스는 둘 이상의 설정 모음을 호스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="d02b3-114">Redmond 사이트에 대 한 새 설정을 만들려고 할 때 레드먼드 사이트가 이미 회의 구성 설정 모음을 호스트 하는 경우에는 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d02b3-115">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="d02b3-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d02b3-116">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 구성 설정을 관리 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="d02b3-117">**회의 구성 설정**</span><span class="sxs-lookup"><span data-stu-id="d02b3-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="d02b3-118">**은**</span><span class="sxs-lookup"><span data-stu-id="d02b3-118">**Cmdlet**</span></span>|<span data-ttu-id="d02b3-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="d02b3-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d02b3-120">Get-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d02b3-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d02b3-121">조직의 회의 구성 설정에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="d02b3-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d02b3-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d02b3-123">새 회의 구성 설정 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="d02b3-124">제거-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d02b3-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d02b3-125">지정 된 회의 구성 설정 모음을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="d02b3-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d02b3-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d02b3-127">기존 회의 구성 설정 컬렉션을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="d02b3-128">다음 명령은 Redmond 사이트 (사이트: Redmond)에 대 한 새 회의 구성 설정 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-128">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond).</span></span> <span data-ttu-id="d02b3-129">이 예제에서는 조직 속성의 값을 Litwareinc로 설정 하는 데 사용 되는 추가 매개 변수 하나 (조직)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-129">In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="d02b3-130">사이트 마다 이러한 컬렉션을 하나만 가질 수 있으므로 Redmond 사이트에 이미 회의 구성 설정 모음이 있는 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="d02b3-131">다음 예에서는 처음에 메모리에 저장 된 다음 나중에 Redmond 사이트에 적용 되는 회의 구성 설정의 새 컬렉션을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="d02b3-132">첫 번째 명령은 **CsConferencingConfiguration** cmdlet을 사용 하 여 변수 $x에 저장 된 새 설정의 메모리 내 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="d02b3-133">InMemory 매개 변수는 컬렉션이 Redmond 사이트에 즉시 적용 되지 않고 메모리에 만들어지도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="d02b3-134">컬렉션을 만든 후 두 번째 명령은 조직 속성의 값을 Litwareinc로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="d02b3-135">마지막으로 세 번째 명령은 **CsConferencingConfiguration** cmdlet을 사용 하 여 새 설정을 Redmond 사이트에 실제로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="d02b3-136">**Set-CsConferencingConfiguration** cmdlet을 호출 하지 않으면 새 설정이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="d02b3-137">대신 Windows PowerShell 세션을 종료 하거나 변수 $x 삭제 하는 즉시 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="d02b3-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

