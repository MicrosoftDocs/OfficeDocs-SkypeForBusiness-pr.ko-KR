---
title: Lync Server 2013에서 XMPP 게이트웨이 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b087b04a4f6bbf4b5740dcc28172d3f5312e793e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Lync Server 2013에서 XMPP 게이트웨이 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-28_

XMPP 게이트웨이 마이그레이션에 대 한 마지막 단계는 Lync Server 2013에 지 서버에 대 한 인증서를 구성 하 고, Lync Server 2013 XMPP 게이트웨이를 배포 하 고, XMPP 게이트웨이의 DNS 레코드를 업데이트 하는 것입니다. 이러한 단계는 XMPP 게이트웨이의 중단 시간을 최소화하면서 병렬로 수행되어야 합니다. 다음 단계를 수행 하기 전에 모든 사용자가 Microsoft Lync Server 2013 배포로 이동 해야 합니다.

<div class=" ">


> [!IMPORTANT]  
> XMPP 페더레이션은 sba (survivable branch 기기에 있는 사용자에 대해서는 지원 되지 않습니다. 이는 현재 상태 정보를 확인 하 고 IM 메시지를 교환 하는 방법에 모두 적용 됩니다.



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Lync Server 2013 에지 서버에서 XMPP 게이트웨이 인증서 구성

1.  에지 서버의 배포 마법사에서 **3단계: 인증서 요청, 설치 또는 할당** 옆에 있는 **다시 실행**을 클릭합니다.
    
    <div class=" ">
    

    > [!TIP]  
    > 처음으로 에지 서버를 배포하는 경우 "다시 실행" 대신 "실행"이 나타납니다.

    
    </div>

2.  **사용할 수 있는 인증서 작업** 페이지에서 **새 인증서 요청 만들기**를 클릭합니다.

3.  **인증서 요청** 페이지에서 **외부 에지 인증서**를 클릭합니다.

4.  **지연 또는 즉시 요청** 페이지에서 **지금 요청을 준비하고 나중에 보냅니다** 확인란을 선택합니다.

5.  **인증서 요청 파일** 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예를 들어, c:\\cert\_외부\_에 있는 .cer).

6.  **대체 인증서 템플릿 지정** 페이지에서 기본 WebServer 템플릿이 아닌 다른 템플릿을 사용하려면 **선택한 인증 기관에 대체 인증서 템플릿 사용** 확인란을 선택합니다.

7.  **이름 및 보안 설정** 페이지에서 다음을 수행합니다.
    
    1.  **이름**에 인증서 표시 이름을 입력합니다.
    
    2.  **비트 길이**에서 비트 길이를 지정합니다(일반적으로 기본값은 2048).
    
    3.  **인증서의 개인 키를 내보낼 수 있는 것으로 표시** 확인란이 선택되어 있는지 확인합니다.

8.  **조직 정보** 페이지에 조직 및 조직 구성 단위의 이름(예: 사업부 또는 부서)을 입력합니다.

9.  **지역 정보** 페이지에서 위치 정보를 지정합니다.

10. **주체 이름/주체 대체 이름** 페이지에 마법사에서 자동으로 채울 정보가 표시됩니다. 추가 주체 대체 이름이 필요한 경우 다음 두 단계에서 지정합니다.

11. **주체 대체 이름 (san)에 대 한 Sip 도메인 설정** 페이지에서 sip를 추가 하려면 도메인 확인란을 선택 합니다. \<주체\> 대체 이름 목록에 microsoft.rtc.management.xds.sipdomain object 항목을 입력 합니다.

12. **추가 주체 대체 이름 구성** 페이지에서 필요한 추가 주체 대체 이름을 지정합니다.
    
    <div class=" ">
    

    > [!TIP]  
    > XMPP 프록시가 설치된 경우 기본적으로 도메인 이름(예: contoso.com)이 SAN 항목에 채워집니다. 더 많은 항목이 필요한 경우 이 단계에서 추가합니다.

    
    </div>

13. **요청 요약** 페이지에서 요청을 생성하는 데 사용할 인증서 정보를 검토합니다.

14. 명령 실행을 마치면 **로그 보기**를 확인하거나 "다음"을 클릭하여 계속 진행합니다.

15. **인증서 요청 파일** 페이지에서 **보기**를 클릭하여 생성된 인증서 서명 요청(CSR) 파일을 확인하거나, **마침**을 클릭하여 인증서 마법사를 종료합니다.

16. 요청 파일을 복사하여 공용 CA(인증 기관)에 제출합니다.

17. 공용 인증서를 받아 가져오고 할당한 후 에지 서버 서비스를 중지한 다음 다시 시작해야 합니다. 이는 Lync Server 관리 콘솔에서 다음을 입력해서 수행할 수도 있습니다.
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>새로운 Lync Server 2013 XMPP 게이트웨이 구성

1.  Lync Server 제어판을 엽니다.

2.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭한 다음 **XMPP 페더레이션 파트너**를 클릭합니다.

3.  새 구성을 만들려면 **새로 만들기**를 클릭합니다.

4.  다음 설정을 정의합니다.

5.  **주 도메인**     (필수) 주 도메인은 XMPP 파트너의 기본 도메인입니다. 예를 들어 XMPP 파트너 도메인 이름에는 **fabrikam.com** 를 입력 합니다. 필수 항목입니다.

6.  **설명**   이 특정 구성에 대 한 참고 사항 또는 기타 식별 정보에 대 한 설명입니다. 이 항목은 선택 사항입니다.

7.  **추가 도메인**   추가 도메인은 허용 되는 xmpp 통신의 일부로 포함 되어야 하는 xmpp 파트너의 도메인에 속하는 도메인입니다. 예를 들어 주 도메인이 **fabrikam.com**인 경우에는 xmpp를 사용 하 여 통신 하는 fabrikam.com 아래의 다른 모든 도메인을 나열 합니다.

8.  **파트너 유형**    **파트너 유형은** 필수 설정입니다. 추가할 수 있는 연락처를 설명 하 고 적용 하려면 다음 중 하나를 선택 해야 합니다. 다음 중에서 선택할 수 있습니다.
    
      - **페더레이션된**    **페더레이션** 파트너 유형은 Lync Server 배포와 xmpp 파트너 간의 높은 신뢰 수준을 나타냅니다.이 파트너 유형은 같은 엔터프라이즈 내의 XMPP 서버와 페더레이션 하거나 설정 된 비즈니스 관계가 있는 위치에 사용 하는 것이 좋습니다.페더레이션 파트너의 XMPP 연락처는 다음을 수행할 수 있습니다.
        
        1.  Lync 사용자로부터의 명시적 권한 부여 없이 Lync 대화 상대를 추가하고 현재 상태를 볼 수 있습니다.
        
        2.  Lync 사용자가 자신의 대화 상대 목록에 추가했는지 여부와 상관없이 Lync 대화 상대에게 메신저 대화를 보낼 수 있습니다.
        
        3.  Lync 사용자의 상태 메모를 볼 수 있습니다.
    
      - **공용 확인**    **공용 확인** 된 파트너는 해당 사용자의 id를 확인 하기 위해 신뢰할 수 있는 공용 xmpp 공급자입니다.공용 확인 된 네트워크의 XMPP 연락처는 lync 사용자 로부터 온 권한 부여 없이 Lync 대화 상대를 추가 하 고 현재 상태를 확인 하 고 인스턴트 메시지를 보낼 수 있습니다.XMPP 연락처 공용 확인 네트워크에는 Lync 사용자의 상태 노트가 표시 되지 않습니다.이 설정은 권장 되지 않습니다.
    
      - **공용**확인 되지 **않은 공용 확인 되지 않은 파트너는** 해당 사용자의 id를 확인 하기 위해 신뢰할 수 없는 공용 xmpp 공급자입니다.   공용 확인 되지 않은 네트워크의 XMPP 사용자는 Lync 사용자가 연락처 목록에 추가 하 여 명시적으로 권한을 부여한 경우가 아니면 Lync 사용자와 통신할 수 없습니다.공용 확인 되지 않은 네트워크의 XMPP 사용자는 Lync 사용자의 상태 메모를 볼 수 없습니다.이 설정은 Google 대화 같은 공용 XMPP 공급자가 있는 모든 페더레이션에 권장 됩니다.

9.  **연결 형식:** 다양한 규칙 및 다이얼백 설정을 정의합니다.
    
      - **Tls 협상**   은 tls 협상 규칙을 정의 합니다. XMPP 서비스에 대해 TLS를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다. "선택 사항"으로 설정하는 경우 협상 필수 항목 결정을 위해 요구 사항을 최대한 XMPP 서비스까지 그대로 둘 수 있습니다. 유효 및 알려진 오류 구성을 포함 하 여 SASL, TLS 및 전화 접속 회의 협상에 대해 가능한 모든 설정 및 세부 정보를 확인 하려면 [Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정을](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)참조 하세요.
        
          - <span></span>  
            **필수**   xmpp 서비스에 TLS 협상이 필요 합니다.
        
          - <span></span>  
            **Optional**   xmpp 서비스는 TLS가 필수-협상 중임을 나타냅니다.
        
          - <span></span>  
            **지원 되지 않음**   xmpp 서비스에서 TLS를 지원 하지 않습니다.
    
      - **Sasl 협상**   은 sasl 협상 규칙을 정의 합니다. XMPP 서비스에 대해 SASL를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다. "선택 사항"으로 설정하는 경우 협상 필수 항목 결정을 위해 요구 사항을 최대한 파트너 XMPP 서비스까지 그대로 둘 수 있습니다.
        
          - <span></span>  
            **필수**   xmpp 서비스에 SASL 협상이 필요 합니다.
        
          - <span></span>  
            **Optional**   xmpp 서비스는 SASL이 필수-협상 임을 나타냅니다.
        
          - <span></span>  
            **지원 되지 않음**   xmpp 서비스에서 SASL을 지원 하지 않습니다.
    
      - **지원 서버 전화 접속 회의 협상** 지원 서버 전화 접속 회의 협상 프로세스는 DNS (domain name system) 및 신뢰할 수 있는 서버를 사용 하 여 요청이 유효한 XMPP 파트너 로부터 온 것 인지 확인 합니다. 이 작업을 수행 하기 위해 원래 서버는 생성 된 전화 접속 회의 키를 사용 하 여 특정 유형의 메시지를 만들고 DNS에서 수신 서버를 조회 합니다. 원본 서버가 XML 스트림의 키를 결과 DNS 조회로 전송 하 고 받는 서버를 제공 합니다. XML stream에서 키를 받으면 수신 서버가 원래 서버에 응답 하지 않지만 알려진 신뢰할 수 있는 서버로 키를 보냅니다. 신뢰할 수 있는 서버에서 키가 유효 하거나 올바르지 않은지 확인 합니다. 올바르지 않으면 받는 서버가 원래 서버에 응답 하지 않습니다. 키가 올바르면 받는 서버가 원래 서버에 id 및 키가 유효 하며 대화를 시작할 수 있음을 알립니다.
        
        **전화 접속 회의 협상**의 유효한 두 상태는 다음과 같습니다.
        
          - <span></span>  
            **True**   원본 서버에서 요청을 받아야 하는 경우 xmpp 서버가 전화 접속 회의 협상을 사용 하도록 구성 됩니다.
        
          - <span></span>  
            **False**   xmpp 서버가 전화 접속 회의 협상을 사용 하도록 구성 되어 있지 않으며, 원래 서버에서 요청을 받아야 하는 경우 해당 서버는 무시 됩니다.

10. **커밋**을 클릭하여 변경 내용을 사이트 또는 사용자 정책에 저장합니다.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Lync Server 2013 XMPP 게이트웨이의 DNS 레코드 업데이트

1.  XMPP 페더레이션을 사용 하도록 DNS를 구성 하려면 외부 DNS:\_xmpp-server에 다음 SRV 레코드를 추가 합니다. \_tcp를 \<도메인 이름\> SRV 레코드는에 지 서버의 액세스에 지 FQDN을 확인 하며 포트 값은 5269입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

