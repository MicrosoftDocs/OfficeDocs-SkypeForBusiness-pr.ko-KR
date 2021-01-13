---
title: 비즈니스용 Skype 서버에서 기존 보관 정책 변경
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '요약: 비즈니스용 Skype 서버의 사용자 보관 정책을 변경하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817708"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="d17ed-103">비즈니스용 Skype 서버에서 기존 보관 정책 변경</span><span class="sxs-lookup"><span data-stu-id="d17ed-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="d17ed-104">**요약:** 비즈니스용 Skype 서버에 대한 사용자 보관 정책을 변경하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="d17ed-105">비즈니스용 Skype 서버를 처음 배포할 때 배포의 사용자에 대해 보관이 구현되는 방법을 결정하는 초기 보관 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="d17ed-106">이 항목에서는 정책을 관리하고 수정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="d17ed-107">제어판을 사용하여 보관 정책 변경</span><span class="sxs-lookup"><span data-stu-id="d17ed-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="d17ed-108">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d17ed-109">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d17ed-110">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d17ed-111">정책 목록에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="d17ed-112">전체 배포에 대한 정책을 변경하려면 정책 목록에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="d17ed-113">단일 사이트에 대한 정책을 변경하려면 정책 목록에서 사이트 이름을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="d17ed-114">단일 사용자 또는 사용자 그룹에 대한 정책을 변경하려면 정책 목록에서 사용자 또는 사용자 그룹 이름을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d17ed-115">**보관 정책 편집** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="d17ed-116">정책에 내부 보관을 사용하거나 사용하지 않도록 설정하려면 **내부 통신 보관** 확인란을 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d17ed-117">정책에 외부 보관을 사용하거나 사용하지 않도록 설정하려면 **외부 통신 보관** 확인란을 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="d17ed-118">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d17ed-119">사용자 정책 설정은 관리자가 정책을 적용한 특정 사용자 및 사용자 그룹에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="d17ed-120">자세한 내용은 비즈니스용 Skype 서버의 사용자에게 보관 정책 [적용을 참조하세요.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="d17ed-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="d17ed-121">보관 정책을 사용하여 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d17ed-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="d17ed-122">**Set-CsArchivingPolicy** cmdlet을 사용하여 보관 정책을 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="d17ed-123">보관 정책 사용</span><span class="sxs-lookup"><span data-stu-id="d17ed-123">Enable archiving policies</span></span>

<span data-ttu-id="d17ed-124">내부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveInternal 매개 변수의 값을 True($True)</span><span class="sxs-lookup"><span data-stu-id="d17ed-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="d17ed-125">외부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveExternal 매개 변수의 값을 True($True)</span><span class="sxs-lookup"><span data-stu-id="d17ed-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="d17ed-126">내부 및 외부 통신 세션 모두의 보관을 사용하도록 설정하려면 ArchiveInternal 및 ArchiveExternal 매개 변수의 값을 True로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d17ed-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="d17ed-127">보관 정책 사용 안</span><span class="sxs-lookup"><span data-stu-id="d17ed-127">Disable archiving policies</span></span>

<span data-ttu-id="d17ed-128">보관을 모두 사용하지 않도록 설정하기 위해 ArchiveInternal 및 ArchiveExternal 매개 변수의 값을 False($False)</span><span class="sxs-lookup"><span data-stu-id="d17ed-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
