---
title: 마이그레이션 후 단순 URL 변경
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
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="f5a62-102">마이그레이션 후 단순 URL 변경</span><span class="sxs-lookup"><span data-stu-id="f5a62-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5a62-103">_**마지막으로 수정한 주제:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="f5a62-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="f5a62-104">Lync Server는 다음과 같은 세 가지 간단한 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="f5a62-105">**회의** 는 사이트 또는 조직의 모든 컨퍼런스에 대 한 기본 URL로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="f5a62-106">모임에 참여 하는 간단한 URL을 사용 하 여 모임을 연결 하는 링크는 이해 하기 쉬우며, 의사 소통 및 배포 하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="f5a62-107">**전화 접속-** 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="f5a62-108">모임에 전화를 걸려면 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 전화 접속 간단한 URL이 모든 모임 초대에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="f5a62-109">**관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="f5a62-110">관리 단순 URL은 조직 내부입니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="f5a62-111">Lync Server 2013으로 마이그레이션한 후에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 영향을 주는 방식을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="f5a62-112">레거시 Lync Server 2010 디렉터가 토폴로지에서 계속 사용 중인 경우 간단한 Url을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="f5a62-113">마이그레이션 후에 Lync Server 2010 디렉터가 토폴로지에서 제거 되는 경우, Lync Server 2013 풀 중 하나를 가리키도록 간단한 URL DNS 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="f5a62-114">그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서-CsComputer를 실행 하 여 변경 내용을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="f5a62-115">마이그레이션 후 간단한 Url 변경</span><span class="sxs-lookup"><span data-stu-id="f5a62-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="f5a62-116">**기본 모임 URL을 업데이트 하려면**</span><span class="sxs-lookup"><span data-stu-id="f5a62-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="f5a62-117">토폴로지 작성기에서 최상위 노드 **Lync Server**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f5a62-118">왼쪽 창에서 **간단한 url** 을 선택 하 고 모임 url 아래에 있는 url을 선택한 다음 **url 편집**을 클릭 합니다 **.**</span><span class="sxs-lookup"><span data-stu-id="f5a62-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="f5a62-119">URL을 원하는 값으로 업데이트 한 다음 **확인** 을 클릭 하 여 편집한 url을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="f5a62-120">**관리 간단한 URL을 업데이트 하려면**</span><span class="sxs-lookup"><span data-stu-id="f5a62-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="f5a62-121">토폴로지 작성기에서 최상위 노드 **Lync Server**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f5a62-122">왼쪽 창에서 **간단한 url** 을 선택 하 고 **관리 액세스 URL** 상자 아래에 있는 Lync Server 2013 제어판에 대 한 관리 액세스에 사용할 간단한 URL을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f5a62-123">관리 URL에 가장 간단한 URL을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a62-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="f5a62-124">가장 간단한 방법은 <STRONG> https://admin입니다.</STRONG> &lt;도메인&gt;.</span><span class="sxs-lookup"><span data-stu-id="f5a62-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5a62-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5a62-125">See Also</span></span>


[<span data-ttu-id="f5a62-126">Lync Server 2013의 단순 URL 계획</span><span class="sxs-lookup"><span data-stu-id="f5a62-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

