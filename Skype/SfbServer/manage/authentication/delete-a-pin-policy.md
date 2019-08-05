---
title: 비즈니스용 Skype 서버에서 핀 정책 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '요약: 비즈니스용 Skype 서버용 사용자의 전화 접속 회의 PIN을 삭제 합니다.'
ms.openlocfilehash: 2f42531480ac4099d574a21a96f1954abc70d1d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189669"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="5457d-103">비즈니스용 Skype 서버에서 핀 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="5457d-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="5457d-104">**요약:** 비즈니스용 Skype 서버용 사용자의 전화 접속 회의 PIN을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="5457d-105">PIN (개인 식별 번호) 정책을 삭제 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="5457d-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5457d-106">글로벌 PIN 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="5457d-107">비즈니스용 Skype Server 제어판에서 핀 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="5457d-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5457d-108">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="5457d-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="5457d-109">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5457d-110">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5457d-111">**PIN 정책** 페이지에서 검색 필드에 삭제 하려는 정책의 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="5457d-112">정책 목록에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="5457d-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5457d-114">Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거</span><span class="sxs-lookup"><span data-stu-id="5457d-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5457d-115">Windows PowerShell 및 CsPinPolicy cmdlet을 사용 하 여 PIN 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="5457d-116">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5457d-117">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5457d-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5457d-118">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="5457d-119">특정 PIN 정책 제거</span><span class="sxs-lookup"><span data-stu-id="5457d-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="5457d-120">이 명령은 Id RedmondPinPolicy를 사용 하 여 PIN 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="5457d-121">사이트 범위에 적용 된 모든 PIN 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="5457d-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="5457d-122">이 명령은 사이트 범위에서 구성 된 PIN 정책을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="5457d-123">공통 패턴을 사용할 수 있는 PIN 정책을 모두 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="5457d-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="5457d-124">이 항목은 일반 패턴을 사용할 수 있는 PIN 정책 (: G)을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5457d-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="5457d-125">자세한 내용은 [제거 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5457d-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

