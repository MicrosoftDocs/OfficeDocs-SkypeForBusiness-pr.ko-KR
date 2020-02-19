---
title: 'Lync Server 2013: 자동 검색을 위한 역방향 프록시 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c50704508c09d1f30a9fb8e31060e2a3b69885d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013에서 자동 검색을 위한 역방향 프록시 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-12_

자동 검색 및 새 검색을 사용 하는 클라이언트의 지원에는 기존 웹 게시 규칙을 수정 하거나 역방향 프록시에 대 한 새로운 웹 게시 규칙을 만드는 작업이 필요 합니다. 새 게시 규칙을 수정 하거나 만드는 것은 역방향 프록시 인증서의 주체 대체 이름 목록을 업데이트 하거나 업데이트 하지 않는 결정에 따라 달라 집니다.

초기 Lync Server 2013 자동 검색 서비스 요청에 HTTPS를 사용 하 고 역방향 프록시 인증서에서 주체 대체 이름 목록을 업데이트 하는 경우 업데이트 된 공용 인증서를 SSL (Secure Sockets layer) 수신기에 할당 해야 합니다. 역방향 프록시 외부 (공용) 인증서에 대 한 필수 업데이트에는 lyncdiscover에 대 한 SAN (주체 대체 이름) 항목이 포함 됩니다. \<도메인 이름\>입니다. 그런 다음 외부 자동 검색 서비스 URL (예: **lyncdiscover.contoso.com**)에 대 한 기존 수신기를 수정 하거나 새 웹 게시 규칙을 만들어야 합니다. 프런트 엔드 풀 및 디렉터 풀에 대 한 외부 Lync Server 2013 웹 서비스 URL에 대 한 웹 게시 규칙이 아직 없는 경우 (디렉터를 배포한 경우)에도 규칙을 게시 해야 합니다.

<div>


> [!NOTE]  
> 리스너에 지정된 인증서에 두 서비스 모두에 필요한 주체 이름 및 주체 대체 이름이 포함된 경우 역방향 프록시 게시 규칙 및 리스너가 외부 웹 서비스와 자동 검색 서비스 모두를 지원할 수 있습니다. 웹 수신기 및 게시 규칙의 기본 구성에 대 한 자세한 내용은 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers For Lync Server 2013</A> 을 참조 하십시오.



</div>

역방향 프록시용 주체 대체 이름을 업데이트하지 않아도 되도록 초기 자동 검색 서비스 요청에 대해 HTTP를 사용하려는 경우에는 포트 80에 대해 웹 게시 규칙을 만들거나 수정해야 합니다.

이 섹션의 절차에서는 자동 검색을 위해 Microsoft Forefront Threat Management Gateway 2010에서 웹 게시 규칙을 만들거나 수정하는 방법을 설명합니다.

<div>


> [!NOTE]  
> 이러한 절차에서는 Forefront Threat Management Gateway(TMG) 2010의 Standard Edition이 설치되어 있다고 가정합니다. 또 다른 역방향 프록시를 사용 중인 경우 절차가 비슷하지만 타사 제품에 대한 설명서에 맞게 매핑할 필요가 있습니다.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>외부 자동 검색 URL에 대해 새 웹 게시 규칙을 만들려면

1.  **시작**을 클릭하고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG 관리**를 클릭합니다.

2.  왼쪽 창에서 **ServerName**을 확장하고 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭합니다.

3.  **새 웹 게시 규칙 시작** 페이지에서 새 게시 규칙의 표시 이름(예: LyncDiscoveryURL)을 입력합니다.

4.  **규칙 동작 선택** 페이지에서 **허용**을 선택합니다.

5.  **게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택합니다.

6.  **서버 연결 보안** 페이지에서 **SSL을 사용하여 게시된 웹 서버 또는 서버 팜에 연결**을 선택합니다.

7.  **내부 게시 정보** 페이지의 **내부 사이트 이름**에 디렉터 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다 (예: lyncdir01). 프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 FQDN (예:: lyncpool01.contoso.local)을 입력 합니다.

8.  **내부 게시 정보** 페이지의 **경로 (옵션)** 에 게시할 폴더의 경로 ** / ** 를 입력 한 다음 **원래 호스트 헤더 전달을**선택 합니다.

9.  **공개 이름 정보** 페이지에서 다음을 수행합니다.
    
      - **다음에 대한 요청 허용**에서 **이 도메인 이름**을 선택합니다.
    
      - **공개 이름**에 **lyncdiscover를 입력 합니다.** \<microsoft.rtc.management.xds.sipdomain object\> (외부 자동 검색 서비스 URL) 프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대 한 FQDN (예: lyncwebextpool01.contoso.com)을 입력 합니다.
    
      - **경로**에를 입력 ** / **합니다.

10. **웹 수신기 선택** 페이지의 **웹 수신기**에서 업데이트된 공용 인증서를 포함하는 기존 SSL 수신기를 선택합니다.

11. **인증 위임** 페이지에서 **위임 안 함 - 클라이언트에서 직접 인증**을 선택합니다.

12. **사용자 집합** 페이지에서 **모든 사용자**를 선택합니다.

13. **새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인하고 **마침**을 클릭합니다.

14. Forefront TMG의 웹 게시 규칙 목록에서 방금 추가한 새 규칙을 두 번 클릭하여 **속성**을 엽니다.

15. **대상** 탭에서 다음을 수행합니다.
    
      - **실제 호스트 헤더 대신 원래 호스트 헤더 전달**을 선택합니다.
    
      - **Forefront TMG 컴퓨터에서 보낸 요청(Requests appear to come from the Forefront TMG computer)** 을 선택합니다.

16. **브리징** 탭에서 다음을 구성합니다.
    
      - **웹 서버**를 선택합니다.
    
      - **HTTP 포트로 요청 리디렉션**을 선택하고 포트 번호로 **8080**을 입력합니다.
    
      - **SSL 포트로 요청 리디렉션**을 선택하고 포트 번호로 **4443**을 입력합니다.

17. **확인**을 클릭합니다.

18. 세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.

19. **규칙 테스트**를 클릭하여 새 규칙이 올바르게 설정되었는지 확인합니다.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>외부 자동 검색 SAN 및 URL을 추가하기 위해 기존 웹 게시 규칙을 수정하려면

1.  **시작**을 클릭하고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG 관리**를 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 갖고 있는 각 게시 규칙 및 리스너에 대해 수정 작업을 반복합니다. 일반적으로이 작업은 프런트 엔드 풀에 대 한 하나의 규칙과 수신기와 선택적 디렉터 또는 디렉터 풀에 대해 하나씩 배포 됩니다.

    
    </div>

2.  왼쪽 창에서 **ServerName**을 확장하고 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 해당 규칙을 클릭합니다. **작업** 탭에서 **선택한 규칙 편집**을 클릭합니다.

3.  **공개 이름** 탭의 **이 규칙 적용**에서 **다음 웹 사이트에 대한 요청**을 선택합니다.

4.  **추가**를 클릭하고 새로운 자동 검색 사이트의 이름(예: 뱇yncdiscover.contoso.com?을 입력한 후 **확인**을 클릭합니다.

5.  **리스너** 탭에서 **인증서 선택**을 클릭하고 추가된 자동 검색 SAN 항목을 포함하는 새 인증서를 지정합니다. 리스너 및 웹 게시 속성을 닫습니다.

6.  세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.

7.  **규칙 테스트**를 클릭하여 새 규칙이 올바르게 설정되었는지 확인합니다.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>포트 80에 대해 웹 게시 규칙을 만들려면

1.  **시작**을 클릭하고 **프로그램**, **Microsoft Forefront TMG**를 차례로 가리킨 다음 **Forefront TMG 관리**를 클릭합니다.

2.  왼쪽 창에서 **ServerName**을 확장하여 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭합니다.

3.  **새 웹 게시 규칙 시작** 페이지에서 게시 규칙의 표시 이름(예: Lync 자동 검색(HTTP))을 입력합니다.

4.  **규칙 동작 선택** 페이지에서 **허용**을 선택합니다.

5.  **게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택합니다.

6.  **서버 연결 보안** 페이지에서 **보안되지 않은 연결을 사용하여 게시된 웹 서버 또는 서버 팜에 연결**을 선택합니다.

7.  **내부 게시 정보** 페이지의 **내부 사이트 이름**에 프런트 엔드 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncpool01.contoso.local)을 입력 합니다.

8.  **내부 게시 정보** 페이지의 **경로 (옵션)** 에 게시할 폴더의 경로 ** / ** 를 입력 하 고 **내부 사이트 이름 필드에 지정 된 호스트 헤더 대신 원래 host 머리글 전달을**선택 합니다.

9.  **공개 이름 정보** 페이지에서 다음을 수행합니다.
    
      - **다음에 대한 요청 허용**에서 **이 도메인 이름**을 선택합니다.
    
      - **공개 이름**에 **lyncdiscover를 입력 합니다.** \<microsoft.rtc.management.xds.sipdomain object\> (외부 자동 검색 서비스 URL)
    
      - **경로**에를 입력 ** / **합니다.

10. **웹 수신기 선택** 페이지의 **웹 수신기**에서 웹 수신기를 선택하거나 새 웹 수신기 정의 마법사를 사용하여 새 수신기를 만듭니다.

11. **인증 위임** 페이지에서 **위임 안 함 - 클라이언트에서 직접 인증할 수 없음**을 선택합니다.

12. **사용자 집합** 페이지에서 **모든 사용자**를 선택합니다.

13. **새 웹 게시 규칙 마법사 완료** 페이지에서 웹 게시 규칙 설정이 올바른지 확인하고 **마침**을 클릭합니다.

14. Forefront TMG의 웹 게시 규칙 목록에서 방금 추가한 새 규칙을 두 번 클릭하여 **속성**을 엽니다.

15. **브리징** 탭에서 다음을 구성합니다.
    
      - **웹 서버**를 선택합니다.
    
      - **HTTP 포트로 요청 리디렉션**을 선택하고 포트 번호로 **8080**을 입력합니다.
    
      - **SSL 포트로 요청 리디렉션**이 선택되어 있지 않은지 확인합니다.

16. **확인**을 클릭합니다.

17. 세부 정보 창에서 **적용**을 클릭하여 변경 내용을 저장하고 구성을 업데이트합니다.

18. **규칙 테스트**를 클릭하여 새 규칙이 올바르게 설정되었는지 확인합니다.

19. 다른 웹 게시 규칙에 대해 외부 자동 검색 서비스 URL이 정의되어 있지 않은지 확인합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 역방향 프록시 서버 설정](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

