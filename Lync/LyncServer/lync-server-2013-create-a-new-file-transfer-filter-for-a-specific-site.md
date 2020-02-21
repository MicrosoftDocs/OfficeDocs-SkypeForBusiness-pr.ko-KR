---
title: 'Lync Server 2013: 특정 사이트에 대 한 새 파일 전송 필터 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bec5e9e33850fc1da53d370f70b948b7ec6b3f27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="38d38-102">특정 사이트에 대해 Lync Server 2013에서 새 파일 전송 필터 만들기</span><span class="sxs-lookup"><span data-stu-id="38d38-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38d38-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="38d38-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="38d38-104">전역 파일 전송 필터를 수정 하는 것 외에도 Lync Server 2013 배포 내의 특정 사이트에 대해 사용자 지정 파일 전송 필터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="38d38-105">파일 전송 필터링에 대 한 자세한 내용은 [Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성을](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38d38-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="38d38-106">특정 사이트에 대해 파일 전송 필터를 만들려면</span><span class="sxs-lookup"><span data-stu-id="38d38-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="38d38-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38d38-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="38d38-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38d38-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="38d38-110">왼쪽 탐색 모음에서 **IM 및 현재 상태**를 클릭한 다음 **파일 필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="38d38-111">**파일 필터** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="38d38-112">**사이트 선택** 대화 상자에서 파일 전송 필터를 만들 사이트를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="38d38-113">**새 파일 필터**에서 **파일 필터 사용** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="38d38-114">**파일 전송** 드롭다운 목록 상자에서 **모두 차단** 또는 **특정 파일 형식 차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="38d38-115">**모두 차단을**클릭 한 경우 10 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="38d38-116">**특정 파일 형식 차단**을 클릭한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="38d38-117">**선택**을 클릭하여 차단할 파일 형식 확장명의 기본 목록을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="38d38-118">**파일 형식 선택** 대화 상자의 **파일 형식 확장명**아래의 범주에서 해당 확장명을 추가 하거나 제거 하 여 차단 하거나 허용할 파일 형식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="38d38-119">차단할 파일 형식 확장명이 표시되지 않은 경우 **목록에 새 파일 형식 확장명 추가** 아래의 텍스트 상자에 확장명을 입력한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="38d38-120">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-120">Click **OK**.</span></span>

10. <span data-ttu-id="38d38-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38d38-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38d38-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38d38-122">See Also</span></span>


[<span data-ttu-id="38d38-123">Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="38d38-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="38d38-124">Lync Server 2013에서 새 URL 필터 만들기 IM 대화의 하이퍼링크를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="38d38-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="38d38-125">Lync Server 2013에서 기본 파일 전송 필터 수정</span><span class="sxs-lookup"><span data-stu-id="38d38-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="38d38-126">Lync Server 2013의 기본 URL 필터 수정</span><span class="sxs-lookup"><span data-stu-id="38d38-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

