---
title: Lync Server 2013:에 지 지원에 대 한 DNS 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e22228ec089f5632f30d4eabc2e8c32d87b5e2d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Lync Server 2013에서에 지 지원에 대 한 DNS 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-15_

내부 및 외부 에지 인터페이스(에지 서버 및 역방향 프록시 인터페이스를 모두 포함)에 대해 DNS(Domain Name System) 레코드를 구성해야 합니다. 기본적으로 에지 서버는 도메인에 연결되지 않으며 FQDN(정규화된 도메인 이름)을 갖지 않습니다. 에지 서버는 정규화된 도메인 이름이 아닌 짧은 (컴퓨터) 이름으로만 참조됩니다. 그러나 토폴로지 작성기는 짧은 이름이 아닌 Fqdn을 사용 합니다. 에 지 서버의 이름은 토폴로지 작성기에서 사용 하는 FQDN과 일치 해야 합니다. 이를 위해 DNS 접미사를 정의하고 컴퓨터 이름과 결합하면 필요한 FQDN이 만들어집니다. 컴퓨터 이름에 DNS 접미사를 추가하려면 "도메인에 가입되지 않은 에지 서버에서 컴퓨터 이름에 DNS 접미사를 추가하려면"에 있는 다음 절차를 따르십시오.

<div>


> [!NOTE]  
> 기본적으로 DNS는 라운드 로빈 알고리즘을 사용 하 여 쿼리 된 DNS 도메인 이름에 대해 같은 유형의 여러 리소스 레코드가 있는 리소스 레코드 데이터의 순서를 순환에 따라 회전 합니다. Lync Server 2013 DNS 부하 분산은 dns 부하 분산 메커니즘의 일부로 DNS 라운드 로빈에 따라 달라 집니다. 라운드 로빈 설정이 사용 하지 않도록 설정 되어 있는지 확인 합니다. Windows 운영 체제를 실행 하 고 있지 않은 DNS 서버를 사용 하는 경우 라운드 로빈 리소스 레코드 순서가 사용 하도록 설정 되어 있는지 확인 합니다.



</div>

"**DNS srv 레코드를 만들려면**"의 다음 절차를 사용 하 여 각 dns srv 레코드를 만들고 확인 합니다. "**Dns a 레코드를 만들려면**"의 절차를 사용 하 여 외부 사용자 액세스에 필요한 DNS a 레코드를 정의 합니다. 레코드가 구성 되 고 올바르게 작동 하는지 확인 하려면이 항목의 "**DNS 레코드를 확인 하려면**"을 참조 하십시오. 외부 사용자 액세스를 지 원하는 데 필요한 각 레코드에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)을 참조 하십시오.

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>도메인에 연결되지 않은 에지 서버의 컴퓨터 이름에 DNS 접미사를 추가하려면

1.  컴퓨터에서 **시작**을 클릭하고 **컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.

2.  **컴퓨터 이름, 도메인 및 작업 그룹 설정**에서 **설정 변경**을 클릭합니다.

3.  **컴퓨터 이름** 탭에서 **변경**을 클릭합니다.

4.  **컴퓨터 이름/도메인 변경**에서 **자세히**를 클릭합니다.

5.  **DNS 접미사 및 NetBIOS 컴퓨터 이름**의 **이 컴퓨터의 주 DNS 접미사**에 내부 도메인의 이름(예: corp.contoso.com)을 입력하고 **확인**을 세 번 클릭합니다.

6.  컴퓨터를 다시 시작합니다.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>DNS SRV 레코드를 만들려면

1.  해당 DNS 서버에서 **시작**, **제어판**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 1) 원격 사용자 및 페더레이션 파트너가 외부 DNS를 조회 하기 위한 외부 DNS 항목을 갖도록 DNS를 구성 해야 합니다. 2) 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함) 내의에 지 서버에서 사용할 DNS 조회 항목을 포함 하 여 Lync Server 2013를 실행 하는 내부 서버의 레코드를 포함할 수 있습니다. 3) 내부 클라이언트 및 Lync Server 2013을 실행 하는 서버에서 조회 하기 위한 내부 DNS 항목

    
    </div>

2.  SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013이 설치 된 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **다른 새 레코드**를 클릭합니다.

4.  **리소스 레코드 종류 선택**에서 **서비스 위치(SRV)** 를 입력한 다음 **레코드 만들기**를 클릭합니다.

5.  DNS SRV 레코드에 필요한 모든 정보를 제공합니다.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>DNS A 레코드를 만들려면

1.  DNS 서버에서 **시작**, **제어판**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

2.  SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013이 설치 된 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **새 호스트(A)** 를 클릭합니다.

4.  DNS SRV 레코드에 필요한 모든 정보를 제공합니다.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>DNS 레코드를 확인하려면

1.  도메인의 클라이언트 컴퓨터에 로그온합니다.

2.  **시작**을 클릭한 다음 **실행**을 클릭합니다.

3.  명령 프롬프트에서 다음 명령을 실행합니다.
    
        nslookup <FQDN edge interface>

4.  FQDN에 대해 적절한 IP 주소로 확인되는 응답이 수신되는지 확인합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[호스팅된 Exchange UM과의 통합을 위한 DNS SRV 레코드 만들기](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

