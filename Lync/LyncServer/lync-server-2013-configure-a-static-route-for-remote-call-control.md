---
title: 'Lync Server 2013: 원격 통화 제어에 대 한 고정 경로 구성'
description: 'Lync Server 2013: 원격 통화 제어에 대 한 고정 경로를 구성 합니다.'
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
ms.openlocfilehash: 8ecf6478d4fb7ab4f04f8a452d4837b327ba254a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551694"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-22_

원격 통화 제어를 사용 하려면 모든 Lync Server 풀이 PBX (private branch exchange)에 연결 되는 SIP/CSTA 게이트웨이로 해당 풀의 경로를 사용 하 여 구성 되어야 합니다. 이 경로에서는 각 풀에 풀이 통화와 연결된 SIP 통화 제어 메시지를 PBX에 프록시하는 각 게이트웨이에 대한 정적 경로가 한 개씩 있어야 합니다. 원격 통화 제어를 위한 전역 고정 경로를 구성하면 해당 풀 수준에서 고정 경로를 사용하여 구성되지 않은 각 풀에 전역 고정 경로가 사용됩니다.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>원격 통화 제어를 위한 고정 경로를 구성하려면

1.  Lync Server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 **새-CsStaticRoute** cmdlet이 할당 된 RBAC (역할 기반 액세스 제어) 역할을 하는 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  고정 경로를 만들고 이 경로를 $TLSRoute 또는 $TCPRoute 변수에 넣으려면 다음 중 하나를 수행합니다.
    
    <div class="">
    

    > [!TIP]  
    > 도메인의 자식 도메인을 일치시키려면 MatchUri 매개 변수에서 와일드카드 값을 지정하면 됩니다(예: <STRONG>*.contoso.net</STRONG>). 해당 값은 <STRONG>contoso.net</STRONG> 접미사로 끝나는 모든 도메인과 일치합니다.

    
    </div>
    
      - TLS(전송 계층 보안) 연결의 경우 명령 프롬프트에 다음을 입력합니다.
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        예:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        UseDefaultCertificate가 False로 설정된 경우 TLSCertIssuer 및 TLSCertSerialNumber 매개 변수를 지정해야 합니다. 이 매개 변수는 각각 고정 경로에서 사용된 인증서를 발급한 CA(인증 기관)의 이름, 해당 TLS 인증서의 일련 번호를 나타냅니다. 이러한 매개 변수에 대 한 자세한 내용은 명령 프롬프트에서 다음을 입력 하 여 Lync Server Management Shell Help를 참조 하십시오.
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - TCP(Transmission Control Protocol) 연결의 경우 명령 프롬프트에 다음을 입력합니다.
        
        <div class="">
        

        > [!NOTE]  
        > FQDN(정규화된 도메인 이름)을 지정한 경우 DNS(도메인 이름 시스템) A 레코드를 먼저 구성해야 합니다.

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        예:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        다음은 고정 경로에 대한 선택적 매개 변수의 기본값입니다.
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        이러한 기본값은 변경하지 않는 것이 좋습니다. 그러나 이러한 매개 변수를 변경 해야 하는 경우 명령 프롬프트에 다음을 입력 하 여 Lync Server Management Shell Help를 참조 하세요.
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


[Lync Server 2013에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

