---
title: 프런트 엔드 풀 또는 Standard Edition server 정의 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52b7e4fcbcce1c297036e7b1e2862e680c4d86cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-08_

이 절차는 로컬 관리자 구성원 자격 또는 권한이 있는 도메인 그룹 구성원 자격이 없어도 수행할 수 있습니다. 즉, 컴퓨터에 표준 사용자로 로그온하면 됩니다.

엔터프라이즈 서버를 배포 하는 경우 풀에 있는 최소 개수의 프런트 엔드 서버가 항상 실행 되 고 있어야 합니다. 다음 표에서는 이러한 요구 사항을 요약해서 보여줍니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>풀에 있는 총 프런트 엔드 서버 수</th>
<th>풀 작동을 위해 실행되어야 하는 서버 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>개</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3(sp3)</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>1-4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>2-5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Lync Server 2013의 경우 풀에서 프런트 엔드 서버를 추가 또는 제거할 때마다 서비스를 다시 시작 해야 합니다. 서버를 제거하고 추가하는 작업은 개별 작업으로 수행되어야 합니다. 예를 들어 프런트 엔드 서버 두 대를 추가 하 고 두 프런트 엔드 서버를 제거 하려면 다음 프로세스를 사용 합니다. 
> <OL>
> <LI>
> <P>2개의 프런트 엔드 서버를 제거합니다.</P>
> <LI>
> <P>토폴로지를 게시하고 다시 활성화합니다.</P>
> <LI>
> <P>서비스를 다시 시작합니다.</P>
> <LI>
> <P>2개의 프런트 엔드 서버를 추가합니다.</P>
> <LI>
> <P>토폴로지를 게시하고 다시 활성화합니다.</P>
> <LI>
> <P>서비스를 다시 시작합니다.</P></LI></OL>



</div>

토폴로지를 정의한 후에는 다음 절차를 사용 하 여 사이트의 프런트 엔드 풀을 정의 합니다. 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성을](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)참조 하십시오.

<div>

## <a name="to-define-a-front-end-pool"></a>프런트 엔드 풀을 정의 하려면

1.  새 프런트 엔드 풀 정의 마법사의 **새 프런트 엔드 풀 정의** 페이지에서 **다음**을 클릭합니다.

2.  **프런트 엔드 풀 FQDN 정의** 페이지에서 만들려는 풀의 fqdn (정규화 된 도메인 이름)을 입력 하 고 **Enterprise Edition 프런트 엔드 풀**을 클릭 한 후 **다음**을 클릭 합니다.

3.  **이 풀의 컴퓨터 정의** 페이지에서 풀의 첫 번째 프런트 엔드 서버에 대 한 컴퓨터 FQDN을 입력 한 다음 **추가**를 클릭 합니다. 풀에 추가할 추가 컴퓨터 (최대 12 개)에 대해이 단계를 반복 하 고 **다음**을 클릭 합니다.

4.  **기능 선택** 페이지에서 이 프런트 엔드 풀에 필요한 기능의 확인란을 선택합니다. 예를 들어 IM (인스턴트 메시징) 및 현재 상태 기능만 배포 하는 경우에는 음성, 비디오 및 공동 작업 회의 기능을 나타내기 때문에 단체 IM을 허용 하 고 **전화 접속 (PSTN) 회의**, **Enterprise Voice**또는 **통화 허용 제어** 확인란이 선택 되지 않도록 **회의** 확인란을 선택 합니다.
    
      - **회의**   이 항목을 선택 하면 다음을 비롯 한 다양 한 기능을 사용할 수 있습니다.
        
          - IM 세션에서 둘 이상의 사용자를 포함하는 IM
        
          - 문서 공동 작업, 응용 프로그램 공유 및 데스크톱 공유를 포함하는 회의
        
          - A/V 회의-사용자가 Live Meeting 서비스나 타사 오디오 브리지 등의 외부 서비스 없이도 실시간 전화 회의를 할 수 있도록 합니다.
    
      - **전화 접속 (pstn) 회의**   를 통해 사용자는 오디오 회의 공급자 없이도 공중 전화망 (pstn) 전화를 사용 하 여 Lync Server 2013 회의의 오디오 부분에 참가할 수 있습니다.
    
      - **Enterprise voice**   enterprise voice는 Lync Server 2013의 VoIP (Voice over IP) 솔루션으로, 사용자가 전화를 걸고 받을 수 있습니다. 음성 통화, 음성 메일 및 하드웨어 장치 또는 소프트웨어 클라이언트를 사용 하는 기타 기능에 Lync Server 2013을 사용 하려면이 기능을 배포 합니다.
    
      - **Cac (통화 허용 제어)**   cac는 사용 가능한 네트워크 대역폭을 기반으로 음성 또는 비디오 통화와 같은 실시간 통신 세션을 설정할지 여부를 결정 합니다. IM과 현재 상태만 배포한 경우에는 두 기능 모두 CAC를 사용하지 않으므로 CAC가 필요하지 않습니다.
    
      - **보관**   보관은 Lync Server 2013를 통해 전송 되는 IM 콘텐츠, 회의 (모임) 콘텐츠 또는 둘 다를 보관할 수 있는 방법을 제공 합니다.
    
      - **모니터링 모니터링 서버**   를 사용 하면 네트워크 및 끝점의 미디어 품질, VoIP 통화, IM 메시지, A/V 대화, 모임, 응용 프로그램 공유, 파일 전송, 실패 한 통화에 대 한 통화 오류 및 문제 해결 정보를 설명 하는 수치 데이터를 수집할 수 있습니다.
    
    <div>
    

    > [!NOTE]
    > 배포에서 CAC를 사용하도록 설정하려면 중앙 사이트당 정확히 하나의 풀에서 CAC를 사용하도록 설정해야 합니다. 음성 기능이나 A/V 회의를 배포하는 경우 CAC를 사용하는 것이 좋습니다.

    
    </div>
    
    다음 표에는 사용 가능한 기능(위쪽)과 사용자에게 제공되는 기능(왼쪽)이 나와 있습니다. 표에서 선택되어 있는 항목은 조직에 대해 해당 기능을 사용하도록 설정하기 위해 선택해야 하는 기능입니다.
    
    
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
    <th>전화</th>
    <th>전화 접속 회의</th>
    <th>Enterprise Voice</th>
    <th>통화 허용 제어</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>인스턴트 메시징 및 현재 상태</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>전화</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>A/V 회의</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Enterprise Voice</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  **배치 된 서버 역할 선택** 페이지에서 프런트 엔드 서버에 대 한 중재 서버를 함께 배치할 독립 실행형 서버로 배포 하는 데 사용할 수 있습니다.
    
    함께 배치할는 프런트 엔드 풀에서 중재 서버를 사용할 수 있습니다.
    
      - Enterprise Edition 프런트 엔드 풀에서 중재 서버를 함께 배치할 확인란이 선택 되어 있는지 확인 합니다. 서버 역할은 풀 서버에 배포됩니다.
    
      - 중재 서버를 독립 실행형 서버로 배포 하려는 경우 해당 확인란의 선택을 취소 합니다. 프런트 엔드 서버를 완전히 배포한 후에 중재 서버를 별도의 배포 단계에 배포 합니다.
    
    <div>
    

    > [!NOTE]
    > 가능한 경우 중재 서버를 배치하는 것이 좋습니다. 배치 된 또는 독립 실행형 중재 서버에 대 한 지원에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013에서 중재 서버의 구성 요소 및 토폴로지</A> 를 참조 하십시오.

    
    </div>

6.  서버 **역할을이 프런트 엔드 풀과 연결** 페이지를 사용 하 여 서버 역할을 정의 하 고 프런트 엔드 풀과 연결할 수 있습니다. 사용할 수 있는 역할은 다음과 같습니다.
    
    **에 지 풀**   사용 단일에 지 서버 또는에 지 서버 풀을 정의 하 고 연결 합니다. 에 지 서버는 페더레이션 사용자를 포함 하 여 조직 외부의 사용자와 조직과의 공동 작업을 용이 하 게 합니다.
    
    서버 역할을 배포하고 연결하는 데 사용할 수 있는 두 가지 가능한 시나리오가 있습니다.
    
    첫 번째 시나리오는 새로운 설치에 대한 새 토폴로지를 정의하는 경우입니다. 다음 두 가지 중 한 가지 방법으로 설치에 접근할 수 있습니다.
    
      - 확인란을 비워 두고 토폴로지 정의를 진행합니다. 프런트 엔드 및 백 엔드 서버 역할을 게시, 구성 및 테스트 한 후에는 토폴로지 작성기를 다시 실행 하 여 역할 서버를 토폴로지에 추가할 수 있습니다. 이 전략을 사용 하면 추가 역할을 추가 하지 않고도 프런트 엔드 풀 및 SQL Server를 실행 하는 서버를 테스트할 수 있습니다. 초기 테스트를 완료 한 후에는 토폴로지 작성기를 다시 실행 하 여 배포 해야 하는 역할을 선택할 수 있습니다.
    
      - 설치해야 하는 역할을 선택하고 이 역할에 맞게 하드웨어를 설정합니다.
    
    시나리오 2의 경우 기존 배포가 있고 인프라가 새 역할에 대해 준비 되어 있거나 기존 역할을 새 프런트 엔드 서버에 연결 해야 합니다.
    
      - 이 경우 배포 하거나 새 프런트 엔드 서버에 연결 하려는 역할을 선택 합니다. 어느 경우든 계속해 역할을 정의하고 필요한 하드웨어를 설정한 후 설치를 계속합니다.

7.  **SQL 저장소 정의** 페이지에서 다음 중 하나를 수행합니다.
    
      - 토폴로지에 이미 정의된 기존 SQL Server 저장소를 사용하려면 **SQL 저장소**에서 인스턴스를 선택합니다.
    
      - 풀 정보를 저장할 새 SQL Server 인스턴스를 정의 하려면 **새로 만들기** 를 클릭 하 고 **새 sql 저장소 정의** 대화 상자에서 **SQL Server FQDN**을 지정 합니다.
    
      - SQL Server 인스턴스 이름을 지정하려면 **명명된 인스턴스**를 선택하고 인스턴스 이름을 지정합니다.
    
      - 기본 인스턴스를 사용하려면 **기본 인스턴스**를 클릭합니다.
    
      - SQL 미러링을 사용하려면 **SQL 미러링 사용**을 선택하고 기존 인스턴스를 선택하거나 새 인스턴스를 만듭니다.

8.  **파일 공유 정의** 페이지에서 다음 중 하나를 수행합니다.
    
      - 토폴로지에 이미 정의된 파일 공유를 사용하려면 **이전에 정의된 파일 공유 사용**을 선택합니다.
    
      - 새 파일 공유를 정의하려면 **새 파일 공유 정의**를 선택하고 **파일 서버 FQDN** 상자에 파일 공유가 있는 기존 파일 서버의 FQDN을 입력한 다음 **파일 공유** 상자에 파일 공유 이름을 입력합니다.
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013에 대 한 파일 공유는 프런트 엔드 서버에 배치할 수 없습니다. 이 예에서는 SQL Server 기반 백 엔드 서버에 파일 공유가 있습니다. 이는 조직의 요구에 맞는 최적의 위치가 아닐 수 있으며, 파일 서버가 더 나은 선택일 수 있습니다. 만들어진 파일 공유가 없는 상태에서 파일 공유를 정의할 수 있습니다. 그러려면 토폴로지를 게시하기 전에 정의한 위치에 파일 공유를 만들어야 합니다.

    
    </div>

9.  **웹 서비스 URL 지정** 페이지에서 다음 중 하나 이상을 수행합니다.
    
    <div>
    

    > [!IMPORTANT]
    > 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 인 https://pool01.contoso.net경우 기본 URL은 pool01.contoso.net입니다.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > 프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.

    
    </div>
    
    1.  DNS 부하 분산을 구성 하는 경우 내부 **웹 서비스 풀 Fqdn 다시 정의** 확인란을 선택 하 고, 내부 기본 url (예: 내부-\<기본 Url\>)을 **내부 기본 url**에 입력 합니다.
        
        <div>
        

        > [!WARNING]
        > 내부 웹 서비스를 자체 정의 된 FQDN으로 재정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다. Url 또는 정규화 된 도메인 이름을 정의할 때는 표준 문자 (-Z, a-z, 0 – 9 및 하이픈 포함) <STRONG>만 사용</STRONG> 합니다. 유니코드 문자나 밑줄은 사용하지 마십시오. URL 또는 FQDN의 비표준 문자는 외부 DNS 및 공용 CAs에서 지원 되지 않는 경우가 많습니다 (즉, URL 또는 FQDN을 인증서의 주체 이름 또는 주체 대체 이름에 할당 해야 하는 경우).

        
        </div>
    
    2.  필요한 경우 외부 **기본 url에**외부 기본 url을 입력 합니다. 외부 기본 URL을 입력 하 여 내부 도메인 명명과 구분 합니다. 내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우를 예로 들 수 있습니다. Contoso.com 도메인 이름을 사용 하 여 URL을 정의 합니다. 이는 역방향 프록시의 경우에도 중요 합니다. 외부 기본 URL 도메인 이름은 역방향 프록시의 FQDN에 대 한 도메인 이름과 동일 합니다. 인스턴트 메시징 및 현재 상태에는 프런트 엔드 풀에 대 한 HTTP 액세스가 필요 합니다.
    
    <div>
    

    > [!NOTE]
    > DNS 부하 분산을 사용하려면 적절한 DNS 레코드를 만들어야 합니다. 자세한 내용은 <A href="lync-server-2013-configure-dns-for-load-balancing.md">Lync Server 2013에서 부하 분산을 위한 DNS 구성을</A>참조 하십시오.

    
    </div>

10. **기능 선택** 페이지에서 **회의** 를 선택한 경우 **office web Apps 서버 선택** 페이지에서 **office web apps server에 풀 연결** 을 선택 하 고 **새로 만들기** (또는 드롭다운 목록에서 기존 Office Web Apps 서버 선택)를 클릭 합니다.

11. **새 Office Web Apps Server 정의** 대화 상자에서 **Office Web Apps Server FQDN** 상자에 Office Web Apps Server 컴퓨터의 FQDN(정규화된 도메인 이름)을 입력합니다. 이렇게 하면 Office Web Apps Server 검색 URL이 **Office Web Apps Server 검색 URL** 상자에 자동으로 입력됩니다.
    
    Office Web Apps 서버를 Lync Server 2013와 동일한 네트워크 영역에 설치 하는 경우에는 **Office Web Apps 서버를 외부 네트워크 (경계/인터넷)에 배포** 하는 옵션을 선택 하면 안 됩니다.
    
    Office Web Apps Server가 내부 방화벽 외부에 배포된 경우 **Office Web Apps Server가 외부 네트워크에 배포되어 있습니다(경계/인터넷).** 옵션을 선택합니다.
    
    <div>
    

    > [!NOTE]
    > 자세한 내용은 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps 서버 및 Lync server 2013의 통합 구성을</A>참조 하세요.

    
    </div>

12. **보관 SQL 저장소 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택하거나 보관 데이터와 연결된 데이터를 저장할 새 인스턴스를 정의합니다.

13. **모니터링 SQL 저장소 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택하거나 모니터링 데이터와 연결된 데이터를 저장할 새 인스턴스를 정의합니다.

14. **다음**을 클릭합니다. **서버 역할을이 프런트 엔드 풀과 연결** 페이지에서 다른 역할 서버를 정의한 경우에는 서버 역할을 구성할 수 있도록 별도의 역할 구성 마법사 페이지가 열립니다. 자세한 내용은 다음을 참조하십시오.
    
    [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)

15. 구성하고 배포할 추가 서버 역할을 선택하지 않았거나 추가 역할 서버 구성을 마친 경우 **마침**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

