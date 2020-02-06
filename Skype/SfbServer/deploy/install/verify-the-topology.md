---
title: 비즈니스용 Skype 서버에서 토폴로지 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '요약: 비즈니스용 Skype 서버 토폴로지와 Active Directory 서버가 예상 대로 작동 하는지 확인 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: aa631e5b08ff8cbe9cb6db17009f286dcc975679
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791716"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="caa7a-104">비즈니스용 Skype 서버에서 토폴로지 확인</span><span class="sxs-lookup"><span data-stu-id="caa7a-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="caa7a-105">**요약:** 비즈니스용 Skype 서버 토폴로지와 Active Directory 서버가 예상 대로 작동 하는지 확인 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="caa7a-106">[Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="caa7a-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="caa7a-107">토폴로지가 게시 되 고 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템 구성 요소가 설치 된 후 토폴로지가 예상 대로 작동 하는지 확인할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="caa7a-108">여기에는 전체 도메인이 도메인에서 비즈니스용 Skype를 사용할 수 있도록 모든 Active Directory 서버로 구성이 전파 되었음을 확인 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="caa7a-109">1 ~ 5 단계는 순서에 관계 없이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="caa7a-110">그러나 6, 7, 8 단계를 순서 대로 수행 하 고 다이어그램에 명시 된 대로 1 ~ 5 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="caa7a-111">토폴로지 확인은 8 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-111">Verifying the topology is step 8 of 8.</span></span>
  
![개요 다이어그램.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="caa7a-113">프런트 엔드 풀 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="caa7a-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="caa7a-114">마지막 단계는 프런트 엔드 풀을 테스트 하 고 비즈니스용 Skype 클라이언트가 서로 통신할 수 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="caa7a-115">사용자 추가 및 클라이언트 연결 확인</span><span class="sxs-lookup"><span data-stu-id="caa7a-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="caa7a-116">Active Directory 컴퓨터 및 사용자를 사용 하 여 비즈니스용 Skype 서버 배포에 대 한 관리자 역할의 Active Directory 사용자 개체 (비즈니스용 Skype Server 제어판이 설치 되어 있는 경우)를 **csadministrator** 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="caa7a-117">CsAdministors 그룹에 적절 한 사용자 및 그룹을 추가 하지 않으면 "권한이 없음: 역할 기반 액세스 제어 (RBAC) 권한 부여 오류로 인해 액세스가 거부 됨을 나타내는 비즈니스용 Skype 서버 제어판을 열 때 오류가 표시 됩니다. ."</span><span class="sxs-lookup"><span data-stu-id="caa7a-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="caa7a-118">사용자 개체가 현재 로그온 되어 있으면 로그 오프 한 다음 다시 로그온 하 여 새 그룹 할당을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="caa7a-119">사용자 계정은 비즈니스용 Skype 서버를 실행 하는 서버의 로컬 관리자가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="caa7a-120">관리 계정을 사용 하 여 비즈니스용 Skype 서버 제어판이 설치 되어 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="caa7a-121">비즈니스용 Skype Server 제어판을 시작 하 고 메시지가 표시 되 면 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="caa7a-122">비즈니스용 Skype Server 제어판에 배포 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="caa7a-123">왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 서비스 상태가 녹색 화살표가 있는 컴퓨터를 표시 하 고 복제 상태에 대 한 녹색 확인 표시가 배포 되어 온라인 상태가 된 각 비즈니스용 Skype 서버 역할 옆에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="caa7a-124">왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 **사용자 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="caa7a-125">**새 비즈니스용 Skype 서버 사용자** 페이지에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="caa7a-126">찾으려는 개체에 대 한 검색 매개 변수를 정의 하려면 **Active Directory에서 선택** 페이지에서 **검색**을 선택한 다음 필요에 따라 **필터 추가**를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="caa7a-127">**Ldap 검색** 을 선택 하 고 ldap 식을 입력 하 여 반환 되는 개체를 필터링 하거나 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="caa7a-128">검색 옵션을 결정 한 후 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="caa7a-129">검색 결과 창에서 추가 하려는 사용자를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="caa7a-130">**새 비즈니스용 Skype Server 사용자** 페이지에서 선택한 사용자가 **사용자에 게** 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="caa7a-131">**풀에 사용자 할당** 목록에서 사용자가 상주해 야 하는 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="caa7a-132">다음은 개체를 구성 하는 데 사용할 수 있는 옵션의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="caa7a-133">**사용자의 SIP URI 생성**</span><span class="sxs-lookup"><span data-stu-id="caa7a-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="caa7a-134">**통신**</span><span class="sxs-lookup"><span data-stu-id="caa7a-134">**Telephony**</span></span>
    
    - <span data-ttu-id="caa7a-135">**줄 URI**</span><span class="sxs-lookup"><span data-stu-id="caa7a-135">**Line URI**</span></span>
    
    - <span data-ttu-id="caa7a-136">**회의 정책**</span><span class="sxs-lookup"><span data-stu-id="caa7a-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="caa7a-137">**클라이언트 버전 정책**</span><span class="sxs-lookup"><span data-stu-id="caa7a-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="caa7a-138">**고정 정책**</span><span class="sxs-lookup"><span data-stu-id="caa7a-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="caa7a-139">**외부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="caa7a-139">**External access policy**</span></span>
    
    - <span data-ttu-id="caa7a-140">**보관 정책**</span><span class="sxs-lookup"><span data-stu-id="caa7a-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="caa7a-141">**위치 정책**</span><span class="sxs-lookup"><span data-stu-id="caa7a-141">**Location policy**</span></span>
    
    - <span data-ttu-id="caa7a-142">**클라이언트 정책**</span><span class="sxs-lookup"><span data-stu-id="caa7a-142">**Client policy**</span></span>
    
    <span data-ttu-id="caa7a-143">기본 기능을 테스트 하려면 **사용자의 SIP URI 생성** 설정 (구성의 다른 옵션)에 대해 선호 하는 옵션을 선택한 다음 그림에 표시 된 대로 **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![제어판에서 사용자를 활성화 합니다.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="caa7a-145">**사용할 수** 있는 열에 확인 표시가 표시 된 요약 페이지가 표시 되 고 사용자가 설정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="caa7a-146">**SIP 주소** 열에는 사용자 로그인 구성에 필요한 주소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![사용자가 비즈니스용 Skype 서버 제어판에 추가 되었습니다.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="caa7a-148">도메인에 가입 된 컴퓨터와 도메인의 다른 컴퓨터에 있는 다른 사용자에 게 한 명의 사용자를 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="caa7a-149">두 클라이언트 컴퓨터 각각에 비즈니스용 Skype 클라이언트를 설치한 다음 두 사용자가 비즈니스용 Skype 서버에 로그인 할 수 있고 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa7a-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

