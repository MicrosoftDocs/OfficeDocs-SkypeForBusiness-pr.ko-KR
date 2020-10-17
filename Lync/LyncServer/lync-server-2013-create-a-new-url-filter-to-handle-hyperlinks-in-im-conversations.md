---
title: IM 대화에서 하이퍼링크를 처리할 새 URL 필터 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b129f2f9f1aa4b9a2a07a63d0432957f2b79941
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501915"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="9b9dc-102">Lync Server 2013에서 새 URL 필터 만들기 IM 대화의 하이퍼링크를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="9b9dc-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b9dc-103">_**마지막으로 수정 된 항목:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="9b9dc-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9b9dc-104">전역 URL 필터를 수정 하는 것 외에도 Lync Server 2013 배포 내의 개별 사이트에 대해 사용자 지정 URL 필터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="9b9dc-105">URL 필터링에 대 한 자세한 내용은 [Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성을](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="9b9dc-106">새 URL 필터를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9b9dc-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="9b9dc-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b9dc-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b9dc-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9b9dc-110">왼쪽 탐색 모음에서 **메신저 및 현재 상태**를 클릭한 다음 **URL 필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="9b9dc-111">**URL 필터** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="9b9dc-112">**사이트 선택**에서 URL 필터를 만들 사이트를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="9b9dc-113">**새 URL 필터** 대화 상자에서 **URL 필터 사용** 확인란을 선택하여 사이트에 대해 URL 필터를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="9b9dc-114">**파일 필터 편집**의 **차단할 파일 형식 확장명**에 나열된 확장명을 가진 파일이 포함된 활성 URL을 차단하려면 **파일 형식 확장명이 있는 URL 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="9b9dc-115">**하이퍼링크 접두사** 드롭다운 목록 상자에서 메신저 대화의 URL을 처리하려는 방법에 해당하는 옵션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="9b9dc-116">**메시지 허용** 상자를 통해 보내도록 허용된 하이퍼링크를 보낼 때 사용자에게 경고 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="9b9dc-117">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9dc-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b9dc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b9dc-118">See Also</span></span>


[<span data-ttu-id="9b9dc-119">Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="9b9dc-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="9b9dc-120">특정 사이트에 대해 Lync Server 2013에서 새 파일 전송 필터 만들기</span><span class="sxs-lookup"><span data-stu-id="9b9dc-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="9b9dc-121">Lync Server 2013에서 기본 파일 전송 필터 수정</span><span class="sxs-lookup"><span data-stu-id="9b9dc-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="9b9dc-122">Lync Server 2013의 기본 URL 필터 수정</span><span class="sxs-lookup"><span data-stu-id="9b9dc-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

