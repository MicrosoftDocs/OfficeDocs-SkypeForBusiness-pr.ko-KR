---
title: 'Lync Server 2013: 토폴로지에서 선택적 디렉터 토폴로지 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Lync Server 2013에 대한 토폴로지에서 선택적 디렉터 토폴로지 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

Lync Server 2013 디렉터는 단일 인스턴스 서버 이거나 가용성과 용량을 높이기 위해 여러 디렉터에 부하 분산 풀로 설치할 수 있습니다. 하드웨어 로드 균형 조정과 DNS (Domain Name System) 부하 분산이 모두 지원 됩니다. 이 항목에서는 디렉터 풀에 대 한 DNS 부하 분산을 구성 하는 방법에 대해 설명 합니다.

서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 **RTCUniversalServerAdmins** 및 **Domain Admins** 그룹의 구성원 인 사용자로 로그온 해야 합니다. 또한 서버 역할을 추가 하는 데 필요한 관리자 권한 및 사용 권한을 위임할 수도 있습니다. 자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서의 [Lync Server 2013에서 설정 위임을](lync-server-2013-delegate-setup-permissions.md) 참조 하세요. 다른 구성 변경의 경우 **RTCUniversalServerAdmins** 그룹의 구성원만 필요 합니다.

이 항목에서는 두 개의 디렉터 토폴로지에 대 한 토폴로지를 정의 하 고 게시 하는 단계에 대해 설명 합니다.

  - 디렉터를 정의 하려면 (단일 인스턴스)

  - 디렉터 (여러 디렉터 풀)를 정의 하려면

<div>

## <a name="to-define-the-director-single-instance"></a>디렉터를 정의 하려면 (단일 인스턴스)

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  시작 페이지에서 **기존 배포의 토폴로지 다운로드**를 클릭 합니다.

3.  다른 이름 **으로 토폴로지 저장** 대화 상자에서 기존 토폴로지의 로컬 복사본의 이름과 위치를 입력 한 다음 **저장**을 클릭 합니다.

4.  디렉터를 추가할 사이트를 확장 하 고 **감독 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 디렉터 풀**을 클릭 합니다.

5.  **디렉터 풀 FQDN 정의** 대화 상자에서 다음을 수행 합니다.
    
      - **풀 fqdn**에 디렉터 풀의 FQDN을 입력 합니다.
    
      - **단일 컴퓨터 풀**을 클릭 하 고 **다음**을 클릭 합니다.

6.  **파일 공유 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
    
    1.  기존 파일 공유를 사용 하려면 **이전에 정의한 파일 공유 사용**을 클릭 하 고 목록에서 파일 공유를 선택한 후 **다음**을 클릭 합니다.
    
    2.  새 파일 공유를 만들려면 **새 파일 공유 정의**를 클릭 하 고 **파일 서버 FQDN**의 파일 공유 위치에 대 한 FQDN을 입력 한 후 **파일 공유**에 공유의 이름을 입력 하 고 **다음**을 클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이 단계에서 지정 하거나 만든 파일 공유가 토폴로지를 게시 하기 전에 존재 하거나 만들어야 합니다.<BR>디렉터에 할당 된 파일 공유는 실제로 사용 되지 않으므로 조직의 모든 풀에 대 한 파일 공유를 할당할 수 있습니다.

    
    </div>

7.  **웹 서비스 URL 지정** 대화 상자의 **외부 기본 url**에서 디렉터에 대 한 FQDN을 지정 하 고 **마침을**클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이름은 인터넷 DNS 서버에서 확인할 수 있어야 하 고 해당 URL에 대 한 HTTP/HTTPS 요청을 수신 하는 역방향 프록시의 공용 IP 주소를 가리켜 해당 디렉터의 외부 웹 서비스 가상 디렉터리로이를 프록시 합니다.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 프런트 엔드 풀 또는 프런트 엔드 서버를 두 개 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다. 디렉터를 배포 하는 경우 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프론트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 모든 디렉터 또는 디렉터 풀에서 고유 해야 합니다. 내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

8.  토폴로지를 게시 합니다.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>디렉터 (여러 디렉터 풀)를 정의 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  시작 페이지에서 **기존 배포의 토폴로지 다운로드**를 클릭 합니다.

3.  다른 이름 **으로 토폴로지 저장** 대화 상자에서 기존 토폴로지의 로컬 복사본의 이름과 위치를 입력 한 다음 **저장**을 클릭 합니다.

4.  디렉터를 추가할 사이트를 확장 하 고 **감독 풀**을 마우스 오른쪽 단추로 클릭 한 다음 **새 디렉터 풀**을 클릭 합니다.

5.  **디렉터 풀 FQDN 정의** 대화 상자에서 다음을 수행 합니다.
    
      - **풀 fqdn**에 디렉터 풀의 FQDN을 입력 합니다.
    
      - **여러 컴퓨터 풀**을 클릭 하 고 **다음**을 클릭 합니다.

6.  **이 풀의 컴퓨터 정의** 대화 상자에서 다음을 수행 합니다.
    
      - 첫 번째 풀 구성원의 컴퓨터 FQDN을 지정한 다음 **추가**를 클릭 합니다.
    
      - 추가 하려는 각 컴퓨터에 대해 이전 단계를 반복 합니다. 마쳤으면 **다음**을 클릭 합니다.

7.  **파일 공유 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
    
      - 기존 파일 공유를 사용 하려면 **이전에 정의한 파일 공유 사용**을 클릭 하 고 목록에서 파일 공유를 선택한 후 **다음**을 클릭 합니다.
    
      - 새 파일 공유를 만들려면 **새 파일 공유 정의**를 클릭 하 고 **파일 서버 FQDN**의 파일 공유 위치에 대 한 FQDN을 입력 한 후 **파일 공유**에 공유의 이름을 입력 하 고 **다음**을 클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이 단계에서 지정 하거나 만든 파일 공유가 토폴로지를 게시 하기 전에 존재 하거나 만들어야 합니다.<BR>디렉터에 할당 된 파일 공유는 실제로 사용 되지 않으므로 조직의 모든 풀에 대 한 파일 공유를 할당할 수 있습니다.

    
    </div>

8.  **웹 서비스 URL 지정** 대화 상자의 **외부 기본 url**에서 디렉터에 대 한 FQDN을 지정 하 고 **마침을**클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이름은 인터넷 DNS 서버에서 확인할 수 있어야 하 고 해당 URL로 전송 된 HTTP/HTTPS 요청을 수신 하는 역방향 프록시의 공용 IP 주소를 가리켜 해당 디렉터 풀의 외부 웹 서비스 가상 디렉터리로이를 프록시 합니다.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 프런트 엔드 풀 또는 프런트 엔드 서버를 두 개 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다. 디렉터를 배포 하는 경우 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프론트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 모든 디렉터 또는 디렉터 풀에서 고유 해야 합니다. 내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

9.  토폴로지를 게시 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

