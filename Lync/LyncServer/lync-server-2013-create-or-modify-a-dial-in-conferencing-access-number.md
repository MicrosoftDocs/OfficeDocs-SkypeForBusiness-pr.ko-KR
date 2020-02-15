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
ms.openlocfilehash: 6406fe5c2f1183b39966902ee2fa5273f509bf2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="6ad2f-102">Lync Server 2013에서 전화 접속 회의 액세스 번호 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="6ad2f-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ad2f-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="6ad2f-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="6ad2f-104">전화 접속 회의 액세스 번호를 만들거나 수정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ad2f-105">새 전화 접속 액세스 번호를 만들기 전에 새 전화 접속 액세스 번호와 연결 된 다이얼 플랜에 전화 접속 회의 지역을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="6ad2f-106">여러 다이얼 플랜에서 같은 지역을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="6ad2f-107">전화 접속 액세스 번호를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="6ad2f-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="6ad2f-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6ad2f-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6ad2f-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6ad2f-111">왼쪽 탐색 모음에서 **회의**를 클릭한 다음 **전화 접속 액세스 번호**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="6ad2f-112">**전화 접속 액세스 번호** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6ad2f-113">**새로 만들기** 를 클릭 하 여 **새 전화 접속 액세스 번호**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="6ad2f-114">목록에서 전화 접속 액세스 번호 중 하나를 클릭 하 고 **편집**을 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6ad2f-115">검색 필드를 사용 하 여 전화 접속 액세스 번호 목록에서 열의 내용을 검색 하면 예상 했던 결과가 나오지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-115">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="6ad2f-116">대신 관심 있는 열을 기준으로 목록을 정렬 하 여 보거나 변경 하려는 전화 접속 액세스 번호를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-116">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="6ad2f-117">**표시 번호**에 공중 전화망 (PSTN) 전화 사용자가 회의에 참가 하기 위해 전화를 걸 수 있는 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ad2f-118">이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="6ad2f-119">**표시 이름**에 전화 접속 액세스 번호에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="6ad2f-120">이 이름은 Lync 검색 결과에서 전화 접속 액세스 번호와 연결 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ad2f-121">사용자가 액세스 번호로 전화를 걸 때이 이름이 클라이언트에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="6ad2f-122">**줄 URI**에서 전화 URI 형식에 + 기호를 포함 하 여 번호 앞에 \*를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-122">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="6ad2f-123">예를 들면 전화: + 14255550200</span><span class="sxs-lookup"><span data-stu-id="6ad2f-123">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ad2f-124">다른 전화 접속 회의 액세스 번호에서 동일한 줄 URI를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="6ad2f-125">**SIP URI**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="6ad2f-126">텍스트 상자에이 전화 접속 회의 액세스 번호에 대 한 고유한 SIP URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="6ad2f-127">이 SIP URI는 전화 알림 메시지 및 이전 버전의 Communicator 클라이언트를 포함 하는 다양 한 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6ad2f-128">다른 전화 접속 회의 액세스 번호에서 동일한 SIP URI를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-128">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="6ad2f-129">액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-129">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="6ad2f-130">SIP URI를 변경 하는 유일한 방법은 액세스 번호를 삭제 하 고 다시 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-130">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="6ad2f-131">드롭다운 목록 상자에서 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 응용 프로그램의 도메인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="6ad2f-132">**풀**에서이 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 인스턴스를 실행 하는 풀을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ad2f-133">액세스 번호를 만든 후에 풀을 변경 해야 하는 경우에는 <STRONG>CsApplicationEndpoint</STRONG> cmdlet을 사용 하거나 액세스 번호를 삭제 하 고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="6ad2f-134">**기본 언어**에서이 전화 접속 액세스 번호에 대 한 프롬프트를 재생할 언어를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ad2f-135">기본 언어는 회의 수행자가 통화에 응답 하는 데 사용 하는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-135">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="6ad2f-136">지원 되는 언어는 전화 접속 회의 설정 웹 페이지에서 각 액세스 전화 번호 옆에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-136">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="6ad2f-137">반드시 **보조 언어 (최대 4 개)** 에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 발신자에 대해 지원할 추가 언어를 하나 이상 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ad2f-138">각 전화 접속 액세스 번호에 대해 최대 4 개의 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-138">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="6ad2f-139">사용자가 회의에 전화를 걸 때 전화 회의 ID를 입력 하기 전에 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-139">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="6ad2f-140">전화 접속 액세스 번호에 대 한 지역을 추가 하려면 **연결 된 지역**아래에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 다이얼 플랜과 연결 된 하나 이상의 지역을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="6ad2f-141">전화 접속 액세스 번호에서 지역을 삭제 하려면 **연결 된 지역**에서 삭제할 지역을 클릭 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="6ad2f-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

