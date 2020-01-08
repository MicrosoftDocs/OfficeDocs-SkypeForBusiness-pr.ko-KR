---
title: 'Lync Server 2013: 풀 배포 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a1dc68b8dbe6285cdf4b7e9c21c873caaf730d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="ad14e-102">Lync Server 2013에서 풀 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="ad14e-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad14e-103">_**마지막으로 수정한 주제:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="ad14e-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="ad14e-104">다음 절차에서는 프런트 엔드 풀의 배포를 테스트 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="ad14e-105">풀 배포를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="ad14e-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="ad14e-106">Active Directory 컴퓨터와 사용자를 사용 하 여 lync server 2013 제어판에 설치 되어 있는 Lync Server 2013 배포에 대 한 관리자 역할의 Active Directory 사용자 개체를 **csadministrator** 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ad14e-107">적절 한 사용자 및 그룹을 CsAdministors 그룹에 추가 하지 않으면 Lync Server 제어판을 열 때 오류가 표시 되며,이는 "허용 되지 않음: ' 사용자가 RBAC (역할 기반 액세스 제어) 권한 부여 오류로 인해 액세스가 거부 됨을 나타내는"입니다. "</span><span class="sxs-lookup"><span data-stu-id="ad14e-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="ad14e-108">사용자 개체가 현재 로그온 되어 있으면 로그 오프 한 다음 다시 로그온 하 여 새 그룹 할당을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad14e-109">사용자 계정은 Lync Server 2013을 실행 하는 서버의 로컬 관리자가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="ad14e-110">관리자 계정을 사용 하 여 Lync Server 제어판이 설치 되어 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="ad14e-111">Lync Server 제어판을 시작한 다음 메시지가 표시 되 면 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="ad14e-112">Lync Server 제어판에 배포 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="ad14e-113">왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 서비스 상태가 녹색 화살표가 있는 컴퓨터를 표시 하 고 복제 상태에 대 한 녹색 확인 표시가 배포 되어 온라인 상태가 된 각 Lync server 역할 옆에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="ad14e-114">왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 **사용자 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="ad14e-115">**새 Lync Server 사용자** 페이지에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="ad14e-116">찾으려는 개체에 대 한 검색 매개 변수를 정의 하려면 **Active Directory에서 선택** 페이지에서 **검색**을 선택한 다음 필요에 따라 **필터 추가**를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="ad14e-117">**Ldap 검색** 을 선택 하 고 ldap 식을 입력 하 여 반환 되는 개체를 필터링 하거나 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="ad14e-118">검색 옵션을 결정 한 후에는 clink **찾기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="ad14e-119">검색 결과 창에서이 검색 세션의 모든 개체를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="ad14e-120">**새 Lync Server 사용자** 페이지에서 선택한 개체는 **사용자가** 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="ad14e-121">**풀에 사용자 할당** 목록에서 개체를 배치할 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="ad14e-122">다음은 개체를 구성 하는 여러 가지 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="ad14e-123">**사용자의 SIP URI 생성**</span><span class="sxs-lookup"><span data-stu-id="ad14e-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="ad14e-124">**통신**</span><span class="sxs-lookup"><span data-stu-id="ad14e-124">**Telephony**</span></span>
    
      - <span data-ttu-id="ad14e-125">**줄 URI**</span><span class="sxs-lookup"><span data-stu-id="ad14e-125">**Line URI**</span></span>
    
      - <span data-ttu-id="ad14e-126">**회의 정책**</span><span class="sxs-lookup"><span data-stu-id="ad14e-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="ad14e-127">**클라이언트 버전 정책**</span><span class="sxs-lookup"><span data-stu-id="ad14e-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="ad14e-128">**고정 정책**</span><span class="sxs-lookup"><span data-stu-id="ad14e-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="ad14e-129">**외부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="ad14e-129">**External access policy**</span></span>
    
      - <span data-ttu-id="ad14e-130">**보관 정책**</span><span class="sxs-lookup"><span data-stu-id="ad14e-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="ad14e-131">**위치 정책**</span><span class="sxs-lookup"><span data-stu-id="ad14e-131">**Location policy**</span></span>
    
      - <span data-ttu-id="ad14e-132">**클라이언트 정책**</span><span class="sxs-lookup"><span data-stu-id="ad14e-132">**Client policy**</span></span>
    
    <span data-ttu-id="ad14e-133">기본 기능을 테스트 하기 위해 **사용자의 SIP URI 생성** 설정 (구성의 다른 옵션에서 기본 설정을 사용 함)에 대해 원하는 옵션을 선택한 다음 **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="ad14e-134">사용 **가능** 열에 확인 표시가 표시 된 요약 페이지가 표시 되 고 이제 해당 개체를 사용할 준비가 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="ad14e-135">**SIP 주소** 열에는 사용자 로그인 구성에 필요한 주소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="ad14e-136">도메인에 가입 된 컴퓨터와 도메인의 다른 컴퓨터에 대 한 다른 사용자에 게 한 명의 사용자를 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="ad14e-137">두 클라이언트 컴퓨터 각각에 Lync 2013를 설치한 다음 두 사용자가 Lync Server 2013에 로그인 하 여 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad14e-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad14e-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad14e-138">See Also</span></span>


[<span data-ttu-id="ad14e-139">Lync Server 2013에서 클라이언트 및 장치 배포</span><span class="sxs-lookup"><span data-stu-id="ad14e-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

