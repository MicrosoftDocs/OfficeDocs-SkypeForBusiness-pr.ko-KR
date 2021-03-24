---
title: 비즈니스용 Skype 서버에서 PIN 정책 삭제
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '요약: 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 삭제합니다.'
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096794"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="6928d-103">비즈니스용 Skype 서버에서 PIN 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="6928d-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="6928d-104">**요약:** 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="6928d-105">PIN(개인 식별 번호) 정책을 삭제하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6928d-106">전역 PIN 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="6928d-107">비즈니스용 Skype 서버 제어판에서 PIN 정책을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="6928d-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="6928d-108">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="6928d-109">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6928d-110">왼쪽 탐색 모음에서 **보안** 을 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="6928d-111">**PIN 정책** 페이지의 검색 필드에 삭제할 정책의 이름 전부 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="6928d-112">정책 목록에서 원하는 정책을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="6928d-113">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6928d-114">cmdlet을 사용하여 PIN Windows PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="6928d-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6928d-115">PIN 정책은 cmdlet 및 Windows PowerShell 사용하여 삭제할 Remove-CsPinPolicy 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="6928d-116">비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6928d-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6928d-117">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="6928d-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6928d-118">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="6928d-119">특정 PIN 정책을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="6928d-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="6928d-120">이 명령은 ID RedmondPinPolicy가 포함된 PIN 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="6928d-121">사이트 범위에 적용된 모든 PIN 정책을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="6928d-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="6928d-122">이 명령은 사이트 범위에 구성된 모든 PIN 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="6928d-123">공통 패턴 사용을 허용하는 모든 PIN 정책을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="6928d-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="6928d-124">그리고 이 명령은 공통 패턴 사용을 허용하는 모든 PIN 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6928d-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="6928d-125">자세한 내용은 [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6928d-125">For more information, see the help topic for the [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
