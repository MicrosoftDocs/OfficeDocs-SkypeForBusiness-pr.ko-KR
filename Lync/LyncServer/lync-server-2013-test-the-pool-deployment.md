---
title: 'Lync Server 2013: 풀 배포 테스트'
description: 'Lync Server 2013: 풀 배포를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576044"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="c1da4-103">Lync Server 2013에서 풀 배포 테스트</span><span class="sxs-lookup"><span data-stu-id="c1da4-103">Test the pool deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1da4-104">_**마지막으로 수정 된 항목:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="c1da4-104">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="c1da4-105">다음 절차에서는 프런트 엔드 풀의 배포를 테스트 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-105">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="c1da4-106">풀 배포를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="c1da4-106">To test the pool deployment</span></span>

1.  <span data-ttu-id="c1da4-107">Active Directory 컴퓨터 및 사용자를 사용 하 여 lync server 2013 제어판이 설치 된 경우의 관리자 2013 역할에 해당 하는 Active Directory 사용자 개체를 **csadministrator** 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1da4-108">CsAdministors 그룹에 적절 한 사용자 및 그룹을 추가 하지 않으면 Lync Server 제어판을 여는 경우 "권한이 없음: ' 허용 되지 않음 ' 권한이 있는 RBAC (역할 기반 액세스 제어) 권한 부여 오류로 인해 액세스가 거부 됨을 나타내는 오류 메시지가 표시 됩니다."</span><span class="sxs-lookup"><span data-stu-id="c1da4-108">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="c1da4-109">사용자 개체가 현재 로그온되어 있는 경우 로그오프하고 다시 로그온하여 새 그룹 지정을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-109">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1da4-110">사용자 계정은 Lync Server 2013를 실행 하는 서버의 로컬 관리자 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-110">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="c1da4-111">관리 계정을 사용 하 여 Lync Server 제어판이 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="c1da4-112">Lync Server 제어판을 시작한 다음 메시지가 표시 되 면 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-112">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="c1da4-113">Lync Server 제어판이 배포 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-113">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="c1da4-114">왼쪽 탐색 모음에서 **토폴로지**를 클릭 하 고 서비스 상태에 녹색 화살표가 있는 컴퓨터가 표시 되 고, 배포 및 온라인 상태가 된 각 Lync Server 서버 역할 옆에 복제 상태에 대 한 녹색 확인 표시가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-114">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="c1da4-115">왼쪽 탐색 표시줄에서 **사용자** 및 **사용자 사용**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-115">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="c1da4-116">**새 Lync Server 사용자** 페이지에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-116">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="c1da4-p102">찾을 개체에 대한 검색 매개 변수를 정의하려면 **Active Directory에서 선택** 페이지에서 **검색**을 선택하고 경우에 따라 **필터 추가**를 클릭하면 됩니다. **LDAP 검색**을 선택하고 LDAP 식을 입력하여 반환되는 개체를 필터링하거나 제한할 수도 있습니다. 검색 옵션을 결정했으면 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-p102">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="c1da4-120">검색 결과 창에서 이 검색 세션에 대한 개체를 모두 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-120">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="c1da4-p103">**새 Lync Server 사용자** 페이지의 **사용자** 화면 표시에 선택한 개체(들)가 나타납니다. **사용자를 풀에 할당** 목록에서 개체가 속해야 하는 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-p103">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display. In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="c1da4-123">아래에 개체를 구성할 수 있는 여러 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-123">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="c1da4-124">**사용자의 SIP URI 생성**</span><span class="sxs-lookup"><span data-stu-id="c1da4-124">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="c1da4-125">**통신과**</span><span class="sxs-lookup"><span data-stu-id="c1da4-125">**Telephony**</span></span>
    
      - <span data-ttu-id="c1da4-126">**줄 URI**</span><span class="sxs-lookup"><span data-stu-id="c1da4-126">**Line URI**</span></span>
    
      - <span data-ttu-id="c1da4-127">**회의 정책**</span><span class="sxs-lookup"><span data-stu-id="c1da4-127">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="c1da4-128">**클라이언트 버전 정책**</span><span class="sxs-lookup"><span data-stu-id="c1da4-128">**Client version policy**</span></span>
    
      - <span data-ttu-id="c1da4-129">**PIN 정책**</span><span class="sxs-lookup"><span data-stu-id="c1da4-129">**PIN policy**</span></span>
    
      - <span data-ttu-id="c1da4-130">**외부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="c1da4-130">**External access policy**</span></span>
    
      - <span data-ttu-id="c1da4-131">**보관 정책**</span><span class="sxs-lookup"><span data-stu-id="c1da4-131">**Archiving policy**</span></span>
    
      - <span data-ttu-id="c1da4-132">**위치 정책**</span><span class="sxs-lookup"><span data-stu-id="c1da4-132">**Location policy**</span></span>
    
      - <span data-ttu-id="c1da4-133">**클라이언트 정책**</span><span class="sxs-lookup"><span data-stu-id="c1da4-133">**Client policy**</span></span>
    
    <span data-ttu-id="c1da4-134">기본적인 기능을 테스트하기 위해 **사용자의 SIP URI 생성** 설정에 대해 원하는 옵션을 선택하고 **사용**을 클릭합니다(구성의 다른 옵션에는 기본 설정이 사용됨).</span><span class="sxs-lookup"><span data-stu-id="c1da4-134">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="c1da4-p104">요약 페이지가 표시되며, 이 페이지의 **사용** 열에는 개체를 바로 사용할 수 있다는 확인 표시가 나타납니다. **SIP 주소** 열에 사용자 로그인 구성에 필요한 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-p104">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="c1da4-137">도메인에 가입된 컴퓨터에 사용자 로그온하고 도메인의 다른 컴퓨터에 다른 사용자로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-137">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="c1da4-138">두 클라이언트 컴퓨터 각각에 Lync 2013을 설치한 다음 두 사용자가 Lync Server 2013에 로그인 하 여 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da4-138">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1da4-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1da4-139">See Also</span></span>


[<span data-ttu-id="c1da4-140">Lync Server 2013에서 클라이언트 및 장치 배포</span><span class="sxs-lookup"><span data-stu-id="c1da4-140">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

