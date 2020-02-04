---
title: 원격 통화 제어를 위한 신뢰할 수 있는 응용 프로그램 항목 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfaec78b0c7d64308b5899a6e7dc5fa95c1f53fb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="dea1f-102">Lync Server 2013에서 원격 통화 제어를 위한 신뢰할 수 있는 응용 프로그램 항목 구성</span><span class="sxs-lookup"><span data-stu-id="dea1f-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dea1f-103">_**마지막으로 수정한 주제:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="dea1f-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="dea1f-104">SIP/CSTA 게이트웨이는 Lync Server가 게이트웨이로 호출을 라우팅하기 위해 고정 경로를 적용 하기 위해 신뢰할 수 있는 응용 프로그램으로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="dea1f-105">이전 버전의 Lync Server 배포에서 사용자를 마이그레이션하는 경우이 항목의 절차를 수행 하기 전에 SIP/CSTA 게이트웨이에 대해 만든 기존의 신뢰할 수 있는 모든 응용 프로그램 항목 (이전에 권한이 부여 된 호스트 항목으로 알려진)을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="dea1f-106">자세한 내용은 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013에서 레거시 권한 부여 된 호스트 제거 (선택 사항)</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dea1f-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="dea1f-107">TCP (전송 제어 프로토콜) 연결을 사용 하 여 새 원격 통화 제어를 배포 하려는 경우 새 신뢰할 수 있는 응용 프로그램에 대해 동일한 TCP 포트를 사용 하려는 경우 <STRONG>선택한 IP 주소에 대 한 서비스 사용량을</STRONG> 기존 신뢰할 수 있는 응용 프로그램 및 풀에서 설정 해야 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="dea1f-108">SIP/CSTA 게이트웨이에 대해 신뢰할 수 있는 응용 프로그램 항목을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="dea1f-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="dea1f-109">Lync Server Management 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins group의 구성원으로 로그온 하거나 **CsTrustedApplicationPool** cmdlet을 할당 한 모든 RBAC (역할 기반 액세스 제어) 역할을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="dea1f-110">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dea1f-111">신뢰할 수 있는 응용 프로그램 항목을 만들려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="dea1f-112">TLS (전송 계층 보안) 연결의 경우 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="dea1f-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="dea1f-114">TCP (전송 제어 프로토콜) 연결의 경우 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="dea1f-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="dea1f-116">신뢰 하는 응용 프로그램을 풀에 추가 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="dea1f-117">TLS 연결의 경우 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="dea1f-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="dea1f-119">TCP 연결의 경우 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="dea1f-120">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="dea1f-121">토폴로지에 대해 변경한 게시 된 변경 내용을 구현 하려면 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea1f-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dea1f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dea1f-122">See Also</span></span>


[<span data-ttu-id="dea1f-123">Lync Server 2013에서 원격 통화 제어에 대한 고정 경로 구성</span><span class="sxs-lookup"><span data-stu-id="dea1f-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="dea1f-124">Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의</span><span class="sxs-lookup"><span data-stu-id="dea1f-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

