---
title: 'Lync Server 2013: 기본 파일 전송 필터 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="e03ca-102">Lync Server 2013의 기본 파일 전송 필터 수정</span><span class="sxs-lookup"><span data-stu-id="e03ca-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e03ca-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e03ca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e03ca-104">Lync Server 2013는 Lync Server 2013 배포 내에서 다음 파일 관련 작업 중 특정 형식의 파일을 차단 하는 전역 파일 전송 필터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="e03ca-105">인스턴트 메시징 (IM) 대화 중 파일 전송 요청</span><span class="sxs-lookup"><span data-stu-id="e03ca-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="e03ca-106">Office Live Meeting 2007 클라이언트의 유인물 기능을 사용 하는 동안 파일 업로드 및 다운로드</span><span class="sxs-lookup"><span data-stu-id="e03ca-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="e03ca-107">회의 중 멀티미디어 재생</span><span class="sxs-lookup"><span data-stu-id="e03ca-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="e03ca-108">차단 하거나 허용 하려는 파일 형식에 따라 Lync Server 제어판을 사용 하 여 전역 필터를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="e03ca-109">파일 전송 필터링에 대 한 자세한 내용은 [Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성을](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e03ca-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="e03ca-110">기본 파일 전송 필터를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="e03ca-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="e03ca-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e03ca-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e03ca-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e03ca-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e03ca-114">왼쪽 탐색 모음에서 **메신저 대화 및 현재 상태** 를 클릭 한 다음 **파일 필터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="e03ca-115">**파일 필터** 페이지에서 **전역** 필터를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="e03ca-116">**파일 편집 필터**에서 **파일 필터 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="e03ca-117">**파일 전송** 드롭다운 목록 상자에서 **모두 차단** 또는 **특정 파일 형식 차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="e03ca-118">**모두 차단을**클릭 한 경우 9 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="e03ca-119">**특정 파일 형식 차단을**클릭 한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="e03ca-120">**선택을** 클릭 하 여 차단 하려는 파일 형식 확장명의 기본 목록을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="e03ca-121">**파일 형식 선택**에서 **파일 형식 확장명**아래에 있는 범주에서 확장을 추가 하거나 제거 하 여 차단 하거나 허용 하려는 파일 형식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="e03ca-122">차단 하려는 파일 형식에 대 한 확장명이 표시 되지 않으면 **목록에 파일 형식 확장명 추가**아래에 있는 텍스트 상자에 확장명을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="e03ca-123">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-123">Click **OK**.</span></span>

9.  <span data-ttu-id="e03ca-124">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e03ca-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e03ca-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e03ca-125">See Also</span></span>


[<span data-ttu-id="e03ca-126">Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="e03ca-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="e03ca-127">특정 사이트에 대 한 Lync Server 2013에서 새 파일 전송 필터 만들기</span><span class="sxs-lookup"><span data-stu-id="e03ca-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="e03ca-128">Lync Server 2013에서 새 URL 필터를 만들어 메신저 대화의 하이퍼링크 처리</span><span class="sxs-lookup"><span data-stu-id="e03ca-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="e03ca-129">Lync Server 2013의 기본 URL 필터 수정</span><span class="sxs-lookup"><span data-stu-id="e03ca-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

