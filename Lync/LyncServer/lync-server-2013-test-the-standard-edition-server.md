---
title: 'Lync Server 2013: Standard Edition Server 테스트'
description: 'Lync Server 2013: Standard Edition Server를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35dc13fc01979cc8b293d0647a7886b7d65d7669
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576014"
---
# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="cc3c5-103">Lync Server 2013에서 Standard Edition server 테스트</span><span class="sxs-lookup"><span data-stu-id="cc3c5-103">Test the Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc3c5-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cc3c5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cc3c5-105">다음 절차에서는 Standard Edition server 배포를 테스트 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-105">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="cc3c5-106">Standard Edition Server 배포를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="cc3c5-106">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="cc3c5-107">Active Directory 컴퓨터 및 사용자를 사용 하 여 lync server 제어판이 설치 된 경우의 관리자 2013 역할에 해당 하는 Active Directory 사용자 개체를 **csadministrator** 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="cc3c5-108">사용자 개체가 현재 로그온되어 있는 경우 로그오프하고 다시 로그온하여 새 그룹 지정을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc3c5-109">사용자 계정은 Lync Server 2013, Standard Edition을 실행 하는 서버의 로컬 관리자 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-109">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="cc3c5-110">적절 한 사용자 및 그룹을 CsAdministors 그룹에 추가 하지 않으면 Lync Server 2013 제어판을 열 때 "권한이 없음: 역할 기반 액세스 제어 (RBAC) 권한 부여 오류로 인해 액세스가 거부 되었습니다." 라는 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-110">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="cc3c5-111">관리 계정을 사용 하 여 Lync Server 제어판이 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="cc3c5-112">Lync Server 제어판을 시작 하 고 메시지가 표시 되 면 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-112">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="cc3c5-113">Lync Server 2013 제어판에서 배포 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-113">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="cc3c5-114">왼쪽 탐색 모음에서 **토폴로지**를 클릭 하 고 서비스 상태가 녹색 화살표가 있는 컴퓨터 아이콘 인지 확인 하 고, 배포 되 고 온라인 상태가 된 각 Lync Server 서버 역할 옆에 녹색 확인 표시가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-114">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="cc3c5-115">왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 두 사용자에 게 Lync Server 2013을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-115">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="cc3c5-116">도메인에 가입된 컴퓨터에 사용자로 로그온하고 도메인의 다른 컴퓨터에 다른 사용자로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-116">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="cc3c5-117">두 클라이언트 컴퓨터 각각에 Lync Server 2013를 설치한 다음 두 사용자가 Lync Server 2013에 로그인 하 여 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3c5-117">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc3c5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc3c5-118">See Also</span></span>


[<span data-ttu-id="cc3c5-119">Lync Server 2013에서 클라이언트 및 장치 배포</span><span class="sxs-lookup"><span data-stu-id="cc3c5-119">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

