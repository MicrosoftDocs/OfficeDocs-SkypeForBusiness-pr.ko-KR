---
title: Lync Server 2013:에 지 서버 인증서 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b70d9635b253c793170ff11373f6d063f0f46c81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="05b84-102">Lync Server 2013의에 지 서버 인증서 계획</span><span class="sxs-lookup"><span data-stu-id="05b84-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05b84-103">_**마지막으로 수정 된 항목:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="05b84-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="05b84-104">Lync Server 2013에서는 Edge 용 인증서 만들기가 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="05b84-105">**에 지 서버에 대 한 인증서 순서도**</span><span class="sxs-lookup"><span data-stu-id="05b84-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="05b84-106">![a5fc20db-7ced-4364-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="05b84-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="05b84-107">단일 공용 인증서를 만들고 인증서에 대해 내보낼 수 있는 개인 키를 정의 했는지 확인 한 후 인증서 마법사를 사용 하 여 다음에 지 서버 외부 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="05b84-108">역방향 프록시를 통해 단순 Url을 요약 하는 데 사용 되는 경우를 제외 하 고는 Lync Server에서 와일드 카드 인증서를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="05b84-109">배포에서 제공 하는 각 SIP 도메인 이름, 웹 회의에 지 서비스, A/V에 지 서비스 및 XMPP 도메인에 대해 고유한 주체 대체 이름 (San)을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="05b84-110">Lync Server 2013, 준비 오디오/비디오 인증 인증서를 현재 인증서의 만료 시간 이전에 도입 하면 몇 가지 추가 계획이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="05b84-111">외부에 지 인터페이스에 대 한 용도가 여러 개인 인증서 하나가 아닌 경우에는 액세스에 지 서비스 및 웹 회의에 지 서비스에 할당 된 인증서와 A/V에 지 서비스에 대 한 인증서가 각각 하나씩 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="05b84-112">자세한 내용은 <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">set-cscertificate in a Lync Server 2013 using a-Roll</A></span><span class="sxs-lookup"><span data-stu-id="05b84-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="05b84-113">에 지 서버 풀의 경우에는 개인 키가 포함 된 인증서를 각에 지 서버로 내보내고 각에 지 서버 서비스에 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="05b84-114">내부에 지 서버 인증서에 대해 동일한 작업을 수행 하 여 인증서를 개인 키로 내보내고 각 내부에 지 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="05b84-115">인증서에 대해 내보낼 수 있는 개인 키가 할당 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="05b84-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="05b84-116">액세스에 지 서비스 (인증서 마법사의 **SIP 액세스에 지 외부** 라고 함)</span><span class="sxs-lookup"><span data-stu-id="05b84-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="05b84-117">웹 회의에 지 서비스 (인증서 마법사의 **웹 회의에 지 외부** 라고 함)</span><span class="sxs-lookup"><span data-stu-id="05b84-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="05b84-118">A/V 인증 서비스 (인증서 마법사의 **a/v에 지 외부** 라고 함)</span><span class="sxs-lookup"><span data-stu-id="05b84-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="05b84-119">내보낼 수 있는 개인 키를 사용 하 여 단일 내부 인증서를 만든 다음 각에 지 서버 내부 인터페이스에 복사 하 여 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="05b84-120">에 지 서버 (인증서 마법사에서에 **지 내부** 라고 함)</span><span class="sxs-lookup"><span data-stu-id="05b84-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="05b84-121">각에 지 서버 서비스에 대해 개별 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="05b84-122">A/V에 지 서비스 인증서에 대해 새 롤링 인증서 기능을 사용 하려는 경우에는 별도의 인증서를 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="05b84-123">이 기능의 경우에는 A/V에 지 서비스 인증서를 액세스에 지 서비스 및 웹 회의에 지 서비스와의 연결을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="05b84-124">각 서비스에 대해 별도의 인증서를 요청 하 고 취득 하 고 할당 하도록 선택한 경우 A/v에 지 서비스에 대해 개인 키를 내보낼 수 있도록 요청 하 고 (이는 실제로 A/V 인증 서비스를 수행 함) 각에 지 서버의 A/V에 지 외부 인터페이스에 동일한 인증서를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05b84-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05b84-125">See Also</span></span>


[<span data-ttu-id="05b84-126">Lync Server 2013 using Set-cscertificate in-Roll에서 AV 및 OAuth 인증서 준비</span><span class="sxs-lookup"><span data-stu-id="05b84-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="05b84-127">에 지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항</span><span class="sxs-lookup"><span data-stu-id="05b84-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

