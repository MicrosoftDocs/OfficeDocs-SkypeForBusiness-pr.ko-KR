---
title: 마이그레이션 후 단순 Url 변경
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e96c6a1d33c9c50208c7cdea628b2c4464a7b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="d6d6a-102">마이그레이션 후 단순 Url 변경</span><span class="sxs-lookup"><span data-stu-id="d6d6a-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6d6a-103">_**마지막으로 수정 된 항목:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="d6d6a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="d6d6a-104">Lync Server에서는 다음과 같은 세 가지 단순 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="d6d6a-105">**모임**은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="d6d6a-106">모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="d6d6a-107">**전화 접속** 을 사용 하면 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="d6d6a-108">전화 접속 단순 URL은 모임에 전화를 거는 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="d6d6a-109">**관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="d6d6a-110">관리 단순 URL은 조직의 내부 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="d6d6a-111">Lync Server 2013로 마이그레이션한 후에는 변경 내용이 단순 Url에 대 한 DNS 레코드 및 인증서에 미치는 영향을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="d6d6a-112">레거시 Lync Server 2010 디렉터가 토폴로지에서 사용 중인 경우에는 단순 Url을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="d6d6a-113">마이그레이션 후에 Lync Server 2010 디렉터를 토폴로지에서 제거한 경우 Lync Server 2013 풀 중 하나를 가리키도록 단순 URL DNS 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="d6d6a-114">그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 Enable-CsComputer를 실행하여 변경 내용을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="d6d6a-115">마이그레이션 후 단순 Url 변경</span><span class="sxs-lookup"><span data-stu-id="d6d6a-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="d6d6a-116">**모임 단순 URL을 업데이트 하려면**</span><span class="sxs-lookup"><span data-stu-id="d6d6a-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="d6d6a-117">토폴로지 작성기에서 맨 위에 있는 **Lync Server**노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="d6d6a-118">왼쪽 창에서 **단순 url** 을 선택한 다음 **모임 Url** 아래에서 회의 url을 선택 하 고 **url 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="d6d6a-119">URL을 원하는 값으로 업데이트하고 **확인**을 클릭하여 편집한 URL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="d6d6a-120">**관리 단순 URL을 업데이트 하려면**</span><span class="sxs-lookup"><span data-stu-id="d6d6a-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="d6d6a-121">토폴로지 작성기에서 맨 위에 있는 **Lync Server**노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="d6d6a-122">왼쪽 창에서 **단순 url** 을 선택한 다음, **관리 액세스 URL** 아래에 관리 액세스용 2013으로 사용할 단순 url을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d6d6a-123">관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d6a-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="d6d6a-124">가장 간단한 방법은 <STRONG> https://admin입니다.</STRONG> &lt;도메인&gt;</span><span class="sxs-lookup"><span data-stu-id="d6d6a-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6d6a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6d6a-125">See Also</span></span>


[<span data-ttu-id="d6d6a-126">Lync Server 2013의 단순 Url 계획</span><span class="sxs-lookup"><span data-stu-id="d6d6a-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

