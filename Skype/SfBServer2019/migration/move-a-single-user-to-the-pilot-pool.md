---
title: 단일 사용자를 시험 운용 풀로 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 skype server 2019 제어판 또는 비즈니스용 Skype Server 2019 Management Shell을 사용 하 여 사용자를 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다. 아래 예제에서 레지스트라 풀 열에는 레거시 풀이 pool01.contoso.net,이 풀에는 6 명의 사용자가 모두 연결 되어 있습니다. 비즈니스용 skype server 2019 제어판 및 비즈니스용 skype Server Management Shell을 사용 하 여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동 하려면 다음 절차를 사용 합니다.
ms.openlocfilehash: 23ce56f8bcf759aeeaa9e9a9b64820958c656c6a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196949"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="d3065-105">단일 사용자를 시험 운용 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="d3065-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="d3065-106">비즈니스용 skype server 2019 제어판 또는 비즈니스용 Skype Server 2019 Management Shell을 사용 하 여 사용자를 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="d3065-107">아래 예제에서 **레지스트라 풀** 열에는 레거시 풀이 **pool01.contoso.net** ,이 풀에는 6 명의 사용자가 모두 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="d3065-108">비즈니스용 skype server 2019 제어판 및 비즈니스용 skype Server Management Shell을 사용 하 여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="d3065-109">비즈니스용 Skype 서버 2019 제어판을 사용 하 여 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="d3065-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="d3065-110">RTCUniversalServerAdmins 그룹의 구성원 이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="d3065-111">**비즈니스용 Skype Server 제어판을**엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="d3065-112">**사용자**를 클릭 하 고 **검색**을 클릭 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="d3065-113">비즈니스용 Skype Server 2019 풀로 이동 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d3065-114">이 예제에서는 사용자 Sara 아를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="d3065-115">**작업** 메뉴에서 **선택한 사용자 이동을 선택 하 여 그룹으로 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="d3065-116">드롭다운 목록에서 비즈니스용 Skype 서버 2019 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="d3065-117">**작업**을 클릭 한 다음 **선택한 사용자 이동을 클릭 하 여 그룹을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="d3065-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="d3065-119">사용자의 **등록자 그룹** 열에 사용자가 성공적으로 이동 했음을 나타내는 비즈니스용 Skype 서버 2019 풀이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="d3065-120">비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="d3065-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="d3065-121">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="d3065-122">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="d3065-123">그런 다음 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="d3065-124">이제 **RegistrarPool** Id는 비즈니스용 Skype 서버 2019 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d3065-125">이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d3065-126">**Get-csuser** cmdlet에 대 한 자세한 내용을 보려면 **Get-help-Csuser-Detailed** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3065-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

