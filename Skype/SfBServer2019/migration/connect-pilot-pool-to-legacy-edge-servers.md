---
title: 레거시 에지 서버에 파일럿 풀 연결
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
description: 비즈니스용 Skype 서버 2019를 배포한 후 사이트에 대한 페더링 경로를 구성해야 합니다. 레거시 설치에서 사용 중이고 있는 페더타 경로를 사용하려면 이 경로를 사용하도록 비즈니스용 Skype 서버 2019를 구성해야 합니다.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753928"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="43eee-104">레거시 에지 서버에 파일럿 풀 연결</span><span class="sxs-lookup"><span data-stu-id="43eee-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="43eee-105">비즈니스용 Skype 서버 2019를 배포한 후 사이트에 대한 페더링 경로를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="43eee-106">레거시 설치에서 사용 중이고 있는 페더타 경로를 사용하려면 이 경로를 사용하도록 비즈니스용 Skype 서버 2019를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="43eee-107">비즈니스용 Skype 서버 2019 사이트에서 레거시 배포의 Director 및 에지 서버를 사용하도록 설정하려면 토폴로지 작성기에서 레거시 에지 풀을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="43eee-108">토폴로지 작성기를 사용하여 레거시 에지 풀을 연결하려면</span><span class="sxs-lookup"><span data-stu-id="43eee-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="43eee-109">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="43eee-110">비즈니스용 Skype 서버 노드 바로 아래에 있는 **사이트를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="43eee-111">**동작** 메뉴에서 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="43eee-112">왼쪽 창에서 **페더레이션 경로** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="43eee-113">사이트 **페더ation** 경로 할당 아래에서 **SIP** 페더ation 사용을 선택한 다음 레거시 Director 또는 레거시 에지 서버가 나열되지 않은 경우 레거시 에지 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="43eee-114">**확인** 을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="43eee-115">토폴로지 작성기에서 비즈니스용 Skype 서버 2019 노드에서 **Standard Edition 서버** 또는 Enterprise **Edition** 프런트 엔드 풀로 이동한 다음 풀을 마우스 오른쪽 단추로 클릭한 다음 속성 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="43eee-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="43eee-116">**연결** 에서 **에지 풀 연결(미디어 구성 요소)** 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="43eee-117">목록에서 레거시 에지 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="43eee-118">**확인** 을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="43eee-119">**토폴로지 작성기에서** 최상위 노드인 비즈니스용 **Skype 서버를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43eee-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="43eee-120">**동작** 메뉴에서 **토폴로지 게시** 를 클릭하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="43eee-121">**게시 마법사** 가 완료되면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="43eee-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

