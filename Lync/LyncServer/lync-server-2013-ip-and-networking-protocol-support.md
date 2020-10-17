---
title: 'Lync Server 2013: IP 및 네트워킹 프로토콜 지원'
description: 'Lync Server 2013: IP 및 네트워킹 프로토콜 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbd8022dd7197524334e0c70ea0ad875a30446de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553124"
---
# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Lync Server 2013의 IP 및 네트워킹 프로토콜 지원

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

Lync Server 2013에서는 다음과 같은 IP 및 네트워킹 프로토콜을 지원 합니다.

  - **IP 프로토콜**     Lync Server 2013는 서버 네트워크에 대해 IPv4 (IP 버전 4) 또는 IPv6 (IP 버전 6)을 지원 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013는 이중 IP 스택이 설정 된 네트워크에서 작동할 수 있습니다.

    
    </div>

  - **SIP 전송 프로토콜입니다.**     일반적으로 SIP는 사용자 데이터 그램 프로토콜 (UDP), TCP (전송 제어 프로토콜) 및 TLS (전송 계층 보안)를 세 가지 이상의 전송 유형으로 사용할 수 있습니다. 기본 SIP 전송 구성에서는 TLS가 TCP를 통해 실행 됩니다. TLS는 Lync Server 2013 네트워크 내에서 사용 됩니다. 네트워크의 경계에서 Lync Server 2013는 TCP를 통해 상호 운용할 수 있습니다. Lync Server 2013에서는 엔터프라이즈 통신 보안, 안정성 및 확장성에 대 한 최소 표준을 충족 하지 않으므로 SIP 전송에 대 한 UDP를 지원 하지 않습니다. 자세한 내용은 다음 홉 블로그 문서, "udp 또는 UDP를 참조 하세요." (해당 되는 경우)를 참고 하세요 [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369) .
    
    <div>
    

    > [!NOTE]  
    > 각 블로그의 콘텐츠와 해당 URL은 사전 통지 없이 변경될 수 있습니다.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

