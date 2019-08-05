---
title: 비즈니스용 Skype 서버에서 사용자에 게 보관 정책 적용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '요약: 비즈니스용 Skype 서버에서 사용자에 게 보관 정책을 할당 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 895a7fac34fcac0a4a7e39756796f6b7d2fc6377
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189360"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="698ef-103">비즈니스용 Skype 서버에서 사용자에 게 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="698ef-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="698ef-104">**요약:** 비즈니스용 Skype 서버에서 사용자에 게 보관 정책을 할당 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="698ef-105">비즈니스용 Skype Server에 속한 사용자에 대해 보관 하기 위해 하나 이상의 사용자 정책을 만든 경우 해당 사용자 또는 사용자 그룹에 적절 한 정책을 적용 하 여 특정 사용자에 대 한 보관 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="698ef-106">예를 들어 내부 통신 보관을 지원 하기 위한 정책을 만드는 경우 사용자의 비즈니스용 Skype 서버 통신 보관을 지원 하기 위해 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="698ef-107">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하면 exchange 원본 위치 유지 정책에서 Exchange를 사용 하는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="698ef-108">자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md) 및 비즈니스용 [skype 서버에 대 한 Exchange 저장소 통합 구성](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="698ef-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="698ef-109">제어판을 사용 하 여 사용자 정책 적용</span><span class="sxs-lookup"><span data-stu-id="698ef-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="698ef-110">제어판을 사용 하 여 사용자 정책을 적용 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="698ef-111">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="698ef-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="698ef-113">왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 구성 하려는 사용자 계정을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="698ef-114">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="698ef-115">**보관 정책**에서 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="698ef-116">자동 설정은 기본 서버 설치 설정을 적용 합니다. \*\* \<\> \*\*</span><span class="sxs-lookup"><span data-stu-id="698ef-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="698ef-117">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="698ef-118">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="698ef-119">Windows PowerShell을 사용 하 여 사용자 정책 적용</span><span class="sxs-lookup"><span data-stu-id="698ef-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="698ef-120">Windows PowerShell **CsArchivingPolicy** cmdlet을 사용 하 여 사용자 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="698ef-121">다음 명령을 사용 하 여 사용자 단위 보관 정책을 RedmondArchivingPolicy: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="698ef-122">이 명령은 등록자 풀 atl-cs-001.contoso.com에 속한 계정이 있는 모든 사용자에 대해 사용자별 보관 정책 RedmondArchivingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="698ef-123">이 명령에 사용 된 필터 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="698ef-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="698ef-124">다음 명령을 사용 하 여 이전에: 진구 Myer에 할당 된 사용자 단위 보관 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="698ef-125">사용자별 정책이 제거 되 면: 진구 Myer는 글로벌 정책을 사용 하 여 자동으로 관리 되거나 (있는 경우) 로컬 사이트 정책이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="698ef-126">사이트 정책이 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="698ef-126">A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="698ef-127">자세한 내용은 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="698ef-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

