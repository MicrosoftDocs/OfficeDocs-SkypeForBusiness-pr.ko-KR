---
title: 'Lync Server 2013: 인증서 요약-공용 인스턴트 메시징 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cacf411f348199376e1564be37f683854480872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="213ce-102">인증서 요약-Lync Server 2013의 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="213ce-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="213ce-103">_**마지막으로 수정 된 항목:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="213ce-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="213ce-104">공용 인스턴트 메시징 연결에 대 한 인증서를 구성 하려면 AOL (북미)에 고유 해야 하는 경우를 제외 하 고는 다른 SIP 페더레이션 형식 또는 표준에 지 서버 인증서와는 다른 것이 무엇 인지 확인 해야 합니다. 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="213ce-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="213ce-105">미국 온라인에서는 일반적인 서버 EKU (확장 된 키 사용) 외에도 클라이언트 EKU를 포함 하도록 인증서 또는 인증서 (에 지 풀의 경우)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="213ce-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="213ce-106">클라이언트 EKU는 인증서에 추가 되며,에 지 서버에 할당 된 외부 공용 인증서의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="213ce-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="213ce-107">인증서 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="213ce-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="213ce-108">구성 요소</span><span class="sxs-lookup"><span data-stu-id="213ce-108">Component</span></span></th>
<th><span data-ttu-id="213ce-109">주체 이름</span><span class="sxs-lookup"><span data-stu-id="213ce-109">Subject name</span></span></th>
<th><span data-ttu-id="213ce-110">SAN(주체 대체 이름)/순서</span><span class="sxs-lookup"><span data-stu-id="213ce-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="213ce-111">설명</span><span class="sxs-lookup"><span data-stu-id="213ce-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="213ce-112">외부/액세스 에지</span><span class="sxs-lookup"><span data-stu-id="213ce-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="213ce-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="213ce-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="213ce-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="213ce-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="213ce-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="213ce-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="213ce-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="213ce-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="213ce-117">이 인증서는 공용 CA에서 발급 한 것 이어야 하며, AOL과의 공용 IM 연결을 배포 하려면 서버 EKU 및 클라이언트 EKU가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="213ce-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="213ce-118">인증서는 다음에 대 한 외부에 지 서버 인터페이스에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="213ce-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="213ce-119">Access Edge service(액세스 에지 서비스)</span><span class="sxs-lookup"><span data-stu-id="213ce-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="213ce-120">웹 회의 에지 서비스</span><span class="sxs-lookup"><span data-stu-id="213ce-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="213ce-121">A/V 에지 서비스</span><span class="sxs-lookup"><span data-stu-id="213ce-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="213ce-p103">SAN은 토폴로지 작성기에서 사용자의 정의에 따라 인증서에 자동으로 추가됩니다. 필요에 따라 추가 SIP 도메인 및 지원이 필요한 다른 항목에 대해 SAN 항목을 추가할 수 있습니다. 주체 이름은 SAN에 복제되며 올바른 작업을 위해서는 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="213ce-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="213ce-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="213ce-125">See Also</span></span>


[<span data-ttu-id="213ce-126">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="213ce-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

