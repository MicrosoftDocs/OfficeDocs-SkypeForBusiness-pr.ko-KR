---
title: 'Lync Server 2013: 원격 통화 제어에 대한 고정 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11b24fc8d4be54f5645853c050891d3821945e4
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40984637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013에서 원격 통화 제어에 대한 고정 경로 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-22_

원격 통화 제어를 위해서는 모든 Lync Server 풀이 PBX (개인 분기 교환)에 연결 되는 SIP/CSTA 게이트웨이로 해당 풀의 경로로 구성 되어 있어야 합니다. 이 경로는 각 풀에 PBX 호출에 연결 된 SIP 통화 제어 메시지를 프록시 하는 각 게이트웨이에 대해 하나의 고정 경로가 있어야 합니다. 원격 통화 제어에 대해 전역 고정 경로를 구성 하는 경우 풀 수준에서 고정 경로로 구성 되지 않은 각 풀은 전역 고정 경로를 사용 합니다.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>원격 통화 제어를 위해 고정 경로를 구성 하려면

1.  Lync Server Management 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins group의 구성원으로 로그온 하거나 **새 CsStaticRoute** cmdlet을 할당 한 RBAC (역할 기반 액세스 제어) 역할을 사용 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  고정 경로를 만들어 변수 $TLSRoute 또는 $TCPRoute에 놓으려면 다음 중 하나를 수행 합니다.
    
    <div class="">
    

    > [!TIP]  
    > 도메인의 자식 도메인을 일치 시키려면 MatchUri 매개 변수에서 와일드 카드 값을 지정 하면 됩니다. 예를 들어 <STRONG>*. contoso.net</STRONG>. 이 값은 접미사 <STRONG>contoso.net</STRONG>로 끝나는 모든 도메인과 일치 합니다.

    
    </div>
    
      - TLS (전송 계층 보안) 연결의 경우 명령 프롬프트에 다음을 입력 합니다.
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        예를 들면 다음과 같습니다.
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        UseDefaultCertificate가 False로 설정 된 경우 TLSCertIssuer 및 TLSCertSerialNumber 매개 변수를 지정 해야 합니다. 이러한 매개 변수는 고정 경로에 사용 되는 인증서를 발급 한 CA (인증 기관)의 이름과 해당 TLS 인증서의 일련 번호를 각각 나타냅니다. 이러한 매개 변수에 대 한 자세한 내용은 명령 프롬프트에서 다음을 입력 하 여 Lync Server Management Shell 도움말을 참조 하세요.
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - TCP (전송 제어 프로토콜) 연결의 경우 명령 프롬프트에 다음을 입력 합니다.
        
        <div class="">
        

        > [!NOTE]  
        > FQDN (정규화 된 도메인 이름)을 지정 하는 경우 먼저 DNS (Domain Name System) 레코드를 구성 해야 합니다.

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        예를 들면 다음과 같습니다.
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        정적 경로의 선택적 매개 변수에 대 한 기본값은 다음과 같습니다.
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        이러한 기본값을 변경 하지 않는 것이 좋습니다. 그러나 이러한 매개 변수를 변경 해야 하는 경우 명령 프롬프트에서 다음을 입력 하 여 Lync Server Management Shell 도움말을 참조 하세요.
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  중앙 관리 저장소에 새로 만든 고정 경로를 유지 하려면 적절 하 게 다음 중 하나를 실행 합니다.
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 원격 통화 제어를 위한 신뢰할 수 있는 응용 프로그램 항목 구성](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

