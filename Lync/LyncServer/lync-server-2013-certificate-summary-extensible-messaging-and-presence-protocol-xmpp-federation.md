---
title: 'Lync Server 2013: 인증서 요약-XMPP (Extensible messaging and 거점 protocol) 페더레이션'
description: 'Lync Server 2013: 인증서 요약-XMPP (Extensible messaging and 거점 protocol) 페더레이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e2bb593d909c2eec6032dc89c07cc5f5b1a72db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572344"
---
# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="dffbc-103">Lync Server 2013의 인증서 요약-XMPP (Extensible messaging and 현재 상태 프로토콜) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="dffbc-103">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dffbc-104">_**마지막으로 수정 된 항목:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="dffbc-104">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="dffbc-105">XMPP (extensible messaging and 현재 상태 프로토콜) 파트너와의 통신을 사용 하도록 설정 하 고 설정 하기 위한 인증서 요구 사항에 따라 XMPP 도메인을 추가로 기록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffbc-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="dffbc-106">인증서에 포함 된 레코드는 SAN (주체 대체 이름)으로 XMPP 통신에 참가할 수 있는 도메인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dffbc-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="dffbc-107">사용자 하위 집합에 XMPP를 사용 하도록 설정 하는 경우 도메인은 루트 수준 도메인 (예: contoso.com)이 될 수 있으며, 전체 도메인에 대해 XMPP를 설정 하거나 하위 도메인 (예: corp.contoso.com, finance.contoso.com)을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dffbc-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="dffbc-108">XMPP(Extensible Messaging and Presence Protocol)의 인증서 요약</span><span class="sxs-lookup"><span data-stu-id="dffbc-108">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dffbc-109">구성 요소</span><span class="sxs-lookup"><span data-stu-id="dffbc-109">Component</span></span></th>
<th><span data-ttu-id="dffbc-110">주체 이름</span><span class="sxs-lookup"><span data-stu-id="dffbc-110">Subject name</span></span></th>
<th><span data-ttu-id="dffbc-111">SAN(주체 대체 이름)/순서</span><span class="sxs-lookup"><span data-stu-id="dffbc-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="dffbc-112">설명</span><span class="sxs-lookup"><span data-stu-id="dffbc-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dffbc-113">에 지 서버 또는에 지 풀에 대 한 액세스에 지 서비스 할당</span><span class="sxs-lookup"><span data-stu-id="dffbc-113">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="dffbc-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dffbc-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dffbc-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dffbc-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="dffbc-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dffbc-116">sip.contoso.com</span></span></p>
<p><span data-ttu-id="dffbc-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="dffbc-117">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="dffbc-118">contoso.com</span><span class="sxs-lookup"><span data-stu-id="dffbc-118">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dffbc-119">처음 세 개의 SAN 항목은 전체에 지 서버에 대 한 일반 SAN 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="dffbc-119">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="dffbc-120">contoso.com은 루트 도메인 수준에서 XMPP 파트너와의 페더레이션을 위해 필요한 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="dffbc-120">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="dffbc-121">이 항목은 contoso.com 접미사를 가진 모든 도메인에 대해 XMPP를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dffbc-121">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dffbc-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dffbc-122">See Also</span></span>


[<span data-ttu-id="dffbc-123">Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="dffbc-123">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="dffbc-124">Lync Server 2013의에 지 서버 인증서 계획</span><span class="sxs-lookup"><span data-stu-id="dffbc-124">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="dffbc-125">Lync Server 2013에 대 한에 지 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="dffbc-125">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="dffbc-126">요청-Set-cscertificate</span><span class="sxs-lookup"><span data-stu-id="dffbc-126">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="dffbc-127">Set-cscertificate</span><span class="sxs-lookup"><span data-stu-id="dffbc-127">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

