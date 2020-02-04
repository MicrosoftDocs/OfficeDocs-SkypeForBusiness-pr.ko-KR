---
title: 호스트되는 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>호스트되는 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

이 항목에서는 Lync Server 2013 Edge 서버에서 Microsoft Exchange Online과 같은 호스팅된 Exchange 서비스로 라우팅하는 데 필요한 DNS (Domain Name System) SRV 레코드를 구성 하는 방법에 대해 설명 합니다.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>호스팅된 Exchange 서비스에 대 한 외부 DNS SRV 레코드를 만들려면

1.  DnsAdmins 그룹의 구성원으로 외부 DNS 서버에 로그온 합니다.

2.  **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 합니다.

3.  SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 하 고 Lync Server 2013을 설치할 SIP 도메인을 선택 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server를 설치 하려는 SIP 도메인에서 DNS SRV 레코드를 만들어야 합니다. SRV 레코드를 만들 때이 서비스 필드를 제공 하는 호스트에 사용 되는 FQDN이 Edge 풀의 외부 FQDN 이어야 합니다. 예를 들어 Edge 풀의 외부 FQDN이 edge01.contoso.net 인 경우 해당 값을 입력 합니다. 이는 DNS 호스트 (A) 레코드와 동일한 도메인에도 있어야 합니다.

    
    </div>

4.  선택한 도메인을 마우스 오른쪽 단추로 클릭 한 다음 **다른 새 레코드**를 클릭 합니다.

5.  **리소스 레코드 종류**에서 **서비스 위치 (SRV)** 를 클릭 한 다음 **레코드 만들기**를 클릭 합니다.

6.  **새 리소스 레코드**에서 **서비스**를 클릭 한 다음 ** \_sipfederationtls**를 입력 합니다.

7.  **프로토콜**을 클릭 한 다음 ** \_tcp**를 입력 합니다.

8.  **포트 번호**를 클릭 한 다음 **5061**을 입력 합니다.

9.  **이 서비스를 제공**하는 호스트를 클릭 한 다음 신뢰할 수 있는 외부 클라이언트에 대 한 lync server 2013 시스템에 대 한 액세스를 제공 하는 lync Server 2013 Edge 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다.
    
    <div>
    

    > [!NOTE]
    > 또한 도메인은 Exchange Online 설정에서 신뢰할 수 있는 허용 도메인으로 설정 해야 합니다. 자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>허용 도메인 만들기를 참조 하세요.

    
    </div>

10. **확인**을 클릭 한 다음 **완료**를 클릭 합니다.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>DNS SRV 레코드가 성공적으로 만들어졌는지 확인 하려면

1.  도메인의 클라이언트 컴퓨터에 로그온 합니다.

2.  **시작**을 클릭 한 다음 **실행**을 클릭 합니다.

3.  명령 프롬프트에서 다음 명령을 실행 합니다.
    
        nslookup <FQDN Lync Edge Pool>

4.  FQDN에 대 한 적절 한 IP 주소로 확인 되는 회신을 수신 하 고 있는지 확인 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 역방향 프록시 서버에 대한 DNS 레코드 만들기](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

