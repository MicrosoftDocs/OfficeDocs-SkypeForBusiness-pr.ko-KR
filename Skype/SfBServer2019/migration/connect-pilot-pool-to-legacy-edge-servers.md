---
title: 레거시 Edge 서버에 파일럿 풀 연결
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019을 배포한 후에는 사이트에 대 한 페더레이션 경로를 구성 해야 합니다. 레거시 설치에 사용 되는 페더레이션 경로를 사용 하기 위해서는이 경로를 사용 하도록 비즈니스용 Skype 서버 2019를 구성 해야 합니다.
ms.openlocfilehash: 20aacda86c6c49b319859d6f1c175ce6258caddb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191157"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="790cb-104">레거시 Edge 서버에 파일럿 풀 연결</span><span class="sxs-lookup"><span data-stu-id="790cb-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="790cb-105">비즈니스용 Skype 서버 2019을 배포한 후에는 사이트에 대 한 페더레이션 경로를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="790cb-106">레거시 설치에 사용 되는 페더레이션 경로를 사용 하기 위해서는이 경로를 사용 하도록 비즈니스용 Skype 서버 2019를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="790cb-107">비즈니스용 Skype Server 2019 사이트에서 레거시 배포의 디렉터 및 Edge 서버를 사용 하도록 설정 하려면 토폴로지 작성기를 사용 하 여 레거시 Edge 풀을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="790cb-108">토폴로지 작성기를 사용 하 여 레거시 Edge 풀을 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="790cb-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="790cb-109">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="790cb-110">**비즈니스용 Skype 서버** 노드 바로 아래에 있는 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="790cb-111">**작업** 메뉴에서 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="790cb-112">왼쪽 창에서 **페더레이션 경로**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="790cb-113">**사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택 하 고, 레거시 감독을 선택 하거나, 디렉터가 나열 되지 않으면 레거시에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="790cb-114">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="790cb-115">토폴로지 작성기의 비즈니스용 Skype 서버 2019 노드에서 **Standard edition server** 또는 **Enterprise Edition 프런트 엔드 풀**로 이동 하 여 해당 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="790cb-116">**연결**에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 옆에 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="790cb-117">목록에서 레거시에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="790cb-118">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="790cb-119">**토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="790cb-120">**작업** 메뉴에서 **토폴로지 게시**를 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="790cb-121">**게시 마법사** 가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="790cb-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

