---
title: 파일럿 풀로 단일 사용자 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용하여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 사용자를 이동할 수 있습니다. 아래 예제에서 등록자 풀 열에서 pool01.contoso.net 레거시 풀이 있으며 이러한 6명 모두 이 풀에 연결됩니다. 다음 절차에 따라 비즈니스용 Skype 서버 2019 제어판 및 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동합니다.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752510"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="00949-105">파일럿 풀로 단일 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="00949-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="00949-106">비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용하여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00949-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="00949-107">아래 예제에서 등록자  풀 열에서  pool01.contoso.net 레거시 풀이 있으며 이러한 6명 모두 이 풀에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="00949-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="00949-108">다음 절차에 따라 비즈니스용 Skype 서버 2019 제어판 및 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="00949-109">비즈니스용 Skype 서버 2019 제어판을 사용하여 사용자를 이동</span><span class="sxs-lookup"><span data-stu-id="00949-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="00949-110">RTCUniversalServerAdmins 그룹의 구성원이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원인 계정으로 프런트 엔드 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="00949-111">비즈니스용 **Skype 서버 제어판을 니다.**</span><span class="sxs-lookup"><span data-stu-id="00949-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="00949-112">사용자, **검색을** 클릭한 다음 찾기를 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="00949-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="00949-113">비즈니스용 Skype 서버 2019 풀로 이동할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="00949-114">이 예에서는 Sara Davis를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="00949-115">**동작** 메뉴에서 **선택한 사용자를 풀로 이동** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="00949-116">드롭다운 목록에서 비즈니스용 Skype 서버 2019 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="00949-117">**동작** 을 클릭하고 **선택한 사용자를 풀로 이동** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="00949-118">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="00949-119">사용자의 등록자 풀 열에 이제 사용자가 성공적으로 이동된 비즈니스용 Skype 서버 2019 풀이 포함되어 있는지 확인해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="00949-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="00949-120">비즈니스용 Skype 서버 2019 관리 셸을 사용하여 사용자를 이동</span><span class="sxs-lookup"><span data-stu-id="00949-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="00949-121">비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00949-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="00949-122">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="00949-123">그런 다음 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="00949-124">**RegistrarPool** ID는 이제 비즈니스용 Skype 서버 2019 풀을 포인트로 합니다.</span><span class="sxs-lookup"><span data-stu-id="00949-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="00949-125">이 ID가 있으면 사용자가 성공적으로 이동되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00949-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="00949-126">**Get-CsUser** cmdlet에 대한 자세한 내용은 **Get-Help Get-CsUser -Detailed를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="00949-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

