---
title: 'Lync Server 2013: 단순 URL 편집 또는 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1439ddb0dafc63b0e70439ee5231477fdbb6be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="48d84-102">Lync Server 2013에서 단순 URL 편집 또는 구성</span><span class="sxs-lookup"><span data-stu-id="48d84-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48d84-103">_**마지막으로 수정한 주제:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="48d84-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="48d84-104">이 절차에서는 로컬 관리자 또는 특권 도메인 그룹의 멤버 자격을 요구 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="48d84-105">표준 사용자로 컴퓨터에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="48d84-106">Lync Server 2013는 간단한 Url을 사용 하 여 프런트 엔드 서버 또는 디렉터 (배포 된 경우)의 서비스에 대 한 내부 및 외부 통화를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="48d84-107">간단한 Url에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 간단한 Url 계획](lync-server-2013-planning-for-simple-urls.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48d84-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="48d84-108">여러 옵션에서 간단한 Url의 형식을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="48d84-109">이러한 옵션에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 간단한 url에 대 한 DNS 요구 사항을](lync-server-2013-dns-requirements-for-simple-urls.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48d84-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="48d84-110">기본적으로 간단한 Url은 다음 형식으로 구성 됩니다 (예: 전화 접속 간단한 URL). https://dialin.\<SIP 도메인\></span><span class="sxs-lookup"><span data-stu-id="48d84-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="48d84-111">간단한 Url을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="48d84-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="48d84-112">토폴로지 작성기에서 **Lync Server** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="48d84-113">**간단한 url** 창에서 **전화 액세스 url:** (전화 접속) 또는 **모임 url:** (모임)을 선택 하 여 편집한 다음 **URL 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="48d84-114">URL을 원하는 값으로 업데이트 한 다음 **확인** 을 클릭 하 여 편집한 url을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="48d84-115">여기에 나와 있는 예제는 전화 접속 URL을 https://pool01.contoso.net/dialin수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="48d84-116">필요한 경우 같은 단계를 사용 하 여 모임 URL을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="48d84-117">관리 간단한 URL (선택 사항)을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="48d84-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="48d84-118">토폴로지 작성기에서 **Lync Server** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="48d84-119">**관리 액세스 URL** 상자에 Lync Server 2013 제어판의 관리 액세스에 사용할 간단한 URL을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="48d84-120">관리 URL에 가장 간단한 URL을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="48d84-121">가장 간단한 방법은 <STRONG> https://admin입니다.</STRONG> &lt;도메인&gt;.</span><span class="sxs-lookup"><span data-stu-id="48d84-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="48d84-122">초기 배포 후 간단한 URL을 변경 하는 경우 간단한 url에 대 한 DNS (Domain Name System) 레코드 및 인증서에 영향을 주는 변경 사항에 대해 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="48d84-123">변경 내용이 간단한 URL의 기본에 영향을 주는 경우 DNS 레코드 및 인증서도 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="48d84-124">예를 들어 lync.contoso.com에서 https://lync.contoso.com/Meet 로 https://meet.contoso.com 변경 하면 기본 URL이 MEET.CONTOSO.COM로 변경 되므로 DNS 레코드와 인증서를 변경 해야 meet.contoso.com을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="48d84-125">간단한 URL을에서 https://lync.contoso.com/Meet 으로 https://lync.contoso.com/Meetings변경한 경우 lync.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="48d84-126">그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 <STRONG>CsComputer</STRONG> cmdlet을 실행 하 여 변경 내용을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48d84-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48d84-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48d84-127">See Also</span></span>


[<span data-ttu-id="48d84-128">Lync Server 2013의 단순 URL 계획</span><span class="sxs-lookup"><span data-stu-id="48d84-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

