---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed16ac6b8aceea6828b600ce18da8b9a72827846
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>페더레이션 경로 및 미디어 트래픽 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-15_

페더레이션은 서로 다른 조직의 사용자가 네트워크 경계를 통해 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간의 신뢰 관계입니다. Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 Lync Server 2010 Edge 서버의 페더레이션 경로에서 Lync Server 2013 Edge 서버의 페더레이션 경로로 전환 해야 합니다.

단일 사이트 배포의 경우 다음 절차를 사용 하 여 Lync Server 2010 Edge 서버 및 디렉터에서 Lync server 2013 Edge 서버로의 페더레이션 경로와 미디어 트래픽 경로를 전환 합니다.

<div>


> [!IMPORTANT]  
> 페더레이션 경로와 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Lync Server 2010 Edge 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다. 또한이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미 합니다. 최소한의 사용자 작업을 예상 하는 동안 가동 중지 시간을 예약 해야 합니다. 또한 최종 사용자에 게 충분 한 알림을 제공 해야 합니다. 이 중단에 대 한 계획을 수립 하 고 조직 내에서 적절 한 기대치를 설정 하세요.



</div>

<div>


> [!IMPORTANT]  
> 레거시 Lync Server 2010 Edge 서버가 액세스 경계 서비스, 웹 회의에 지 서비스, 그리고 A/V Edge 서비스에 대해 동일한 FQDN을 사용 하도록 구성 된 경우이 섹션의 절차는 지원 되지 않습니다. 레거시 Edge 서비스가 동일한 FQDN을 사용 하도록 구성 된 경우에는 먼저 Lync server 2010에서 Lync server 2013로 모든 사용자를 마이그레이션한 다음 lync server 2013 edge 서버에서 페더레이션을 사용 하기 전에 Lync 서버 2010 Edge 서버의 서비스를 해제 해야 합니다.



</div>

<div>


> [!IMPORTANT]  
> XMPP 페더레이션이 Lync Server 2013 Edge 서버를 통해 라우팅된 경우, 모든 사용자가 Lync Server 2013로 이동할 때까지 레거시 Lync Server 2010 사용자가 XMPP 페더레이션 파트너와 통신할 수 없습니다. XMPP 정책 및 인증서가 구성 된 XMPP 페더레이션 파트너는 Lync Server 2013에서 구성 되었고 마지막으로 DNS 항목이 업데이트 되었습니다.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거 하려면

1.  Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기의 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **Lync Server**바로 아래에 있는 사이트 노드로 이동 합니다.

3.  사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

4.  왼쪽 창에서 **페더레이션 경로**를 선택 합니다.

5.  **사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용** 확인란의 선택을 취소 하 여 레거시 Lync Server 2010 환경을 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.
    
    ![속성 편집 대화 상자, 페더레이션 경로 페이지](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로 페이지")

6.  **확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.

7.  **토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.

8.  **작업** 메뉴에서 **토폴로지 게시**를 클릭 합니다.

9.  **다음** 을 클릭 하 여 게시 프로세스를 완료 하 고 게시 프로세스가 완료 되 면 **마침을** 클릭 합니다.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>레거시 Edge 서버를 비 페더레이션에 지 서버를 구성 하려면

1.  왼쪽 창에서 **Lync Server 2010** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.

2.  Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

3.  왼쪽 창에서 **일반** 을 선택 합니다.

4.  **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란 항목을 선택 취소 하 고 **확인** 을 선택 하 여 페이지를 닫습니다.
    
    ![속성, 일반, 페더레이션 사용],(images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "속성 지우기, 일반, 선택 취소 페더레이션 사용") 을 편집 합니다.

5.  **작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.

6.  **게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.

7.  레거시 Edge 서버에 대 한 페더레이션이 비활성화 되어 있는지 확인 합니다.
    
    ![토폴로지 작성기, Edge 풀, 페더레이션](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "이 불가능 한 토폴로지 작성기, Edge 풀, 페더레이션이 불가능 함")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Lync Server 2010 Edge 서버에서 인증서를 구성 하려면

1.  개인 키가 있는 외부 액세스 프록시 인증서를 레거시 Lync Server 2010 Edge 서버에서 내보냅니다.

2.  Lync Server 2013 Edge 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.

3.  액세스 프록시 외부 인증서를 Edge 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.

4.  Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 신뢰할 수 있는 CA에서 요청 하 고 할당 해야 합니다.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Lync server 2013 Edge 서버를 사용 하도록 Lync Server 2010 페더레이션 경로를 변경 하려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.

2.  Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

3.  왼쪽 창에서 **일반** 을 선택 합니다.

4.  **이 Edge 풀의 페더레이션 사용 (포트 5061)** 에 대 한 확인란 항목을 선택한 다음 **확인** 을 클릭 하 여 페이지를 닫습니다.
    
    ![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")

5.  **작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.

6.  **게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.

7.  **페더레이션 (포트 5061)** 이 **사용**으로 설정 되어 있는지 확인 합니다.
    
    ![토폴로지 작성기, Edge 풀, 페더레이션 사용](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "토폴로지 작성기, Edge 풀, 페더레이션 사용")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Lync Server 2013 Edge 서버 페더레이션 다음 홉을 업데이트 하려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.

2.  노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

3.  **일반** 페이지의 **다음 홉 선택**아래에 있는 드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.
    
    ![속성 편집 대화 상자의 다음 홉 페이지](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "속성 편집 대화 상자에서 다음 홉 페이지")

4.  **확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.

5.  **토폴로지 작성기**에서 최상위 노드 **Lync 서버** 를 선택 합니다.

6.  **작업** 메뉴에서 **토폴로지 게시** 를 클릭 하 고 마법사를 완료 합니다.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Lync Server 2013 Edge 서버 아웃 바운드 미디어 경로를 구성 하려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래에 있는 풀로 이동 합니다.

2.  풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

3.  **연결** 섹션에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 확인란을 선택 합니다.
    
    ![속성 편집, 일반, edge 풀 연결](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "속성 편집, 일반, edge 풀 연결")

4.  드롭다운 상자에서 Lync Server 2013 Edge 서버를 선택 합니다.

5.  **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Lync Server 2013 Edge 서버 페더레이션을 켜려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.

2.  노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 페더레이션은 단일 Edge 풀에 대해서만 사용 하도록 설정할 수 있습니다. Edge 풀이 여러 개 있는 경우 하나를 선택 하 여 페더레이션 가장자리 풀로 사용 합니다.

    
    </div>

3.  **일반** 페이지에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 설정이 선택 되어 있는지 확인 합니다.
    
    ![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")

4.  **확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.

5.  다음으로, 사이트 노드로 이동 합니다.

6.  사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

7.  왼쪽 창에서 **페더레이션 경로**를 클릭 합니다.

8.  **사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync server 2013 Edge 서버를 선택 합니다.
    
    ![속성 편집, 페더레이션 라우팅 페이지](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "속성 편집, 페더레이션 경로 페이지")

9.  **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.
    
    여러 사이트 배포의 경우 각 사이트에서이 절차를 완료 합니다.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Edge 서버 구성 변경 내용을 게시 하려면

1.  **토폴로지 작성기**에서 최상위 노드 **Lync 서버** 를 선택 합니다.

2.  **작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 마법사를 완료 합니다.

3.  Active Directory 복제가 배포의 모든 풀에 발생 하는 것을 기다립니다.
    
    <div>
    

    > [!NOTE]  
    > 다음과 같은 메시지가 표시 될 수 있습니다.<BR><STRONG>경고: 토폴로지에 두 개 이상의 페더레이션된 Edge 서버가 있습니다. 이 문제는 최신 버전의 제품으로 마이그레이션하는 동안 발생할 수 있습니다. 이 경우에는 오직 하나의 Edge 서버만 페더레이션에 사용 됩니다. 외부 DNS SRV 레코드가 올바른 Edge 서버를 가리키는지 확인 합니다. 동시에 여러 페더레이션에 지 서버를 배포 하려는 경우 (즉, 마이그레이션 시나리오가 아닌 경우), 모든 페더레이션 파트너가 Lync Server를 사용 하 고 있는지 확인 합니다. 외부 DNS SRV 레코드에 모든 페더레이션 가능 Edge 서버가 나열 되는지 확인 합니다.</STRONG><BR>이 경고는 예상 되는 것으로 무시 해도 됩니다.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Lync Server 2013 Edge 서버를 구성 하려면

1.  모든 Lync Server 2013 Edge 서버를 온라인 상태로 전환 합니다.

2.  외부에 지 서버 대신 외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정 (일반적으로 포트 443) 및 페더레이션 (일반적으로 포트 5061)에 대 한 SIP 트래픽을 Lync Server 2013 Edge 서버에 전송 하도록 업데이트 합니다.
    
    <div>
    

    > [!NOTE]  
    > 하드웨어 부하 분산이 없는 경우 새 Lync Server 액세스 Edge 서버로 확인 되도록 페더레이션에 대 한 DNS A 레코드를 업데이트 해야 합니다. 최소 중단으로이 작업을 수행 하려면 DNS가 새 Lync Server Access Edge를 가리키도록 업데이트 될 때 페더레이션 및 원격 액세스가 빠르게 업데이트 되도록 외부 Lync Server 액세스 Edge FQDN에 대 한 TLL 값을 줄이십시오.

    
    </div>

3.  다음으로 각 Edge 서버 컴퓨터에서 **Lync Server 액세스 가장자리** 를 중지 합니다.

4.  각 레거시 Edge 서버 컴퓨터에서 **관리 도구**를 통해 **서비스** 애플릿을 엽니다.

5.  서비스 목록에서 **Lync Server 액세스 가장자리**를 찾습니다.

6.  서비스 이름을 마우스 오른쪽 단추로 클릭 하 고 **중지** 를 선택 하 여 서비스를 중지 합니다.

7.  시작 유형을 **사용 안 함으로**설정 합니다.

8.  **확인** 을 클릭 하 여 **속성** 창을 닫습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

