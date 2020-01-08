---
title: 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac840cb40da71f81a24501f3d9caa53fb316e86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-08_

이 절차에서는 로컬 관리자 또는 특권 도메인 그룹의 멤버 자격을 요구 하지 않습니다. 표준 사용자로 컴퓨터에 로그온 해야 합니다.

엔터프라이즈 서버를 배포 하는 경우 풀에 있는 프런트 엔드 서버의 최소 수는 항상 실행 중 이어야 합니다. 다음 표에는 이러한 요구 사항이 요약 되어 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>풀의 총 프런트 엔드 서버 수</th>
<th>풀을 작동 하기 위해 실행 해야 하는 서버 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4(tcp/ipv4)</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5mb</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>26</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Lync Server 2013의 경우 풀에서 프런트 엔드 서버를 추가 하거나 제거할 때마다 서비스를 다시 시작 해야 합니다. 서버 제거 및 추가는 별도의 작업으로 수행 해야 합니다. 예를 들어 프런트 엔드 서버 두 개를 추가 하 고 프런트 엔드 서버 두 개를 제거 하려면 다음 프로세스를 사용 합니다. 
> <OL>
> <LI>
> <P>두 프런트 엔드 서버를 제거 합니다.</P>
> <LI>
> <P>토폴로지를 게시 하 고 다시 활성화 합니다.</P>
> <LI>
> <P>서비스 다시 시작</P>
> <LI>
> <P>두 프런트 엔드 서버를 추가 합니다.</P>
> <LI>
> <P>토폴로지를 게시 하 고 다시 활성화 합니다.</P>
> <LI>
> <P>서비스를 다시 시작 합니다.</P></LI></OL>



</div>

토폴로지를 정의한 후에는 다음 절차를 사용 하 여 사이트의 프런트 엔드 풀을 정의 합니다. 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성을](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)참조 하세요.

<div>

## <a name="to-define-a-front-end-pool"></a>프런트 엔드 풀을 정의 하려면

1.  새 프런트 엔드 풀 정의 마법사의 **새 프런트 엔드 풀 정의** 페이지에서 **다음**을 클릭 합니다.

2.  **프런트 엔드 풀 Fqdn 정의** 페이지에서 만들려는 풀의 fqdn (정규화 된 도메인 이름)을 입력 하 고 **Enterprise Edition 프런트 엔드 풀**을 클릭 한 후 **다음**을 클릭 합니다.

3.  **이 풀의 컴퓨터 정의** 페이지에서 풀의 첫 번째 프런트 엔드 서버에 대 한 컴퓨터 FQDN을 입력 한 다음 **추가**를 클릭 합니다. 풀에 추가 하려는 추가 컴퓨터 (최대 12 개)에 대해이 단계를 반복한 후 **다음**을 클릭 합니다.

4.  **기능 선택** 페이지에서이 프런트 엔드 풀에 대해 원하는 기능에 해당 하는 확인란을 선택 합니다. 예를 들어 인스턴트 메시지 (IM) 및 현재 상태 기능만 배포 하는 경우에는 **회의** 확인란을 선택 하 여 단체 메신저를 허용 하 되 **전화 접속 (PSTN) 회의**, **엔터프라이즈 음성**또는 **통화 허용 제어** 확인란은 음성, 비디오, 공동 작업 회의 기능을 나타내므로 선택 하지 않습니다.
    
      - **회의**   : 다음을 비롯 한 다양 한 기능을 선택할 수 있습니다.
        
          - IM 세션에 두 명 이상의 파티가 있는 IM
        
          - 회의에는 문서 공동 작업, 응용 프로그램 공유, 데스크톱 공유가 포함 됩니다.
        
          - Live Meeting 서비스 또는 타사 오디오 브리지와 같은 외부 서비스에 대 한 필요 없이 사용자가 실시간으로 오디오/비디오 (A/V) 회의를 할 수 있는 A/V 회의.
    
      - **전화 접속 (pstn) 회의**   를 통해 사용자는 오디오 회의 공급자 없이도 pstn (공개 전환 통신 네트워크) 전화를 사용 하 여 Lync Server 2013 컨퍼런스의 오디오 부분에 참가할 수 있습니다.
    
      - **Enterprise voice**   enterprise voice는 사용자가 전화를 걸고 받을 수 있는 Lync Server 2013의 VoIP (Voice over IP) 솔루션입니다. 음성 통화, 음성 메일 및 하드웨어 장치 또는 소프트웨어 클라이언트를 사용 하는 기타 기능을 위해 Lync Server 2013을 사용할 계획인 경우이 기능을 배포 합니다.
    
      - **Cac (통화 허용 제어)**   cac는 사용 가능한 네트워크 대역폭을 기준으로 음성 또는 영상 통화와 같은 실시간 통신 세션을 설정할 수 있는지 여부를 결정 합니다. IM 및 현재 상태만 배포 하는 경우에는 이러한 두 기능 모두 CAC를 사용 하지 않으므로 CAC가 필요 하지 않습니다.
    
      - **보관**   보관을 통해 Lync Server 2013를 통해 전송 되는 IM 콘텐츠, 회의 (모임) 콘텐츠 또는 둘 다를 보관할 수 있는 방법을 제공 합니다.
    
      - ****   모니터링 서버 모니터링을 사용 하면 네트워크 및 끝점의 미디어 품질, VoIP 통화와 관련 된 사용 정보, IM 메시지, A/V 대화, 모임, 응용 프로그램 공유, 파일 전송, 실패 한 통화에 대 한 통화 오류 및 문제 해결 정보를 설명 하는 숫자 데이터를 수집할 수 있습니다.
    
    <div>
    

    > [!NOTE]
    > 배포에서 CAC를 사용 하도록 설정 하려면 중앙 사이트 당 정확히 하나의 풀에서 CAC를 사용 하도록 설정 해야 합니다. 음성 기능 또는 A/V 회의를 배포 하는 경우에는 CAC가 권장 됩니다.

    
    </div>
    
    다음 표에서는 사용 가능한 기능 (위쪽)과 사용자에 게 제공 되는 기능 (왼쪽)을 보여 줍니다. 테이블의 선택 사항에 따라 조직에서 해당 기능을 사용 하도록 설정 해야 합니다.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>회의</th>
    <th>전화 접속 회의</th>
    <th>Enterprise Voice</th>
    <th>통화 허용 제어</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>인스턴트 메시징 및 현재 상태</p></td>
    <td><p>축</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>회의</p></td>
    <td><p>축</p></td>
    <td><p>축</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>A/V 회의</p></td>
    <td><p>축</p></td>
    <td><p>축</p></td>
    <td></td>
    <td><p>축</p></td>
    </tr>
    <tr class="even">
    <td><p>Enterprise Voice</p></td>
    <td></td>
    <td></td>
    <td><p>축</p></td>
    <td><p>축</p></td>
    </tr>
    </tbody>
    </table>


5.  **Collocated 서버 역할 선택** 페이지에서 프런트 엔드 서버에 대 한 중재 서버를 collocate 독립 실행형 서버로 배포 하도록 할 수 있습니다.
    
    프런트 엔드 풀에서 중재 서버를 collocate 수 있습니다.
    
      - 엔터프라이즈 버전 프런트 엔드 풀에서 중재 서버를 collocate 하려면 확인란이 선택 되어 있는지 확인 합니다. 서버 역할이 풀 서버에 배포 됩니다.
    
      - 중재 서버를 독립 실행형 서버로 배포 하려는 경우 해당 확인란의 선택을 취소 합니다. 프런트 엔드 서버를 완전히 배포한 후에는 중재 서버를 별도의 배포 단계에서 배포 합니다.
    
    <div>
    

    > [!NOTE]
    > 가능한 경우 중재 서버를 collocate 하는 것이 좋습니다. Collocated 또는 독립 실행형 중재 서버에 대 한 지원에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013에서 중재 서버용 구성 요소 및 토폴로지</A> 를 참조 하세요.

    
    </div>

6.  **이 프런트 엔드 풀을 사용 하 여 서버 역할 연결** 페이지를 통해 서버 역할을 정의 하 고 프런트 엔드 풀에 연결할 수 있습니다. 다음 역할을 사용할 수 있습니다.
    
    **Edge 풀**   사용 단일 edge 서버 또는 edge 서버 풀을 정의 하 고 연결 합니다. Edge 서버는 페더레이션 사용자와 조직 외부의 사용자 간 통신 및 공동 작업을 용이 하 게 합니다.
    
    서버 역할을 배포 하 고 연결 하는 데 사용할 수 있는 두 가지 시나리오가 있습니다.
    
    시나리오 1의 경우 새 설치에 대 한 새 토폴로지를 정의 하 게 됩니다. 다음 두 가지 방법 중 하나를 사용 하 여 설치할 수 있습니다.
    
      - 확인란을 선택 하지 않은 상태로 두고 토폴로지 정의를 계속 진행 합니다. 프런트 엔드 및 백 엔드 서버 역할을 게시 하 고 구성 하 고 테스트 한 후에는 토폴로지 작성기를 다시 실행 하 여 토폴로지에 역할 서버를 추가할 수 있습니다. 이 전략을 사용 하면 추가 역할에서 추가적인 문제가 발생 하지 않고 프런트 엔드 풀 및 SQL Server를 실행 하는 서버를 테스트할 수 있습니다. 초기 테스트를 완료 한 후 토폴로지 작성기를 다시 실행 하 여 배포 해야 하는 역할을 선택할 수 있습니다.
    
      - 설치 해야 하는 역할을 선택한 다음 선택한 역할을 수용할 수 있도록 하드웨어를 설정 합니다.
    
    시나리오 2의 경우 기존 배포가 있고 인프라에서 새 역할을 사용할 준비가 되었거나 기존 역할을 새 프런트 엔드 서버와 연결 해야 합니다.
    
      - 이 경우에는 새 프런트 엔드 서버에 배포 하거나 연결할 역할을 선택 합니다. 두 경우 모두 역할 정의를 진행 하 고, 필요한 하드웨어를 설정 하 고, 설치를 진행 하 게 됩니다.

7.  **SQL 스토어 정의** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 토폴로지에 이미 정의 된 기존 SQL Server 저장소를 사용 하려면 **SQL store**에서 인스턴스를 선택 합니다.
    
      - 새 SQL Server 인스턴스를 정의 하 여 풀 정보를 저장 하려면 **새로 만들기** 를 클릭 한 다음 **새 sql store 정의** 대화 상자에서 **SQL server FQDN**을 지정 합니다.
    
      - SQL Server 인스턴스의 이름을 지정 하려면 **명명 된 인스턴스**를 선택한 다음 인스턴스의 이름을 지정 합니다.
    
      - 기본 인스턴스를 사용 하려면 **기본 인스턴스**를 클릭 합니다.
    
      - SQL 미러링을 사용 하려면 **sql 미러링 사용** 을 선택 하 고 기존 인스턴스를 선택 하거나 새 인스턴스를 만듭니다.

8.  **파일 공유 정의** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 토폴로지에 이미 정의 된 파일 공유를 사용 하려면 **이전에 정의 된 파일 공유 사용**을 선택 합니다.
    
      - 새 파일 공유를 정의 하려면 **새 파일 공유 정의**를 선택 하 고 **파일 서버 FQDN** 상자에 파일 공유가 위치할 기존 파일 서버의 FQDN을 입력 한 다음 **파일 공유** 상자에 파일 공유의 이름을 입력 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013의 파일 공유는 프런트 엔드 서버에 있을 수 없습니다. 이 예제에서는 파일 공유가 SQL Server 기반 백 엔드 서버에 위치 합니다. 이는 조직의 요구 사항에 적합 한 위치가 아닐 수 있으며 파일 서버를 선택 하는 것이 더 좋을 수 있습니다. 파일 공유를 만들지 않고 파일 공유를 정의할 수 있습니다. 토폴로지를 게시 하기 전에 사용자가 정의한 위치에 파일 공유를 만들어야 합니다.

    
    </div>

9.  **웹 서비스 URL 지정** 페이지에서 다음 중 하나 또는 모두를 수행 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > 기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > 프런트 엔드 풀 또는 프런트 엔드 서버를 둘 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.

    
    </div>
    
    1.  DNS 부하 분산을 구성 하는 경우 내부 **웹 서비스 풀 Fqdn 무시** 확인란을 선택 하 고 내부 기본 url (예:\<사용자의 기본 url\>과 내부 기본 url)을 입력 합니다. ****
        
        <div>
        

        > [!WARNING]
        > 내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다. Url 또는 정규화 된 도메인 이름을 정의할 때는 표준 문자 (-Z, a-z, 0 – 9 및 하이픈 포함) <STRONG>만 사용</STRONG> 합니다. 유니코드 문자나 밑줄은 사용 하지 마세요. URL 또는 fqdn의 비표준 문자는 외부 DNS 및 공개 Ca (즉 URL 또는 FQDN을 인증서의 주체 이름 또는 주체 대체 이름에 할당 해야 하는 경우)에서 지원 되지 않는 경우가 많습니다.

        
        </div>
    
    2.  필요에 **따라 외부 기본**url에 외부 기본 url을 입력 합니다. 외부 기본 URL을 입력 하 여 내부 도메인 명명을 구분 합니다. 예를 들어 내부 도메인은 contoso.net 외부 도메인 이름은 contoso.com입니다. Contoso.com 도메인 이름을 사용 하 여 URL을 정의 합니다. 이는 리버스 프록시의 경우에도 중요 합니다. 외부 기본 URL 도메인 이름은 역방향 프록시의 FQDN에 대 한 도메인 이름과 동일 합니다. 인스턴트 메시지 및 현재 상태에는 프런트 엔드 풀에 대 한 HTTP 액세스가 필요 합니다.
    
    <div>
    

    > [!NOTE]
    > DNS 부하 분산을 사용 하려면 적절 한 DNS 레코드를 만들어야 합니다. 자세한 내용은 <A href="lync-server-2013-configure-dns-for-load-balancing.md">Lync Server 2013에서 부하 분산을 위한 DNS 구성을</A>참조 하세요.

    
    </div>

10. **기능 선택** 페이지에서 **회의** 를 선택한 경우 Office web apps **서버 선택** 페이지에서 그룹을 **office web apps 서버와 연결** 을 선택 하 고 **새로 만들기** (또는 드롭다운 목록에서 기존 Office Web Apps 서버 선택)를 클릭 합니다.

11. **새 Office Web Apps 서버 정의** 대화 상자에서 office web APPS 서버 **Fqdn** 상자에 office ONLINE server 컴퓨터의 fqdn (정규화 된 도메인 이름)을 입력 합니다. 이렇게 하면 office Web Apps 서버 검색 URL이 **Office Web Apps server 검색 url** 상자에 자동으로 입력 됩니다.
    
    Office Web Apps 서버가 Lync Server 2013와 같은 네트워크 영역에 설치 되어 있는 경우 **외부 네트워크 (즉, 경계/인터넷)에 Office Web Apps 서버를 배포** 하는 옵션을 선택 하지 않아야 합니다.
    
    Office Web Apps 서버가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버를 외부 네트워크 (즉, 외곽/인터넷)에 배포**하는 옵션을 선택 합니다.
    
    <div>
    

    > [!NOTE]
    > 자세한 내용은 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps 서버 및 Lync server 2013의 통합 구성을</A>참조 하세요.

    
    </div>

12. **보관 SQL 저장소 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택 하거나, 데이터 보관에 연결 된 데이터를 저장할 새 인스턴스를 정의 합니다.

13. **모니터링 SQL Store 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택 하거나 모니터링 데이터와 관련 된 데이터를 저장할 새 인스턴스를 정의 합니다.

14. **다음**을 클릭 합니다. **이 프런트 엔드 풀을 사용 하 여 서버 역할 연결** 페이지에서 다른 역할 서버를 정의한 경우 서버 역할을 구성할 수 있도록 별도의 역할 구성 마법사 페이지가 열립니다. 자세한 내용은 다음을 참조 하세요.
    
    [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)

15. 구성 및 배포할 추가 서버 역할을 선택 하지 않은 경우 또는 추가 역할 서버의 구성을 완료 한 경우 **마침을**클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

