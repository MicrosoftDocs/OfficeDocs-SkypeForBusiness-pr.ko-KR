---
title: 비즈니스용 Skype 서버에서 기존 보관 정책 변경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '요약: 비즈니스용 Skype 서버에 대 한 사용자 보관 정책을 변경 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 00f22b9afa5332bd7075b03823d321d35a0e4b8b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992775"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="fbd57-103">비즈니스용 Skype 서버에서 기존 보관 정책 변경</span><span class="sxs-lookup"><span data-stu-id="fbd57-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="fbd57-104">**요약:** 비즈니스용 Skype 서버에 대 한 사용자 보관 정책을 변경 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="fbd57-105">비즈니스용 Skype 서버를 처음 배포 하는 경우 배포의 사용자에 대해 보관을 구현 하는 방법을 결정 하는 초기 보관 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="fbd57-106">이 항목에서는 정책을 관리 하 고 수정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="fbd57-107">제어판을 사용 하 여 보관 정책 변경</span><span class="sxs-lookup"><span data-stu-id="fbd57-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="fbd57-108">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="fbd57-109">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="fbd57-110">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="fbd57-111">정책 목록에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="fbd57-112">전체 배포에 대 한 정책을 변경 하려면 정책 목록에서 **전역** 을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="fbd57-113">단일 사이트의 정책을 변경 하려면 정책 목록에서 사이트 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="fbd57-114">단일 사용자 또는 사용자 그룹에 대 한 정책을 변경 하려면 정책 목록에서 사용자 또는 사용자 그룹 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="fbd57-115">**보관 정책 편집** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="fbd57-116">정책에 대 한 내부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="fbd57-117">정책에 대해 외부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="fbd57-118">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fbd57-119">사용자 정책 설정은 정책을 적용 하는 특정 사용자 및 사용자 그룹에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="fbd57-120">자세한 내용은 [비즈니스용 Skype 서버에서 사용자에 게 보관 정책 적용](apply-a-policy-to-users.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbd57-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="fbd57-121">Windows PowerShell을 사용 하 여 보관 정책 변경</span><span class="sxs-lookup"><span data-stu-id="fbd57-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="fbd57-122">Windows PowerShell **CsArchivingPolicy** cmdlet을 사용 하 여 보관 정책을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="fbd57-123">보관 정책 사용</span><span class="sxs-lookup"><span data-stu-id="fbd57-123">Enable archiving policies</span></span>

<span data-ttu-id="fbd57-124">내부 통신 세션 보관을 사용 하도록 설정 하려면 ArchiveInternal 매개 변수의 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="fbd57-125">외부 통신 세션 보관을 사용 하도록 설정 하려면 ArchiveExternal 매개 변수의 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="fbd57-126">내부 및 외부 통신 세션을 모두 보관할 수 있도록 하려면 ArchiveInternal 및 ArchiveExternal 매개 변수의 값을 모두 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="fbd57-127">보관 정책 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="fbd57-127">Disable archiving policies</span></span>

<span data-ttu-id="fbd57-128">보관을 완전히 사용 하지 않도록 설정 하려면 ArchiveInternal 및 ArchiveExternal 매개 변수 값을 모두 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd57-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
