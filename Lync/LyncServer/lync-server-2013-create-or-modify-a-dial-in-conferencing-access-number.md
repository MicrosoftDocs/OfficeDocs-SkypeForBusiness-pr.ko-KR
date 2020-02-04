---
title: 'Lync Server 2013: 전화 접속 회의 액세스 번호 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ecfebba25d45f53633fdd425e5901929fc32d0c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="f14dc-102">Lync Server 2013에서 전화 접속 회의 액세스 번호 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f14dc-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f14dc-103">_**마지막으로 수정한 주제:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f14dc-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f14dc-104">전화 접속 회의 액세스 번호를 만들거나 수정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f14dc-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f14dc-105">새 전화 접속 액세스 번호를 만들기 전에 새 전화 접속 액세스 번호와 연결 된 다이얼 플랜에서 전화 접속 회의 영역을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="f14dc-106">여러 다이얼 플랜은 같은 지역을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="f14dc-107">전화 접속 액세스 번호를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="f14dc-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="f14dc-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f14dc-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f14dc-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f14dc-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f14dc-111">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **전화 접속 액세스 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="f14dc-112">**전화 접속 액세스 번호** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f14dc-113">**새로 만들기** 를 클릭 하 여 **새 전화 접속 액세스 번호**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="f14dc-114">목록에서 전화 접속 액세스 번호 중 하나를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f14dc-115">검색 필드를 사용 하 여 전화 접속 액세스 번호 목록에서 열의 내용을 검색 하면 예상한 결과가 생성 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-115">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="f14dc-116">대신 원하는 열을 기준으로 목록을 정렬 하 여 보거나 변경 하려는 전화 접속 액세스 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-116">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="f14dc-117">**표시 번호**에 공개 전환 전화 네트워크 (PSTN) 전화 사용자가 전화를 걸고 있는 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f14dc-118">이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="f14dc-119">**표시 이름**에 전화 접속 액세스 번호에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="f14dc-120">Lync 검색 결과의 전화 접속 액세스 번호와 연결 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f14dc-121">이 이름은 사용자가 액세스 번호를 호출할 때 클라이언트에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="f14dc-122">**줄 uri**에서 번호 앞에 + 기호를 포함 하 고 공백을 제외 하 고 TEL uri 형식의 전화 접속 액세스 번호에 대 한 E 자의 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-122">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="f14dc-123">예를 들어, tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="f14dc-123">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f14dc-124">같은 회선 URI를 다른 전화 접속 회의 액세스 번호로 재사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="f14dc-125">**SIP URI**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="f14dc-126">입력란에이 전화 접속 회의 액세스 번호에 대 한 고유한 SIP URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="f14dc-127">이 SIP URI는 통화 알림 메시지 및 이전 버전의 Communicator 클라이언트를 포함 하 여 다양 한 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f14dc-128">같은 SIP URI를 다른 전화 접속 회의 액세스 번호에서 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-128">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="f14dc-129">액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-129">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="f14dc-130">SIP URI를 변경 하는 유일한 방법은 액세스 번호를 삭제 하 고 다시 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-130">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="f14dc-131">드롭다운 목록 상자에서이 전화 접속 액세스 번호를 지 원하는 회의 수행자 응용 프로그램의 도메인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="f14dc-132">**풀**에서이 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 인스턴스를 실행 하는 풀을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f14dc-133">액세스 번호를 만든 후에 풀을 변경 해야 하는 경우 <STRONG>-CsApplicationEndpoint</STRONG> cmdlet을 사용 하거나 액세스 번호를 삭제 하 고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="f14dc-134">**기본 언어**에서이 전화 접속 액세스 번호에 대 한 메시지가 재생 되는 언어를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f14dc-135">기본 언어는 회의 수행자가 통화에 응답 하는 데 사용 하는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-135">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="f14dc-136">지원 되는 언어는 전화 접속 회의 설정 웹 페이지의 각 액세스 전화 번호 옆에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-136">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="f14dc-137">) **보조 언어 (최대 4 개)** 에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 호출자에 대해 지원할 추가 언어를 하나 이상 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f14dc-138">각 전화 접속 액세스 번호에 대해 최대 4 개의 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-138">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="f14dc-139">사용자가 회의에 전화를 걸 때 전화 회의 ID를 입력 하기 전에 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-139">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="f14dc-140">전화 접속 액세스 번호에 대 한 영역을 추가 하려면 **연결 된 지역**에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 다이얼 플랜에 연결 된 하나 이상의 지역을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="f14dc-141">전화 접속 액세스 번호에서 지역을 삭제 하려면 **연결 된 지역**에서 삭제할 지역을 클릭 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="f14dc-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f14dc-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

