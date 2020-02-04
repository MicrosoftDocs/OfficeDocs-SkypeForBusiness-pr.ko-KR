---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af8228a7537f1bbef4e92af852834459281a817
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728178"
---
# <a name="configure-federation-routes-and-media-traffic"></a>페더레이션 경로 및 미디어 트래픽 구성

 


페더레이션은 서로 다른 조직의 사용자가 네트워크 경계를 통해 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간의 신뢰 관계입니다. Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 Microsoft Office Communications Server 2007 R2 Edge 서버의 페더레이션 경로에서 Lync Server 2013 Edge 서버의 페더레이션 경로로 전환 해야 합니다.

단일 사이트 배포의 경우 다음 절차를 사용 하 여 Office Communications Server 2007 R2 Edge 서버와 디렉터에서 Lync Server 2013 Edge 서버로 페더레이션 경로와 미디어 트래픽 경로를 전환 합니다.


> [!IMPORTANT]  
> 페더레이션 경로와 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Office Communications Server 2007 R2 Edge 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다. 또한이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미 합니다. 최소한의 사용자 작업을 예상 하는 동안 가동 중지 시간을 예약 해야 합니다. 또한 최종 사용자에 게 충분 한 알림을 제공 해야 합니다. 이 중단에 대 한 계획을 수립 하 고 조직 내에서 적절 한 기대치를 설정 하세요.




> [!IMPORTANT]  
> 레거시 Office 통신 서버 2007 R2 Edge 서버가 액세스 경계 서비스, 웹 회의 Edge 서비스 및 A/V Edge 서비스에 대해 동일한 FQDN을 사용 하도록 구성 된 경우이 섹션의 절차는 페더레이션 설정을 Lync Server 2013 Edge 서버로 전환 하는 것이 지원 되지 않습니다. 레거시 Edge 서비스가 동일한 FQDN을 사용 하도록 구성 된 경우 먼저 Office Communications Server 2007 R2에서 Lync Server 2013로 모든 사용자를 마이그레이션한 다음, 페더레이션 사용을 설정 하기 전에 Office Communications Server 2007 R2 Edge 서버의 서비스를 해제 해야 합니다. Lync Server 2013 Edge 서버. 자세한 내용은 다음 항목을 참조 하세요. 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Lync Server 2013으로 나머지 사용자 이동</A></P>
> <LI>
> <P>"서버 및 서버 역할 제거"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> XMPP 페더레이션이 Lync Server 2013 Edge 서버를 통해 라우팅된 경우, 모든 사용자가 Lync Server 2013, XMPP 정책으로 이동 될 때까지 레거시 Office Communications Server 2007 R2 사용자는 XMPP 페더레이션 파트너와 통신할 수 없습니다. 인증서가 구성 되 고 XMPP 페더레이션 파트너가 Lync Server 2013에 구성 되어 있고 마지막으로 DNS 항목이 업데이트 되었습니다.



서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그인 해야 합니다. 또한 서버 역할 추가에 대 한 적절 한 사용자 권한 및 사용 권한을 위임할 수 있습니다. 자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서의 [Lync Server 2013에서 설정 위임을](lync-server-2013-delegate-setup-permissions.md) 참조 하세요. 다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거 하려면

1.  토폴로지 작성기를 사용 하 여 파일럿 풀 토폴로지를 엽니다.

2.  왼쪽 창에서 사이트 노드로 이동 합니다.

3.  사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

4.  왼쪽 창에서 **페더레이션 경로** 를 선택 합니다.

5.  사이트 페더레이션 경로 할당에서 **SIP 페더레이션 사용** 옆에 있는 확인란의 선택을 취소 하 여 **BackCompatSite**를 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.
    
    ![속성 편집 대화 상자, 페더레이션 경로](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로")

6.  **확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.

7.  **토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.

8.  **작업** 메뉴에서 **토폴로지 게시** 를 클릭 하 고 마법사를 완료 합니다.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>레거시 Edge 서버를 비 페더레이션에 지 서버를 구성 하려면

1.  **토폴로지 작성기**의 **동작** 메뉴에서 **Office Communications Server 2007 R2 토폴로지 병합**을 클릭 합니다.

2.  계속하려면 **다음**을 클릭합니다.

3.  **Edge 설정 지정**에서 현재 페더레이션에 대해 구성 된 **EDGE Server 내부 FQDN** 을 선택한 다음 **변경을**클릭 합니다.
    
    ![OCS 2007 R2 토폴로지 병합, 에지 설정 지정](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 토폴로지 병합, 에지 설정 지정")

4.  **다음** 을 클릭 하 고 **외부에 지 지정** 페이지에 도달할 때까지 기본 설정을 적용 합니다.
    
    ![토폴로지 작성기 외부 에지 지정 페이지](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "토폴로지 작성기 외부 에지 지정 페이지")

5.  **외부에 지 지정**에서 **이 Edge 풀은 페더레이션 및 공용 IM 연결에 사용 됨** 확인란의 선택을 취소 합니다. 이렇게 하면 BackCompatSite에 대 한 페더레이션 연결이 제거 됩니다.
    

    > [!IMPORTANT]  
    > 이 단계는 중요 합니다. 레거시 페더레이션 연결을 제거 하려면이 옵션을 선택 취소 해야 합니다.



6.  **다음** 을 클릭 하 고 마법사의 나머지 페이지에 대 한 기본 설정을 적용 합니다.

7.  **요약**에서 **다음** 을 클릭 하 여 토폴로지 병합을 시작 합니다.

8.  **상태** 열에서 값이 **성공**인지 확인 한 다음 **마침을** 클릭 하 여 마법사를 닫습니다.

9.  **작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.

10. **게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.
    
    ![병합된 후의 사이트가 표시된 토폴로지 작성기](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "병합된 후의 사이트가 표시된 토폴로지 작성기")
    
    앞의 그림과 같이 **사이트 페더레이션 경로 할당** 아래에 있는 **SIP 페더레이션** 이 **사용 안 함으로**설정 됩니다.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Lync Server 2013 Edge 서버에서 인증서를 구성 하려면

1.  개인 키를 사용 하 여 외부 액세스 프록시 인증서를 레거시 Office Communications Server 2007 R2 Edge 서버에서 내보냅니다.

2.  Lync Server 2013 Edge 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.

3.  액세스 프록시 외부 인증서를 Edge 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.

4.  Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 변경 되어서는 안 됩니다.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Lync Server 2013 Edge 서버를 사용 하도록 Office Communications Server 2007 R2 페더레이션 경로를 변경 하려면

1.  Office Communications Server 2007 R2 Standard Edition server 또는 프런트 엔드 서버에서 Office Communications Server 2007 R2 관리 도구를 엽니다.

2.  왼쪽 창에서 최상위 노드를 확장 한 다음 **포리스트** 노드를 마우스 오른쪽 단추로 클릭 합니다. **속성**을 선택 하 고 **전역 속성**을 클릭 합니다.

3.  **페더레이션** 탭을 클릭 합니다.

4.  페더레이션 및 공용 IM 연결을 사용 하도록 확인란을 선택 합니다.

5.  Lync Server 2013 Edge 서버의 FQDN을 입력 한 다음 **확인**을 클릭 합니다.
    
    ![OCS 전역 속성, 페더레이션 탭](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 전역 속성, 페더레이션 탭")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Lync Server 2013 Edge 서버 페더레이션을 켜려면

1.  토폴로지 작성기의 왼쪽 창에서 Lync Server 2013 **Edge 풀** 노드로 이동 합니다.

2.  노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    

    > [!NOTE]  
    > 페더레이션은 단일 Edge 풀에 대해서만 사용 하도록 설정할 수 있습니다. Edge 풀이 여러 개 있는 경우 하나를 선택 하 여 페더레이션 가장자리 풀로 사용 합니다.



3.  **일반** 페이지에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.
    
    ![속성 편집, 일반, 에지 페더레이션 사용](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "속성 편집, 일반, 에지 페더레이션 사용")

4.  **확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.

5.  다음으로, 사이트 노드로 이동 합니다.

6.  사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

7.  왼쪽 창에서 **페더레이션 경로**를 클릭 합니다.

8.  **사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync server 2013 Edge 서버를 선택 합니다.

9.  **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.
    
    ![속성 편집, 일반, 에지 풀 연결](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "속성 편집, 일반, 에지 풀 연결")
    
    여러 사이트 배포의 경우 각 사이트에서이 절차를 완료 합니다.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Lync Server 2013 Edge 서버 아웃 바운드 미디어 경로를 구성 하려면

1.  **토폴로지 작성기**에서 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래의 Lync Server 2013 풀로 이동 합니다.

2.  풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

3.  **연결** 섹션에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 확인란을 선택 합니다.

4.  드롭다운 상자에서 Lync Server 2013 Edge 서버를 선택 합니다.
    
    ![속성 편집 대화 상자, 에지 풀 연결](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "속성 편집 대화 상자, 에지 풀 연결")

5.  **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.

## <a name="to-publish-edge-server-configuration-changes"></a>Edge 서버 구성 변경 내용을 게시 하려면

1.  **토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.

2.  **작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 마법사를 완료 합니다.

3.  Active Directory 복제가 배포의 모든 풀에 발생 하는 것을 기다립니다.
    

    > [!NOTE]  
    > 다음과 같은 메시지가 표시 될 수 있습니다.<BR><STRONG>경고: 토폴로지에 두 개 이상의 페더레이션된 Edge 서버가 있습니다. 이 문제는 최신 버전의 제품으로 마이그레이션하는 동안 발생할 수 있습니다. 이 경우에는 오직 하나의 Edge 서버만 페더레이션에 사용 됩니다. 외부 DNS SRV 레코드가 올바른 Edge 서버를 가리키는지 확인 합니다. 동시에 여러 페더레이션에 지 서버를 배포 하려는 경우 (즉 마이그레이션 시나리오가 아닌 경우) 모든 페더레이션 파트너가 Office Communications Server 2007 R2 또는 Lync Server를 사용 하 고 있는지 확인 합니다. 외부 DNS SRV 레코드에 모든 페더레이션 가능 Edge 서버가 나열 되는지 확인 합니다.</STRONG><BR>이 경고는 예상 되는 것으로 무시 해도 됩니다.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>외부 사용자에 대 한 페더레이션 및 원격 액세스를 확인 하려면

1.  Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.

2.  페더레이션 및 원격 액세스의 상태를 확인 하려면 명령줄에서 다음을 입력 합니다.
    
        Get-CsAccessEdgeConfiguration

3.  페더레이션 및 원격 액세스를 사용 하도록 설정 하려면 명령줄에서 다음 명령을 입력 합니다.
    
        Set-CsAccessEdgeConfiguration
    
    이러한 cmdlet에 대 한 자세한 내용은 다음 항목을 참조 하세요. [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) 및 [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).

4.  복제가 완료 될 때까지 기다렸다가 Lync Server 2013 Edge 서버를 온라인 상태로 전환 하 고 페더레이션 및 외부 액세스를 테스트 합니다.

## <a name="to-configure-lync-server-2013-edge-server"></a>Lync Server 2013 Edge 서버를 구성 하려면

1.  모든 Lync Server 2013 Edge 서버를 온라인 상태로 전환 합니다.

2.  외부에 지 서버 대신 외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정 (일반적으로 포트 443) 및 페더레이션 (일반적으로 포트 5061)에 대 한 SIP 트래픽을 Lync Server 2013 Edge 서버에 전송 하도록 업데이트 합니다.
    

    > [!NOTE]  
    > 하드웨어 부하 분산이 없는 경우 새 Lync Server 액세스 Edge 서버를 확인 하려면 페더레이션에 대 한 DNS A 레코드를 업데이트 해야 합니다. 최소 중단으로이 작업을 수행 하려면 DNS가 새 Lync Server 액세스 Edge 서버를 가리키도록 업데이트 될 때 페더레이션 및 원격 액세스가 빠르게 업데이트 되도록 외부 Lync Server 액세스에 지 FQDN에 대 한 TTL 값을 줄이십시오.



3.  다음으로 각 Edge 서버 컴퓨터에서 **Lync Server 액세스 가장자리** 를 중지 합니다.

4.  각 레거시 Edge 서버 컴퓨터에서 **관리 도구**를 통해 **서비스** 애플릿을 엽니다.

5.  서비스 목록에서 **Office Communications Server 액세스 Edge**를 찾습니다.

6.  서비스 이름을 마우스 오른쪽 단추로 클릭 하 고 **중지** 를 선택 하 여 서비스를 중지 합니다.

7.  시작 유형을 **사용 안 함으로**설정 합니다.

8.  **확인** 을 클릭 하 여 **속성** 창을 닫습니다.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>외부 사용자 및 외부 액세스의 연결을 테스트 하려면

  - 하나 이상의 페더레이션 도메인, Lync Server 2013의 내부 사용자 및 Office Communications Server 2007 R2 사용자의 사용자 인스턴트 메시지 (IM), 현재 상태, 오디오/비디오 (A/V) 및 데스크톱 공유를 테스트 합니다.

  - 조직에서 지 원하는 각 공용 IM 서비스 공급자의 사용자 (그리고 프로 비전이 완료 된 경우)는 Lync Server 2013 및 Office Communications Server 2007 R2 사용자와 통신 합니다.

  - 익명 사용자가 회의에 참가할 수 있는지 확인 합니다.

  - 원격 사용자 액세스를 사용 하 여 Office communications Server 2007 R2에 호스팅되는 사용자 (인트라넷 외부에서는 Office Communications Server 2007 R2에 로그인 하 고 VPN 제외)는 Lync Server 2013의 사용자와 Office Communications Server 2007 R2에 대 한 사용자입니다. IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.

  - Lync server 2013에서 원격 사용자 액세스를 사용 하 여 (인트라넷 외부에서 Lync Server 2013에 로그인 하 고 VPN이 없는 경우 2013) 사용자에 대 한 자세한 2007 정보 IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.

