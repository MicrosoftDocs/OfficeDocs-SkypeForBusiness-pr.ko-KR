---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f5b3e0a775af649b7210dd75dcf90d012f2e421
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>페더레이션 경로 및 미디어 트래픽 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-15_

페더레이션은 개별 조직의 사용자가 네트워크 경계에서 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간 신뢰 관계입니다. Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 lync server 2010에 지 서버의 페더레이션 경로에서 Lync Server 2013에 지 서버의 페더레이션 경로로 전환 해야 합니다.

단일 사이트 배포의 경우 다음 절차에 따라 Lync Server 2010에 지 서버 및 디렉터에서 Lync server 2013 Edge 서버로의 페더레이션 경로 및 미디어 트래픽 경로를 전환 합니다.

<div>


> [!IMPORTANT]  
> 페더레이션 경로 및 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Lync Server 2010에 지 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다. 이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미하기도 합니다. 사용자 활동이 최소로 예상되는 시간으로 중단 시간을 예약합니다. 또한 최종 사용자에게 충분한 알림을 제공해야 합니다. 이 중단에 맞게 계획하고 조직 내에서 적당한 기대치를 설정합니다.



</div>

<div>


> [!IMPORTANT]  
> 레거시 Lync Server 2010에 지 서버가 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V에 지 서비스에 대해 동일한 FQDN을 사용 하도록 구성 되어 있는 경우이 섹션의 절차는 지원 되지 않습니다. 레거시에 지 서비스가 동일한 FQDN을 사용 하도록 구성 되어 있는 경우 lync server 2013에 지 서버에서 페더레이션을 사용 하도록 설정 하기 전에 먼저 Lync server 2010에서 lync server 2013로 모든 사용자를 마이그레이션한 다음 Lync Server 2010에 지 서버를 해제 해야 합니다.



</div>

<div>


> [!IMPORTANT]  
> XMPP 페더레이션이 Lync Server 2013에 지 서버를 통해 라우팅되는 경우, 모든 사용자가 Lync Server 2013로 이동 될 때까지 레거시 Lync Server 2010 사용자는 XMPP 페더레이션 파트너와 통신할 수 없으며 XMPP 정책 및 인증서가 사용 됩니다. 구성 된 경우에는 Lync Server 2013에 XMPP 페더레이션 파트너가 구성 되어 있고 마지막으로 DNS 항목이 업데이트 되었습니다.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거하려면

1.  Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기의 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **Lync Server** 아래에 있는 사이트 노드로 이동합니다.

3.  사이트를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.

4.  왼쪽 창에서 **페더레이션 경로**를 선택합니다.

5.  **사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용** 확인란의 선택을 취소 하 여 레거시 Lync Server 2010 환경을 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.
    
    ![속성 편집 대화 상자, 페더레이션 경로 페이지](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로 페이지")

6.  **확인**을 클릭하여 속성 편집 페이지를 닫습니다.

7.  **토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.

8.  **동작** 메뉴에서 **토폴로지 게시**를 클릭합니다.

9.  **다음**을 클릭하여 게시 프로세스를 완료하고 게시 프로세스가 완료되었으면 **마침**을 클릭합니다.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>레거시 에지 서버를 비페더레이션 에지 서버로 구성하려면

1.  왼쪽 창에서 **Lync Server 2010** 노드로 이동하고 **에지 풀** 노드로 이동합니다.

2.  에지 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.

3.  왼쪽 창에서 **일반**을 선택합니다.

4.  **이 에지 풀에 페더레이션 사용(포트 5061)** 확인란 항목의 선택을 취소하고 **확인**을 선택하여 페이지를 닫습니다.
    
    ![속성 편집, 일반, 페더레이션 사용 지우기](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "속성 편집, 일반, 페더레이션 사용 지우기")

5.  **동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.

6.  **게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.

7.  레거시 에지 서버에 대한 페더레이션이 사용하지 않도록 설정되었는지 확인합니다.
    
    ![토폴로지 작성기,에 지 풀, 페더레이션 사용 안 함](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "토폴로지 작성기,에 지 풀, 페더레이션 사용 안 함")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Lync Server 2010 에지 서버에서 인증서를 구성하려면

1.  레거시 Lync Server 2010에 지 서버에서 개인 키를 사용 하 여 외부 액세스 프록시 인증서를 내보냅니다.

2.  Lync Server 2013에 지 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.

3.  액세스 프록시 외부 인증서를에 지 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.

4.  Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 신뢰할 수 있는 CA에서 요청 하 고 할당 해야 합니다.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Lync Server 2013 에지 서버를 사용하도록 Lync Server 2010 페더레이션 경로를 변경하려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동하고 **에지 풀** 노드로 이동합니다.

2.  에지 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.

3.  왼쪽 창에서 **일반**을 선택합니다.

4.  **이 에지 풀에 페더레이션 사용(포트 5061)** 에 대한 확인란 항목을 선택한 후 **확인**을 클릭하여 페이지를 닫습니다.
    
    ![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")

5.  **동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.

6.  **게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.

7.  **페더레이션(포트 5061)** 이 **사용**으로 설정되었는지 확인합니다.
    
    ![토폴로지 작성기,에 지 풀, 페더레이션 사용](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "토폴로지 작성기,에 지 풀, 페더레이션 사용")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Lync Server 2013 에지 서버 페더레이션 다음 홉을 업데이트하려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동하고 **에지 풀** 노드로 이동합니다.

2.  노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.

3.  **일반** 페이지의 **다음 홉 선택**에 있는 드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.
    
    ![속성 편집 대화 상자의 다음 홉 페이지](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "속성 편집 대화 상자의 다음 홉 페이지")

4.  **확인**을 클릭하여 속성 편집 페이지를 닫습니다.

5.  **토폴로지 작성기**에서 최상위 노드 **Lync Server** 를 선택 합니다.

6.  **동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 마법사를 완료합니다.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Lync Server 2013 에지 서버 아웃바운드 미디어 경로를 구성하려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래의 풀로 이동 합니다.

2.  풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.

3.  **연결** 섹션에서 **에지 풀 연결(미디어 구성 요소)** 확인란을 선택합니다.
    
    ![속성 편집, 일반,에 지 풀 연결](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "속성 편집, 일반,에 지 풀 연결")

4.  드롭다운 상자에서 Lync Server 2013에 지 서버를 선택 합니다.

5.  **확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Lync Server 2013 에지 서버 페더레이션을 설정하려면

1.  토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동하고 **에지 풀** 노드로 이동합니다.

2.  노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 페더레이션은 단일에 지 풀에 대해서만 사용 하도록 설정할 수 있습니다. 에지 풀이 여러 개인 경우 페더레이션 에지 풀로 사용할 항목을 하나 선택합니다.

    
    </div>

3.  **일반** 페이지에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 설정이 선택되었는지 확인합니다.
    
    ![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")

4.  **확인**을 클릭하여 속성 편집 페이지를 닫습니다.

5.  그런 다음 사이트 노드로 이동합니다.

6.  사이트에서 마우스 오른쪽 단추를 클릭한 다음 **속성 편집**을 클릭합니다.

7.  왼쪽 창에서 **페더레이션 경로**를 클릭합니다.

8.  **사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync Server 2013에 지 서버를 선택 합니다.
    
    ![속성 편집, 페더레이션 경로 페이지](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "속성 편집, 페더레이션 경로 페이지")

9.  **확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.
    
    다중 사이트 배포의 경우 각 사이트에서 이 절차를 완료합니다.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>에지 서버 구성 변경 사항을 게시하려면

1.  **토폴로지 작성기**에서 최상위 노드 **Lync Server** 를 선택 합니다.

2.  **동작** 메뉴에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.

3.  배포의 모든 풀에 대해 Active Directory 복제가 발생할 때까지 기다립니다.
    
    <div>
    

    > [!NOTE]  
    > 다음 메시지가 표시될 수 있습니다.<BR><STRONG>경고: 토폴로지에 둘 이상의 페더레이션 에지 서버가 포함되어 있습니다. 상위 버전의 제품으로 마이그레이션하는 동안 이 상황이 발생할 수 있습니다. 이 경우 하나의 에지 서버만 페더레이션에 사용됩니다. 외부 DNS SRV 레코드가 올바른 에지 서버를 가리키는지 확인하십시오. 동시에 활성화되도록 여러 페더레이션 에지 서버를 배포하려면(즉, 마이그레이션 시나리오가 아님) 모든 페더레이션 파트너가 Lync Server를 사용하고 있는지 확인하고 외부 DNS SRV 레코드에 모든 페더레이션 사용 가능 에지 서버가 나열되는지 확인하십시오.</STRONG><BR>이 경고는 예상된 경고이므로 무시해도 됩니다.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Lync Server 2013 에지 서버를 구성하려면

1.  모든 Lync Server 2013에 지 서버를 온라인 상태로 전환 합니다.

2.  외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정을 업데이트 하 여 외부 액세스에 대 한 SIP 트래픽 (일반적으로 포트 443)과 페더레이션 (일반적으로 포트 5061)을 레거시에 지 서버 대신 Lync Server 2013에 지 서버에 전송 합니다.
    
    <div>
    

    > [!NOTE]  
    > 하드웨어 부하 분산 장치가 없으면 새 Lync Server 액세스 에지 서버로 확인되도록 페더레이션에 대한 DNS A 레코드를 업데이트해야 합니다. 최소한의 중단으로 이를 수행하려면 새 Lync Server 액세스 에지를 가리키도록 DNS를 업데이트할 때 페더레이션 및 원격 액세스를 빠르게 업데이트할 수 있도록 외부 Lync Server 액세스 에지 FQDN에 대한 TLL 값을 줄입니다.

    
    </div>

3.  다음으로 각에 지 서버 컴퓨터에서 **Lync Server 액세스에 지** 를 중지 합니다.

4.  각 레거시에 지 서버 컴퓨터의 **관리 도구**에서 **서비스** 애플릿을 엽니다.

5.  서비스 목록에서 **Lync Server 액세스 에지**를 찾습니다.

6.  서비스 이름을 마우스 오른쪽 단추로 클릭한 후 **중지**를 선택하여 서비스를 중지합니다.

7.  시작 유형을 **사용 안 함**으로 설정합니다.

8.  **확인**을 클릭하여 **속성** 창을 닫습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

