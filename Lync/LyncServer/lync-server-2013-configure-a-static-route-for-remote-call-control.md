---
title: 'Lync Server 2013: 원격 통화 제어에 대한 고정 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfb825e51a9beec7010f9f46ed0fc649267897fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="cc5c1-102">Lync Server 2013에서 원격 통화 제어에 대한 고정 경로 구성</span><span class="sxs-lookup"><span data-stu-id="cc5c1-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc5c1-103">_**마지막으로 수정한 주제:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="cc5c1-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="cc5c1-104">원격 통화 제어를 위해서는 모든 Lync Server 풀이 PBX (개인 분기 교환)에 연결 되는 SIP/CSTA 게이트웨이로 해당 풀의 경로로 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="cc5c1-105">이 경로는 각 풀에 PBX 호출에 연결 된 SIP 통화 제어 메시지를 프록시 하는 각 게이트웨이에 대해 하나의 고정 경로가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="cc5c1-106">원격 통화 제어에 대해 전역 고정 경로를 구성 하는 경우 풀 수준에서 고정 경로로 구성 되지 않은 각 풀은 전역 고정 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="cc5c1-107">원격 통화 제어를 위해 고정 경로를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="cc5c1-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="cc5c1-108">Lync Server Management 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins group의 구성원으로 로그온 하거나 **새 CsStaticRoute** cmdlet을 할당 한 RBAC (역할 기반 액세스 제어) 역할을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="cc5c1-109">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cc5c1-110">고정 경로를 만들어 변수 $TLSRoute 또는 $TCPRoute에 놓으려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="cc5c1-111">도메인의 자식 도메인을 일치 시키려면 MatchUri 매개 변수에서 와일드 카드 값을 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="cc5c1-112">예를 들어 <STRONG>\*. contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="cc5c1-113">이 값은 접미사 <STRONG>contoso.net</STRONG>로 끝나는 모든 도메인과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="cc5c1-114">TLS (전송 계층 보안) 연결의 경우 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="cc5c1-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="cc5c1-116">UseDefaultCertificate가 False로 설정 된 경우 TLSCertIssuer 및 TLSCertSerialNumber 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="cc5c1-117">이러한 매개 변수는 고정 경로에 사용 되는 인증서를 발급 한 CA (인증 기관)의 이름과 해당 TLS 인증서의 일련 번호를 각각 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="cc5c1-118">이러한 매개 변수에 대 한 자세한 내용은 명령 프롬프트에서 다음을 입력 하 여 Lync Server Management Shell 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="cc5c1-119">TCP (전송 제어 프로토콜) 연결의 경우 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="cc5c1-120">FQDN (정규화 된 도메인 이름)을 지정 하는 경우 먼저 DNS (Domain Name System) 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="cc5c1-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="cc5c1-122">정적 경로의 선택적 매개 변수에 대 한 기본값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="cc5c1-123">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="cc5c1-123">Enabled = True</span></span>
        
          - <span data-ttu-id="cc5c1-124">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="cc5c1-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="cc5c1-125">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="cc5c1-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="cc5c1-126">이러한 기본값을 변경 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="cc5c1-127">그러나 이러한 매개 변수를 변경 해야 하는 경우 명령 프롬프트에서 다음을 입력 하 여 Lync Server Management Shell 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="cc5c1-128">중앙 관리 저장소에 새로 만든 고정 경로를 유지 하려면 적절 하 게 다음 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc5c1-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc5c1-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc5c1-129">See Also</span></span>


[<span data-ttu-id="cc5c1-130">Lync Server 2013에서 원격 통화 제어를 위한 신뢰할 수 있는 응용 프로그램 항목 구성</span><span class="sxs-lookup"><span data-stu-id="cc5c1-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="cc5c1-131">Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의</span><span class="sxs-lookup"><span data-stu-id="cc5c1-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

