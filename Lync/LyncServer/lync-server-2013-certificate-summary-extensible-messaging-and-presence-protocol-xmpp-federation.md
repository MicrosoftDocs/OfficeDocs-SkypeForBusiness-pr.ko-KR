---
title: 'Lync Server 2013: 인증서 요약-XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01b21c8b09d93f8d2788424f2c8f440e1dec66b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e47c3-102">인증서 요약-Lync Server 2013의 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="e47c3-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e47c3-103">_**마지막으로 수정한 주제:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="e47c3-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="e47c3-104">XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 파트너와 통신을 사용 하도록 설정 하 고 설정 하기 위한 인증서 요구 사항에 따라 XMPP 도메인의 추가 기록이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47c3-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="e47c3-105">인증서에 포함 된 레코드는 SAN (주체 대체 이름)으로 XMPP 통신에 참여할 수 있는 도메인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e47c3-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="e47c3-106">사용자의 하위 집합에 대해 XMPP를 사용 하는 경우 도메인은 전체 도메인에 대해 XMPP를 사용 하거나 하위 도메인 (예: corp.contoso.com, finance.contoso.com)을 선택할 수 있는 경우 루트 수준 도메인 (예: contoso.com)이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47c3-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e47c3-107">확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 인증서 요약</span><span class="sxs-lookup"><span data-stu-id="e47c3-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e47c3-108">요소가</span><span class="sxs-lookup"><span data-stu-id="e47c3-108">Component</span></span></th>
<th><span data-ttu-id="e47c3-109">주체 이름</span><span class="sxs-lookup"><span data-stu-id="e47c3-109">Subject name</span></span></th>
<th><span data-ttu-id="e47c3-110">SAN (주체 대체 이름)/Order</span><span class="sxs-lookup"><span data-stu-id="e47c3-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="e47c3-111">메모</span><span class="sxs-lookup"><span data-stu-id="e47c3-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e47c3-112">Edge 서버 또는 Edge 풀에 대 한 액세스에 지 서비스에 할당</span><span class="sxs-lookup"><span data-stu-id="e47c3-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="e47c3-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e47c3-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e47c3-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e47c3-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="e47c3-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e47c3-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="e47c3-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e47c3-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="e47c3-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e47c3-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e47c3-118">처음 세 개의 SAN 항목은 전체 Edge 서버에 대 한 일반적인 SAN 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e47c3-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="e47c3-119">Contoso.com는 루트 도메인 수준의 XMPP 파트너와 페더레이션 하는 데 필요한 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e47c3-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="e47c3-120">이 항목은 접미사 contoso.com를 가진 모든 도메인에 대해 XMPP를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47c3-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e47c3-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e47c3-121">See Also</span></span>


[<span data-ttu-id="e47c3-122">Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="e47c3-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="e47c3-123">Lync Server 2013의 에지 서버 인증서 계획</span><span class="sxs-lookup"><span data-stu-id="e47c3-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="e47c3-124">Lync Server 2013의 에지 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="e47c3-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="e47c3-125">요청-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e47c3-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="e47c3-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e47c3-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

