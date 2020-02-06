---
title: 비즈니스용 Skype 서버에서 보관 정책 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '요약: 비즈니스용 Skype 서버용으로 보관할 사용자 정책을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818890"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="5e78e-103">비즈니스용 Skype 서버에서 보관 정책 관리</span><span class="sxs-lookup"><span data-stu-id="5e78e-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="5e78e-104">**요약:** 비즈니스용 Skype 서버용으로 보관할 사용자 정책을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="5e78e-105">보관 정책을 처음에 설정 했지만 배포 후에 구성을 변경, 추가, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="5e78e-106">보관 정책은 보관할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="5e78e-107">내부 통신</span><span class="sxs-lookup"><span data-stu-id="5e78e-107">Internal communications</span></span>
    
- <span data-ttu-id="5e78e-108">외부 통신</span><span class="sxs-lookup"><span data-stu-id="5e78e-108">External communications</span></span>
    
<span data-ttu-id="5e78e-109">보관 정책은 전역, 사이트 또는 사용자 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e78e-110">배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 정책은 Exchange에 설치 된 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5e78e-111">자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md) 및 비즈니스용 [skype 서버에 대 한 Exchange 저장소 통합 구성](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e78e-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="5e78e-112">제어판을 사용 하 여 보관 정책 관리</span><span class="sxs-lookup"><span data-stu-id="5e78e-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="5e78e-113">다음과 같이 제어판을 사용 하 여 보관 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="5e78e-114">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5e78e-115">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5e78e-116">왼쪽 탐색 모음에서 **보관 정책을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="5e78e-117">Windows PowerShell을 사용 하 여 보관 정책 관리</span><span class="sxs-lookup"><span data-stu-id="5e78e-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="5e78e-118">다음 표에 나열 된 Windows PowerShell cmdlet을 사용 하 여 보관 정책을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="5e78e-119">사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server Management Shell](../management-shell.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e78e-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="5e78e-120">**은**</span><span class="sxs-lookup"><span data-stu-id="5e78e-120">**Cmdlet**</span></span>|<span data-ttu-id="5e78e-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="5e78e-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5e78e-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="5e78e-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="5e78e-123">조직의 IM (인스턴트 메시징) 세션 보관 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="5e78e-124">부여-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="5e78e-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="5e78e-125">사용자 또는 사용자 집합에 IM (인스턴트 메시징) 세션 보관 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="5e78e-126">이러한 정책을 사용 하면 내부 사용자 간에 발생 하는 모든 IM 세션을 보관 하거나 내부 사용자와 외부 파트너 간에 발생 하는 모든 IM 세션을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="5e78e-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="5e78e-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="5e78e-128">새 IM (인스턴트 메시징) 세션 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="5e78e-129">이러한 정책을 사용 하면 내부 사용자 간에 발생 하는 모든 IM 세션을 보관 하거나 내부 사용자와 외부 파트너 간에 발생 하는 모든 IM 세션을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="5e78e-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="5e78e-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="5e78e-131">비즈니스용 Skype 서버가 내부 사용자와 페더레이션 파트너 간에 발생 하는 모든 im 세션을 자동으로 저장 하는지 여부를 결정 하는 지정 된 IM (인스턴트 메시징) 보관 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="5e78e-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="5e78e-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="5e78e-133">기존 IM (인스턴트 메시징) 보관 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="5e78e-134">보관 정책을 통해 내부 사용자 간에 발생 하는 모든 IM 세션과 회의를 보관할 수 있습니다. 내부 사용자와 페더레이션 파트너 간에 발생 하는 세션만 보관할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e78e-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

