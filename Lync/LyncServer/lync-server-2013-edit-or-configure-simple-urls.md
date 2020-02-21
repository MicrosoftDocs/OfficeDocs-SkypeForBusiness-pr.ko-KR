---
title: 'Lync Server 2013: 단순 Url 편집 또는 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e77d5ddf74d43cd277a701608e801a65262c929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="0c5f2-102">Lync Server 2013에서 단순 Url 편집 또는 구성</span><span class="sxs-lookup"><span data-stu-id="0c5f2-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c5f2-103">_**마지막으로 수정 된 항목:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="0c5f2-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="0c5f2-p101">이 절차는 로컬 관리자 구성원 자격 또는 권한이 있는 도메인 그룹 구성원 자격이 없어도 수행할 수 있습니다. 즉, 컴퓨터에 표준 사용자로 로그온하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="0c5f2-106">Lync Server 2013에서는 단순 Url을 사용 하 여 프런트 엔드 서버 또는 디렉터 (배포 된 경우)의 서비스에 대 한 내부 및 외부 통화를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="0c5f2-107">단순 Url에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 단순 Url 계획](lync-server-2013-planning-for-simple-urls.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="0c5f2-108">여러 옵션에서 단순 Url의 형식을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="0c5f2-109">이러한 옵션에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 단순 url에 대 한 DNS 요구 사항을](lync-server-2013-dns-requirements-for-simple-urls.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="0c5f2-110">기본적으로 단순 Url은 (예: 전화 접속 단순 URL)와 같은 형식으로 구성 됩니다. https://dialin.\<SIP\></span><span class="sxs-lookup"><span data-stu-id="0c5f2-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="0c5f2-111">단순 URL을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="0c5f2-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="0c5f2-112">토폴로지 작성기에서 **Lync Server** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="0c5f2-113">**단순 url** 창에서 **전화 액세스 url:** (전화 접속) 또는 **모임 url:** (모임)을 선택 하 여 편집 하 고 **URL 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="0c5f2-114">URL을 원하는 값으로 업데이트하고 **확인**을 클릭하여 편집한 URL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="0c5f2-115">여기에 표시 된 예는 전화 접속 URL을로 https://pool01.contoso.net/dialin수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="0c5f2-116">필요한 경우 같은 단계를 수행하여 모임 URL을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="0c5f2-117">관리 단순 URL(선택 사항)을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="0c5f2-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="0c5f2-118">토폴로지 작성기에서 **Lync Server** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="0c5f2-119">**관리 액세스 URL** 상자에 Lync Server 2013 제어판에 대 한 관리 액세스용으로 사용할 단순 URL을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="0c5f2-120">관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="0c5f2-121">가장 간단한 방법은 <STRONG> https://admin입니다.</STRONG> &lt;도메인&gt;</span><span class="sxs-lookup"><span data-stu-id="0c5f2-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0c5f2-122">초기 배포 후에 단순 URL을 변경하는 경우에는 변경 내용이 단순 URL의 DNS(Domain Name System) 레코드 및 인증서에 주는 영향을 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="0c5f2-123">변경 내용이 단순 URL의 기준에 영향을 주는 경우에는 DNS 레코드 및 인증서도 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="0c5f2-124">예를 들어에서 https://lync.contoso.com/Meet 를 https://meet.contoso.com 변경 하면 기본 URL이 lync.contoso.com에서 MEET.CONTOSO.COM으로 변경 되므로 DNS 레코드 및 인증서를 변경 하 여 meet.contoso.com를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="0c5f2-125">단순 URL을에서 https://lync.contoso.com/Meet 로 https://lync.contoso.com/Meetings변경한 경우 lync.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="0c5f2-126">그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 <STRONG>CsComputer</STRONG> cmdlet을 실행 하 여 변경 내용을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c5f2-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c5f2-127">See Also</span></span>


[<span data-ttu-id="0c5f2-128">Lync Server 2013의 단순 Url 계획</span><span class="sxs-lookup"><span data-stu-id="0c5f2-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

