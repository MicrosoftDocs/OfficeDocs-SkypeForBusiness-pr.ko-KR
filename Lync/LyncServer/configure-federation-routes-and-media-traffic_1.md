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
ms.openlocfilehash: a9f4818e74bbc0f59900ebf7d8f0a2b79fcd003f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006664"
---
# <a name="configure-federation-routes-and-media-traffic"></a>페더레이션 경로 및 미디어 트래픽 구성

 


페더레이션은 개별 조직의 사용자가 네트워크 경계에서 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간 신뢰 관계입니다. Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 Microsoft Office Communications Server 2007 R2에 지 서버의 페더레이션 경로에서 Lync Server 2013에 지 서버의 페더레이션 경로로 전환 해야 합니다.

단일 사이트 배포의 경우 다음 절차를 사용 하 여 Office Communications Server 2007 R2에 지 서버 및 디렉터에서 Lync Server 2013 Edge 서버로의 페더레이션 경로 및 미디어 트래픽 경로를 전환 합니다.


> [!IMPORTANT]  
> 페더레이션 경로 및 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Office Communications Server 2007 R2에 지 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다. 이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미하기도 합니다. 사용자 활동이 최소로 예상되는 시간으로 중단 시간을 예약합니다. 또한 최종 사용자에게 충분한 알림을 제공해야 합니다. 이 중단에 맞게 계획하고 조직 내에서 적당한 기대치를 설정합니다.




> [!IMPORTANT]  
> 레거시 Office Communications Server 2007 R2에 지 서버가 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V에 지 서비스에 대해 동일한 FQDN을 사용 하도록 구성 되어 있는 경우이 섹션의 절차를 통해 페더레이션 설정을 Lync Server 2013에 지 서버로 전환할 수 없습니다. 레거시에 지 서비스가 동일한 FQDN을 사용 하도록 구성 된 경우에는 먼저 Office Communications Server 2007 R2에서 Lync Server 2013로 모든 사용자를 마이그레이션한 다음, 페더레이션을 사용 하도록 설정 하기 전에 Office Communications Server 2007 R2에 지 서버를 해제 해야 합니다. Lync Server 2013에 지 서버 자세한 내용은 다음 항목을 참조하십시오. 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Lync Server 2013로 나머지 사용자 이동</A></P>
> <LI>
> <P>"서버 및 서버 역할 제거"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> XMPP 페더레이션이 Lync Server 2013에 지 서버를 통해 라우팅되는 경우에는 모든 사용자가 Lync Server 2013, XMPP 정책으로 이동 될 때까지 레거시 Office Communications Server 2007 R2 사용자가 XMPP 페더레이션 파트너와 통신할 수 없습니다. 인증서가 구성 되어 있고, XMPP 페더레이션 파트너가 Lync Server 2013에 구성 되어 있고, 마지막으로 DNS 항목이 업데이트 되었습니다.



서버 역할을 추가하거나 제거할 때 토폴로지를 게시하거나, 사용 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원인 사용자로 로그인해야 합니다. 또한 서버 역할에 적당한 사용자 권리 및 사용 권한을 위임할 수도 있습니다. 자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서에서 [Lync Server 2013의 대리인 설치 권한](lync-server-2013-delegate-setup-permissions.md) 를 참조 하십시오. 그 밖의 구성 변경은 RTCUniversalServerAdmins 그룹의 구성원이면 됩니다.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거하려면

1.  토폴로지 작성기를 사용하여 파일럿 풀 토폴로지를 엽니다.

2.  왼쪽 창에서 사이트 노드로 이동합니다.

3.  사이트를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.

4.  왼쪽 창에서 **페더레이션 경로**를 선택합니다.

5.  사이트 페더레이션 경로 지정에서 **SIP 페더레이션 사용(Enable SIP federation)** 옆에 있는 확인란의 선택을 취소하여 **BackCompatSite**를 통해 페더레이션 경로를 사용하지 않도록 설정합니다.
    
    ![속성 편집 대화 상자, 페더레이션 경로](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로")

6.  **확인**을 클릭하여 속성 편집 페이지를 닫습니다.

7.  **토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.

8.  **동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 마법사를 완료합니다.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>레거시 에지 서버를 비페더레이션 에지 서버로 구성하려면

1.  **토폴로지 작성기**의 **동작** 메뉴에서 **Office Communications Server 2007 R2 토폴로지 병합(Merge Office Communications Server 2007 R2 Topology)** 를 클릭합니다.

2.  **다음**을 클릭하여 계속합니다.

3.  **에지 설정 지정**에서 현재 페더레이션에 대해 구성된 **에지 서버 내부 FQDN**을 선택한 후 **변경**을 클릭합니다.
    
    ![OCS 2007 R2 토폴로지 병합,에 지 설정 지정](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 토폴로지 병합,에 지 설정 지정")

4.  **다음**을 클릭하고 **외부 에지 지정** 페이지에 연결될 때까지 기본 설정을 수락합니다.
    
    ![토폴로지 작성기 외부에 지 지정 페이지](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "토폴로지 작성기 외부에 지 지정 페이지")

5.  **외부 에지 지정**에서 **이 에지 풀은 페더레이션 및 공용 IM 연결에 사용됩니다.** 확인란의 선택을 취소합니다. 그러면 BackCompatSite와의 페더레이션 연결이 제거됩니다.
    

    > [!IMPORTANT]  
    > 이 단계는 중요한 단계입니다. 레거시 페더레이션 연결을 제거하려면 이 옵션의 선택을 취소해야 합니다.



6.  **다음**을 클릭하고 마법사의 남은 페이지에서 기본 설정을 그대로 사용합니다.

7.  **요약**에서 **다음**을 클릭하여 토폴로지 병합을 시작합니다.

8.  **상태** 열에서 값이 **성공**인지 확인 한 다음 **마침을** 클릭 하 여 마법사를 닫습니다.

9.  **동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.

10. **게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.
    
    ![병합 후 사이트가 표시 되는 토폴로지 작성기](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "병합 후 사이트가 표시 되는 토폴로지 작성기")
    
    이전 그림에서처럼 **사이트 페더레이션 경로 지정** 아래에 있는 **SIP 페더레이션**이 **사용 안 함**으로 설정되어 있습니다.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Lync Server 2013 에지 서버에서 인증서를 구성하려면

1.  레거시 Office Communications Server 2007 R2에 지 서버에서 개인 키를 사용 하 여 외부 액세스 프록시 인증서를 내보냅니다.

2.  Lync Server 2013에 지 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.

3.  액세스 프록시 외부 인증서를에 지 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.

4.  Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 변경 하면 안 됩니다.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Lync Server 2010 에지 서버를 사용하도록 Office Communications Server 2013 R2 페더레이션 경로를 변경하려면

1.  Office Communications Server 2007 R2 Standard Edition server 또는 프런트 엔드 서버에서 Office Communications Server 2007 R2 관리 도구를 엽니다.

2.  왼쪽 창에서 맨 위의 노드를 확장한 후 **포리스트** 노드를 마우스 오른쪽 단추로 클릭합니다. **속성**을 선택한 후 **전역 속성**을 클릭합니다.

3.  **페더레이션** 탭을 클릭합니다.

4.  확인란을 선택하여 페더레이션 및 공용 IM 연결을 사용하도록 설정합니다.

5.  Lync Server 2013 Edge 서버의 FQDN을 입력 하 고 **확인**을 클릭 합니다.
    
    ![OCS 전역 속성, 페더레이션 탭](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 전역 속성, 페더레이션 탭")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Lync Server 2013 에지 서버 페더레이션을 설정하려면

1.  토폴로지 작성기의 왼쪽 창에서 Lync Server 2013 **Edge 풀** 노드로 이동 합니다.

2.  노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.
    

    > [!NOTE]  
    > 페더레이션은 단일에 지 풀에 대해서만 사용 하도록 설정할 수 있습니다. 에지 풀이 여러 개인 경우 페더레이션 에지 풀로 사용할 항목을 하나 선택합니다.



3.  **일반** 페이지에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 확인란을 선택합니다.
    
    ![속성 편집, 일반,에 지 페더레이션 사용](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "속성 편집, 일반,에 지 페더레이션 사용")

4.  **확인**을 클릭하여 속성 편집 페이지를 닫습니다.

5.  그런 다음 사이트 노드로 이동합니다.

6.  사이트에서 마우스 오른쪽 단추를 클릭한 다음 **속성 편집**을 클릭합니다.

7.  왼쪽 창에서 **페더레이션 경로**를 클릭합니다.

8.  **사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync Server 2013에 지 서버를 선택 합니다.

9.  **확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.
    
    ![속성 편집, 일반,에 지 풀 연결](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "속성 편집, 일반,에 지 풀 연결")
    
    다중 사이트 배포의 경우 각 사이트에서 이 절차를 완료합니다.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Lync Server 2013 에지 서버 아웃바운드 미디어 경로를 구성하려면

1.  **토폴로지 작성기**에서 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래의 Lync Server 2013 풀로 이동 합니다.

2.  풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.

3.  **연결** 섹션에서 **에지 풀 연결(미디어 구성 요소)** 확인란을 선택합니다.

4.  드롭다운 상자에서 Lync Server 2013에 지 서버를 선택 합니다.
    
    ![속성 편집 대화 상자,에 지 풀 연결](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "속성 편집 대화 상자,에 지 풀 연결")

5.  **확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.

## <a name="to-publish-edge-server-configuration-changes"></a>에지 서버 구성 변경 사항을 게시하려면

1.  **토폴로지 작성기**에서 맨 위에 있는 최상위 노드 **Lync Server**를 선택합니다.

2.  **동작** 메뉴에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.

3.  배포의 모든 풀에 대해 Active Directory 복제가 발생할 때까지 기다립니다.
    

    > [!NOTE]  
    > 다음 메시지가 표시될 수 있습니다.<BR><STRONG>경고: 토폴로지에 둘 이상의 페더레이션 에지 서버가 포함되어 있습니다. 상위 버전의 제품으로 마이그레이션하는 동안 이 상황이 발생할 수 있습니다. 이 경우 하나의 에지 서버만 페더레이션에 사용됩니다. 외부 DNS SRV 레코드가 올바른 에지 서버를 가리키는지 확인하십시오. 동시에 활성화되도록 여러 페더레이션 에지 서버를 배포하려면(즉, 마이그레이션 시나리오가 아님) 모든 페더레이션 파트너가 Office Communications Server 2007 R2 또는 Lync Server를 사용하고 있는지 확인하고 외부 DNS SRV 레코드에 모든 페더레이션 사용 가능 에지 서버가 나열되는지 확인하십시오.</STRONG><BR>이 경고는 예상된 경고이므로 무시해도 됩니다.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>외부 사용자를 위한 페더레이션 및 원격 액세스를 확인하려면

1.  Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.

2.  페더레이션 및 원격 액세스 상태를 확인하려면 명령줄에서 다음을 입력합니다.
    
        Get-CsAccessEdgeConfiguration

3.  페더레이션 및 원격 액세스를 사용하려면 명령줄에서 다음을 입력합니다.
    
        Set-CsAccessEdgeConfiguration
    
    이러한 cmdlet에 대 한 자세한 내용은 [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) 및 [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))항목을 참조 하십시오.

4.  Lync Server 2013에 지 서버를 온라인으로 전환 하 고 페더레이션 및 외부 액세스를 테스트 하기 전에 복제가 완료 될 때까지 기다립니다.

## <a name="to-configure-lync-server-2013-edge-server"></a>Lync Server 2013 에지 서버를 구성하려면

1.  모든 Lync Server 2013에 지 서버를 온라인 상태로 전환 합니다.

2.  외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정을 업데이트 하 여 외부 액세스에 대 한 SIP 트래픽 (일반적으로 포트 443)과 페더레이션 (일반적으로 포트 5061)을 레거시에 지 서버 대신 Lync Server 2013에 지 서버에 전송 합니다.
    

    > [!NOTE]  
    > 하드웨어 부하 분산 기능이 없는 경우 페더레이션에 대한 DNS A를 업데이트하여 새 Lync Server 액세스 에지 서버를 확인해야 합니다. 최소한의 중단만으로 이 작업을 수행하려면 DNS가 업데이트되어 새 Lync Server 액세스 에지 서버를 가리킬 때 페더레이션 및 원격 액세스가 신속히 업데이트되도록 외부 Lync Server 액세스 에지 FQDN에 대한 TTL 값을 낮춥니다.



3.  다음으로 각에 지 서버 컴퓨터에서 **Lync Server 액세스에 지** 를 중지 합니다.

4.  각 레거시에 지 서버 컴퓨터의 **관리 도구**에서 **서비스** 애플릿을 엽니다.

5.  서비스 목록에서 **Office Communications Server 액세스 에지**를 찾습니다.

6.  서비스 이름을 마우스 오른쪽 단추로 클릭한 후 **중지**를 선택하여 서비스를 중지합니다.

7.  시작 유형을 **사용 안 함**으로 설정합니다.

8.  **확인**을 클릭하여 **속성** 창을 닫습니다.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>외부 사용자 및 외부 액세스 연결을 테스트하려면

  - 하나 이상의 페더레이션 도메인에서 사용자, Lync Server 2013의 내부 사용자 및 Office Communications Server 2007 r 2에 대 한 사용자입니다. IM(인스턴트 메시징), 현재 상태, A/V(오디오/비디오) 및 데스크톱 공유를 테스트합니다.

  - 조직이 지원 하 고 프로 비전이 완료 된 각 공용 IM 서비스 공급자의 사용자가 Lync Server 2013 및 Office Communications Server 2007 r 2의 사용자와 통신 합니다.

  - 익명 사용자가 회의에 참가할 수 있는지 확인합니다.

  - Lync Server 2013에 있는 사용자와 Office communications Server 2007 r 2에 대 한 사용자의 원격 사용자 액세스를 사용 하 여 Office communications server 2007 R2에 호스트 되는 사용자 2007 (VPN 제외) IM, 현재 상태, A/V 및 데스크톱 공유를 테스트합니다.

  - Lync server 2013을 사용 하 여 lync server 2013에 2013 호스트 되는 사용자에 게 원격 사용자 액세스 (VPN 제외)로 로그온 하 고, Office Communications Server 2007 r 2에 대 한 사용자와 연결 합니다. IM, 현재 상태, A/V 및 데스크톱 공유를 테스트합니다.

