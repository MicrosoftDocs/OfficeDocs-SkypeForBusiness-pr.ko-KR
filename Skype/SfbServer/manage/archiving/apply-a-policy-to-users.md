---
title: 비즈니스용 Skype 서버에서 사용자에게 보관 정책 적용
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '요약: 비즈니스용 Skype 서버에서 사용자에게 보관 정책을 할당하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817768"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="e9c3a-103">비즈니스용 Skype 서버에서 사용자에게 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="e9c3a-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="e9c3a-104">**요약:** 비즈니스용 Skype 서버에서 사용자에게 보관 정책을 할당하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="e9c3a-105">비즈니스용 Skype 서버에 있는 사용자에 대한 보관에 대한 사용자 정책을 하나 이상 만든 경우 해당 사용자 또는 사용자 그룹에 적절한 정책을 적용하여 특정 사용자에 대한 보관 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="e9c3a-106">예를 들어 내부 통신 보관을 지원하는 정책을 만드는 경우 하나 이상의 사용자 또는 사용자 그룹에 정책을 적용하여 사용자의 비즈니스용 Skype 서버 통신 보관을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9c3a-107">배포에 Microsoft Exchange 통합을 사용하도록 설정한 경우 Exchange In-Place 보류 정책은 Exchange에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어하고 사서함을 보류로 In-Place 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e9c3a-108">자세한 내용은 비즈니스용 Skype 서버의 보관 계획 및 비즈니스용 [Skype](../../plan-your-deployment/archiving/archiving.md) 서버용 Exchange 저장소와의 통합 [구성을 참조하세요.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="e9c3a-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="e9c3a-109">제어판을 사용하여 사용자 정책 적용</span><span class="sxs-lookup"><span data-stu-id="e9c3a-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="e9c3a-110">제어판을 사용하여 사용자 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="e9c3a-111">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e9c3a-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e9c3a-113">왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성하려는 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="e9c3a-114">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e9c3a-115">보관 **정책에서 Lync Server 사용자** 편집에서 적용할 보관 사용자 정책을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="e9c3a-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e9c3a-116">이 **\<Automatic\>** 설정은 기본 서버 설치 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="e9c3a-117">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="e9c3a-118">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="e9c3a-119">사용자 정책을 사용하여 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9c3a-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="e9c3a-120">**Grant-CsArchivingPolicy** cmdlet을 사용하여 사용자 정책을 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e9c3a-121">다음 명령은 사용자별 보관 정책 RedmondArchivingPolicy를 Ken Myer라는 사용자에게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="e9c3a-122">이 명령은 등록자 풀에 있는 계정이 있는 모든 사용자에게 사용자당 보관 정책 RedmondArchivingPolicy를 atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="e9c3a-123">이 명령에 사용되는 Filter 매개 변수에 대한 자세한 내용은 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="e9c3a-124">다음 명령은 이전에 Ken Myer에게 할당된 사용자당 보관 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e9c3a-125">사용자당 정책이 제거된 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용하여 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="e9c3a-126">사이트 정책은 글로벌 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="e9c3a-127">자세한 내용은 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9c3a-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

