---
title: 보관 서버 연결 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 보관 서버를 제거 하려면 연결 된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch 기기 및 Survivable Branch 서버에 대 한 종속성을 변경 하거나 선택 취소 해야 합니다. 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch 기기 및 Survivable Branch 서버의 속성을 편집 하 여 종속성을 제거 합니다. 종속성을 지우고 토폴로지 작성기에서 서버를 삭제 하면 토폴로지 작성기의 관련 데이터베이스 저장소 개체도 삭제 된다는 알림이 표시 됩니다.
ms.openlocfilehash: 52bba22f678bb4aee1ce406613ce19bb686a78c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197171"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="80ab3-105">보관 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="80ab3-105">Remove the Archiving server association</span></span>

<span data-ttu-id="80ab3-106">보관 서버를 제거 하려면 연결 된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch 기기 및 Survivable Branch 서버에 대 한 종속성을 변경 하거나 선택 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="80ab3-107">프런트 엔드 풀, 프론트 엔드 서버, Survivable Branch 기기의 속성을 편집 하 고 Survivable Branch 서버에서 종속성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="80ab3-108">종속성을 지우고 토폴로지 작성기에서 서버를 삭제 하면 토폴로지 작성기의 관련 데이터베이스 저장소 개체도 삭제 된다는 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="80ab3-109">보관 서버 연결을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="80ab3-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="80ab3-110">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="80ab3-111">레거시 설치 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="80ab3-112">토폴로지 작성기에서 보관 서버가 정의 된 위치에 따라 **Enterprise Edition 프런트 엔드 풀**, **Standard Edition 프런트 엔드 서버**또는 **분기 사이트**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="80ab3-113">연결 된 Survivable Branch 서버가 있는 경우 **분기**사이트를 확장 하 고 분기 사이트 이름을 확장 한 다음 **Survivable branch 기기**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80ab3-114">사용자 인터페이스의 **Survivable Branch 기기** 는 Survivable branch 서버와 Survivable branch 기기 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="80ab3-115">보관 서버와 연결 된 풀, 서버 또는 장치를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="80ab3-116">**속성 편집**의 **일반** > **연결**에서 **보관 서버 연결** 확인란의 선택을 취소 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="80ab3-117">제거 하려는 보관 서버와 연결 된 다른 풀, 서버 또는 장치에 대해 앞의 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="80ab3-118">보관 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="80ab3-119">**종속 저장소 삭제**에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="80ab3-120">토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 비즈니스용 Skype 서버 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab3-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

