---
title: 비즈니스용 Skype 서버에서 보관 정책 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '요약: 비즈니스용 Skype 서버 보관에 대한 사용자 정책을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828554"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="cf3cd-103">비즈니스용 Skype 서버에서 보관 정책 관리</span><span class="sxs-lookup"><span data-stu-id="cf3cd-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="cf3cd-104">**요약:** 비즈니스용 Skype 서버 보관에 대한 사용자 정책을 관리하는 방법을 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="cf3cd-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="cf3cd-105">보관을 배포할 때 처음에는 보관 정책을 설정했지만 배포 후에 구성을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="cf3cd-106">보관 정책에 따라 보관 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="cf3cd-107">내부 통신</span><span class="sxs-lookup"><span data-stu-id="cf3cd-107">Internal communications</span></span>
    
- <span data-ttu-id="cf3cd-108">외부 통신</span><span class="sxs-lookup"><span data-stu-id="cf3cd-108">External communications</span></span>
    
<span data-ttu-id="cf3cd-109">보관 정책은 전역, 사이트 또는 사용자 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf3cd-110">배포에 Microsoft Exchange 통합을 사용하도록 설정한 경우 Exchange 정책은 Exchange에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어하고 사서함을 보류로 In-Place 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="cf3cd-111">자세한 내용은 비즈니스용 Skype 서버에서 보관 계획 및 비즈니스용 [Skype](../../plan-your-deployment/archiving/archiving.md) 서버용 Exchange 저장소와의 통합 [구성을 참조하세요.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="cf3cd-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="cf3cd-112">제어판을 사용하여 보관 정책 관리</span><span class="sxs-lookup"><span data-stu-id="cf3cd-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="cf3cd-113">다음과 같이 제어판을 사용하여 보관 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="cf3cd-114">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="cf3cd-115">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cf3cd-116">왼쪽 탐색 모음에서 보관 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf3cd-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="cf3cd-117">보관 정책을 사용하여 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf3cd-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="cf3cd-118">또한 다음 표에 나열된 Windows PowerShell cmdlet을 사용하여 보관 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="cf3cd-119">사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="cf3cd-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="cf3cd-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cf3cd-120">**Cmdlet**</span></span>|<span data-ttu-id="cf3cd-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="cf3cd-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf3cd-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cf3cd-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cf3cd-123">조직의 IM(인스턴트 메시징) 세션 보관 정책에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="cf3cd-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cf3cd-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cf3cd-125">사용자 또는 사용자 집합에 IM(인스턴트 메시징) 세션 보관 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="cf3cd-126">이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="cf3cd-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cf3cd-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cf3cd-128">새 IM(인스턴트 메시징) 세션 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="cf3cd-129">이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="cf3cd-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cf3cd-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cf3cd-131">비즈니스용 Skype 서버에서 내부 사용자 간에 수행되는 모든 메신저 세션 및/또는 내부 사용자와 페더링 파트너 간의 모든 메신저 세션을 자동으로 저장할지 여부를 결정하는 지정된 IM(인스턴트 메시징) 보관 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="cf3cd-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cf3cd-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cf3cd-133">기존 메신저 대화 보관 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="cf3cd-134">보관 정책을 사용하면 내부 사용자 간에 수행되는 모든 메신저 대화 세션과 전화 회의를 보관하는 기능을 사용할 수 있고, 내부 사용자와 페더레이션 파트너 간에 수행되는 세션을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3cd-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

