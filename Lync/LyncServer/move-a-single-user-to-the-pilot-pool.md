---
title: 단일 사용자를 시험 운용 풀로 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c14c4a772ced3939d979bd8d4cd053207b0c5613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="65b23-102">단일 사용자를 시험 운용 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="65b23-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65b23-103">_**마지막으로 수정한 주제:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="65b23-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="65b23-104">Lync server 2013 제어판 또는 Lync Server 2013 Management Shell을 사용 하 여 Lync Server 2010 풀에서 Lync server 2013 파일럿 풀로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="65b23-105">아래 예제에서 레지스트라 풀 열의 **pool01.contoso.net** 는 Lync Server 2010 풀 이며,이 풀에는 6 명의 사용자가 모두 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="65b23-106">Lync Server 2013 제어판 및 Lync Server Management Shell을 사용 하 여 사용자를 Lync Server 2013 풀로 이동 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="65b23-107">Lync Server 2013 제어판을 사용 하 여 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="65b23-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="65b23-108">**Lync Server 2013 제어판의 사용자 목록**</span><span class="sxs-lookup"><span data-stu-id="65b23-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="65b23-109">![Lync Server 제어판, 사용자 이동 대화 상자](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server 제어판, 사용자 이동 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="65b23-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="65b23-110">RTCUniversalServerAdmins 그룹의 구성원 이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="65b23-111">**Lync Server 제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="65b23-112">**사용자**를 클릭 하 고 검색을 클릭 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="65b23-113">Lync Server 2013 풀로 이동 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="65b23-114">이 예제에서는 사용자 Sara 아를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="65b23-115">**작업** 메뉴에서 **선택한 사용자 이동을 선택 하 여 그룹으로 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="65b23-116">드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="65b23-117">**작업** 을 클릭 한 다음 **선택한 사용자 이동을 클릭 하 여 그룹을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="65b23-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-118">Click **OK**.</span></span>
    
    <span data-ttu-id="65b23-119">![사용자 이동, 대상 등록자 풀 대화 상자](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "사용자 이동, 대상 등록자 풀 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="65b23-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="65b23-120">사용자의 **등록자 그룹** 열에 사용자가 성공적으로 이동 했음을 나타내는 Lync Server 2013 풀이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="65b23-121">Lync Server 2013 관리 셸을 사용 하 여 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="65b23-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="65b23-122">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="65b23-123">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="65b23-124">그런 다음 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="65b23-125">이제 **RegistrarPool** Id는 Lync Server 2013 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="65b23-126">이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="65b23-127">![ID 필터가 사용된 Get-CsUser cmdlet의 출력](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "ID 필터가 사용된 Get-CsUser cmdlet의 출력")</span><span class="sxs-lookup"><span data-stu-id="65b23-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65b23-128"><STRONG>Get-csuser</STRONG> cmdlet에 대 한 자세한 내용을 보려면 <STRONG>Get-help-Csuser-Detailed</STRONG> 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b23-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

