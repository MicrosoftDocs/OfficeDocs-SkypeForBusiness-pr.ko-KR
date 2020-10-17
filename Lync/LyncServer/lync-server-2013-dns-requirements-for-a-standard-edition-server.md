---
title: 'Lync Server 2013: Standard Edition Server에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c88a76939e07a3b2306f46dc4930fa2b180404df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528915"
---
# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="270a5-102">Lync Server 2013의 Standard Edition server에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="270a5-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="270a5-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="270a5-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="270a5-104">이 섹션에서는 Standard Edition 서버를 배포하는 데 필요한 DNS(Domain Name System) 레코드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="270a5-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="270a5-105">Standard Edition 서버에 대한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="270a5-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="270a5-106">다음 표에서는 Lync Server 2013 Standard Edition Server 배포에 대 한 DNS 요구 사항을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="270a5-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="270a5-107">배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="270a5-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="270a5-108">DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="270a5-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="270a5-109">Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="270a5-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="270a5-110">서버의 FQDN(정규화된 도메인 이름)을 해당 IP 주소로 확인하는 내부 A 레코드</span><span class="sxs-lookup"><span data-stu-id="270a5-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="270a5-111">자동 클라이언트 로그인</span><span class="sxs-lookup"><span data-stu-id="270a5-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="270a5-112">지원 되는 각 SIP 도메인에 대해 _sipinternaltls에 대 한 SRV 레코드 _tcp. &gt;로그인 하는 클라이언트 요청을 인증 하 고 리디렉션하는 Standard Edition 서버의 FQDN에 매핑되는 포트 5061의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="270a5-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="270a5-113">자세한 내용은 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항을</a>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="270a5-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="270a5-114">UC(통합 통신) 장치를 통한 장치 업데이트 웹 서비스 검색</span><span class="sxs-lookup"><span data-stu-id="270a5-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="270a5-115">이름이 &lt; c s p 2 인 내부 A 레코드 &gt; Standard Edition server 호스팅 장치 업데이트 웹 서비스의 IP 주소로 확인 되는 SIP 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="270a5-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="270a5-116">UC 장치가 설정되었지만 사용자가 장치에 로그인하지 않은 상황에서 A 레코드를 사용하면 장치가 장치 업데이트 웹 서비스를 호스팅하는 서버를 검색하고 업데이트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="270a5-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="270a5-117">그렇지 않은 경우 장치는 사용자가 처음 로그인할 때 인밴드 프로비전을 통해 이 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="270a5-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="270a5-118">자세한 내용은 작업 설명서에서 <a href="lync-server-2013-device-update-web-service.md">Lync Server 2013의 장치 업데이트 웹 서비스</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="270a5-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="270a5-119">HTTP 트래픽을 지원하는 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="270a5-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="270a5-120">외부 웹 팜 FQDN을 역방향 프록시의 외부 IP 주소로 확인하는 외부 A 레코드.</span><span class="sxs-lookup"><span data-stu-id="270a5-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="270a5-121">클라이언트와 UC 장치는 이 레코드를 사용하여 역방향 프록시에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="270a5-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="270a5-122">자세한 내용은 계획 설명서에서 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013에 대 한 DNS 요구 사항 결정</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="270a5-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="270a5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="270a5-123">See Also</span></span>


[<span data-ttu-id="270a5-124">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="270a5-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="270a5-125">Lync Server 2013에 대 한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="270a5-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="270a5-126">Lync Server 2013의 장치 업데이트 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="270a5-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

