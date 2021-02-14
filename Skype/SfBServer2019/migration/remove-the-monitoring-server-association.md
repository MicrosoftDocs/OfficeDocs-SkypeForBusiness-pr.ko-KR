---
title: 모니터링 서버 연결 제거
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
description: 모니터링 서버를 제거하려면 연결된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server에 대한 종속성의 변경 또는 선택을 취소해야 합니다. 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server의 속성을 편집하여 종속성 제거 토폴로지 작성기에서 종속성의 선택을 취소하고 서버를 삭제하면 토폴로지 작성기에서 연결된 데이터베이스 저장소 개체도 삭제될 것임이 통보됩니다.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753420"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="d4acf-105">모니터링 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="d4acf-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="d4acf-106">모니터링 서버를 제거하려면 연결된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server에 대한 종속성의 변경 또는 선택을 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="d4acf-107">종속성 제거를 위해 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server의 속성을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="d4acf-108">토폴로지 작성기에서 종속성의 선택을 취소하고 서버를 삭제하면 토폴로지 작성기에서 연결된 데이터베이스 저장소 개체도 삭제될 것임이 통보됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="d4acf-109">모니터링 서버 연결을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="d4acf-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="d4acf-110">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기 를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="d4acf-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="d4acf-111">레거시 설치 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="d4acf-112">토폴로지 작성기에서 모니터링 서버가 정의된 위치에 따라 Enterprise  **Edition** 프런트 엔드 풀, **Standard Edition** 프런트 엔드 서버 또는 분기 사이트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="d4acf-113">Survivable Branch Server가 연결된 경우 분기 사이트를 확장하고 **분기** 사이트 이름을 확장한 다음 **Survivable Branch Appliance를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="d4acf-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4acf-114">**사용자 인터페이스의 Survivable Branch Appliance는** Survivable Branch Server 및 Survivable Branch Appliance 둘 다에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="d4acf-115">모니터링 서버와 연결된 풀, 서버 또는 장치를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d4acf-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="d4acf-116">속성 **편집의** **일반** 연결에서 모니터링 서버 연결 확인란의 선택을 취소하고  >    확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d4acf-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="d4acf-117">모니터링 서버와 연결된 다른 풀, 서버 또는 장치에 대해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="d4acf-118">모니터링 서버를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d4acf-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="d4acf-119">**종속 저장소 삭제** 에서 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="d4acf-120">토폴로지 게시, 복제 상태 확인 및 필요한 경우 비즈니스용 Skype 서버 배포 마법사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4acf-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

