---
title: 호스팅된 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기
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
ms.openlocfilehash: c30164813619a271f2321db3ff3e8019067193c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>호스팅된 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

이 항목에서는 Lync Server 2013에 지 서버에서 Microsoft Exchange Online과 같은 호스팅된 Exchange 서비스로 라우팅하기 위해 필요한 DNS (Domain Name System) SRV 레코드를 구성 하는 방법을 설명 합니다.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>호스트된 Exchange 서비스에 대해 외부 DNS SRV 레코드를 만들려면

1.  DnsAdmins 그룹의 구성원으로 외부 DNS 서버에 로그온합니다.

2.  **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

3.  SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 하 고 Lync Server 2013을 설치할 SIP 도메인을 선택 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server가 현재 설치되어 있거나 설치될 예정인 SIP 도메인에서 DNS SRV 레코드를 만들어야 합니다. SRV 레코드를 만들 때 이 서비스를 제공하는 호스트 필드에 사용되는 FQDN은 에지 풀의 외부 FQDN이어야 합니다. 예를 들어 에지 풀의 외부 FQDN이 edge01.contoso.net인 경우 해당 값을 입력합니다. 또한 이 FQDN은 DNS 호스트(A) 레코드와 같은 도메인에 있어야 합니다.

    
    </div>

4.  선택한 도메인을 마우스 오른쪽 단추로 클릭하고 **다른 새 레코드**를 클릭합니다.

5.  **리소스 레코드 종류**에서 **서비스 위치(SRV)** 를 클릭하고 **레코드 만들기**를 클릭합니다.

6.  **새 리소스 레코드**에서 **서비스**를 클릭 하 고 ** \_sipfederationtls**를 입력 합니다.

7.  **프로토콜**을 클릭 한 다음 ** \_tcp**를 입력 합니다.

8.  **포트 번호**를 클릭한 다음 **5061**을 입력합니다.

9.  **이 서비스를 제공**하는 호스트를 클릭 한 다음 신뢰할 수 있는 외부 클라이언트에 대해 lync server 2013 시스템에 대 한 액세스를 제공 하는 lync server 2013에 지 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다.
    
    <div>
    

    > [!NOTE]
    > 이 도메인은 Exchange Online 설정에서 허용되는 신뢰할 수 있는 도메인으로도 설정되어야 합니다. 자세한 내용은 허용 도메인 만들기를 참조 하십시오 <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.

    
    </div>

10. **확인**을 클릭한 다음 **완료**를 클릭합니다.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>DNS SRV 레코드가 올바르게 만들어졌는지 확인하려면

1.  도메인의 클라이언트 컴퓨터에 로그온합니다.

2.  **시작**을 클릭한 다음 **실행**을 클릭합니다.

3.  명령 프롬프트에서 다음 명령을 실행합니다.
    
        nslookup <FQDN Lync Edge Pool>

4.  FQDN에 대해 적절한 IP 주소로 확인되는 응답이 수신되는지 확인합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 역방향 프록시 서버에 대 한 DNS 레코드 만들기](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

