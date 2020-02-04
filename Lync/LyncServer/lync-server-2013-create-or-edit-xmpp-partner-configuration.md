---
title: 'Lync Server 2013: XMPP 파트너 구성 만들기 또는 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488665bca5cd2ad1b4d2d91a3c85a6a1ddaa3916
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Lync Server 2013에서 XMPP 파트너 구성 만들기 또는 편집

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-09-03_

Microsoft Lync Server 2013는 Edge 서버의 XMPP (확장 가능한 메시징 및 현재 상태 프로토콜) 프록시를 통합 하 고 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이를 표시 합니다. 다른 XMPP 배포의 연결을 허용 하려면 Lync Server 제어판에서 XMPP를 구성 해야 합니다. XMPP 도메인 단위로 설정을 구성 합니다. 새 파트너 연결을 만들려면 다음을 수행 합니다.

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>새 페더레이션 파트너를 만들거나 기존 구성을 편집 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **Xmpp 페더레이션된 파트너**를 클릭 합니다.

4.  새 구성을 만들려면 **새로** 만들기를 클릭 합니다.

5.  기존 구성을 편집 하려면 구성을 선택 하 고 **편집** 을 클릭 합니다.

6.  **Xmpp 페더레이션 파트너**에 대 한 구성을 만들거나 편집 하려면 다음 설정을 정의 합니다.

7.  **주 도메인** (필수). 주 도메인은 XMPP 파트너의 기본 도메인입니다. 예를 들어 XMPP 파트너 도메인 이름에 대해 **fabrikam.com** 를 입력 합니다. 필수 입력 사항입니다.

8.  **설명**. 설명은이 특정 구성에 대 한 메모 또는 기타 식별 정보에 대 한 설명입니다. 이 항목은 선택 사항입니다.

9.  **추가 도메인**. 추가 도메인은 허용 된 XMPP 통신의 일부로 포함 되어야 하는 XMPP 파트너의 도메인에 속하는 도메인입니다. 예를 들어 주 도메인이 **fabrikam.com**인 경우에는 fabrikam.com 아래에 있는 다른 모든 도메인이 xmpp를 통해 통신 하도록 나열 됩니다. 예를 들어, 회사 XMPP 도메인 및 정보 기술 XMPP 도메인에 대 한 **corp.fabrikam.com** 및 **it.fabrikam.com** 를 fabrikam의 주 xmpp 도메인 아래에 입력할 수 있습니다.

10. **파트너 유형**. **파트너 종류** 는 필수 설정이 며 드롭다운 메뉴에서 세 가지 선택 항목을 선택할 수 있도록 합니다. 추가할 수 있는 연락처를 설명 하 고 적용 하려면 다음 중 하나를 선택 해야 합니다. 다음 중에서 선택할 수 있습니다.
    
      - **페더레이션**. **페더레이션** 파트너 종류는 Lync Server 또는 Office Communications Server 2007 R2 파트너 배포 간의 신뢰 된 연결입니다.
    
      - **공용이 확인**되었습니다. **공개 확인** 된 파트너는 공급자가 확인 한 배포의 일부인 연락처를 사용자의 연락처 목록에 추가할 수 있는 경우입니다. 초대는 Lync 사용자에 게 서 보내거나, Lync 사용자가 파트너 연락처의 초대를 수락할 수 있습니다.
    
      - **공용**이 확인 되지 않았습니다. 확인 되지 않은 **공용** 관계는 두 배포 간에 설정 및 확인 가능한 상태가 없음을 의미 합니다. Lync 사용자는 해당 연락처에 대 한 확인 되지 않은 연락처를 초대 하 여 Lync 사용자를 자신의 연락처 목록에 추가할 수 있도록 해야 합니다. 예를 들어 Google GTalk는 Lync Server와 관련 하 여 공용으로 확인 된 XMPP 서비스는 아닙니다. GTalk 사용자는 Lync 사용자가 보낸 명시적 초대가 없는 경우 Lync 사용자를 연락처로 추가할 수 없습니다.

11. 스트림 협상과 보안 방법 (TLS (전송 계층 보안) 및 SASL (소프트웨어 인증 및 보안 레이어)에 대 한 참고 사항:
    
    **Xmpp 표준 파운데이션** (XSF) 및 **Internet 공학적 작업 포스** (IETF)는 TLS 클라이언트 인증서, TLS 서버 인증서 및 SASL 메커니즘을 사용 하 고 관리 하기 위한 규칙 및 표준 집합을 정의 합니다. TLS 및 SASL을 사용 하는 것은 XMPP 스트림을 보호 하는 데 필요한 프로세스입니다. XMPP 표준 문서 **Xmpp-0178**에서 "PKIX 인증서와 함께 SASL 외부 메커니즘을 사용 하기 위한 권장 프로토콜 흐름을 지정 합니다. 특히 xmpp 서비스에서 TLS가 필수 인 경우에는이를 나타냅니다. XSF 설명서에 명시 된 대로 PKIX는 공개 키 인프라 (PKI 라고도 함)를 나타냅니다.
    
    XEP 요구 사항에 대 한 자세한 내용은 XSF 문서 XEP-0178을 참조 하세요. 자세한 내용은 "XEP-0178: SASL 외부의 인증서 사용에 대 한 모범 사례"를 참조 하세요. <http://xmpp.org/extensions/xep-0178.html>
    
    IETF 문서 "확장할 수 있는 메시징 및 현재 상태 프로토콜 (XMPP): Core", 섹션 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>를 참조 하세요.
    
      - **TLS 협상**. TLS 협상 규칙을 정의 합니다. XMPP 서비스는 TLS를 요구 하거나 TLS 옵션을 만들거나 해당 TLS가 지원 되지 않는 것으로 정의할 수 있습니다. 선택 항목을 선택 하면 필수적으로 협상을 결정할 수 있도록 XMPP 서비스에 대 한 요구 사항이 유지 됩니다. SASL, TLS 및 Dialback 협상 (유효 하지 않은 알려진 오류 구성 포함)에 대 한 가능한 모든 설정 및 세부 정보를 보려면 [Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정을](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)참조 하세요.
        
          - <span></span>  
            **필요**합니다. XMPP 서비스에는 TLS 협상이 필요 합니다.
        
          - <span></span>  
            **선택 사항**입니다. XMPP 서비스는 TLS가 필수적으로 협상 됨을 나타냅니다.
        
          - <span></span>  
            **지원 되지 않습니다**. XMPP 서비스는 TLS를 지원 하지 않습니다.
    
      - **SASL 협상**. SASL 협상 규칙을 정의 합니다. XMPP 서비스에는 SASL이 필요 하거나, SASL을 선택적으로 만들거나, SASL이 지원 되지 않는 것으로 정의할 수 있습니다. 선택 항목을 선택 하면 파트너 XMPP 서비스에 대 한 필수-협상 결정을 위한 요구 사항이 유지 됩니다.
        
        <div>
        

        > [!WARNING]  
        > SASL에는 TLS가 필요 합니다. SASL을 사용 하려면 TLS가 필수 또는 선택 사항 이어야 합니다. SASL을 필수 또는 선택 사항으로 정의 하는 구성은 모두 TLS를 지원 해야 합니다. <STRONG>커밋을</STRONG> 클릭 하 여 변경 내용을 저장 하는 경우, tls를 필수 또는 선택 사항으로 설정 하지 않으면 SASL이 tls를 지원 해야 하며 변경 내용이 저장 되지 않은 경고가 표시 됩니다. 이 오류를 해결 하려면 TLS를 <STRONG>Required</STRONG> 또는 <STRONG>Optional</STRONG>로 설정 합니다. SASL을 사용할 수 없는 경우 TLS 협상이 지원 되지 않으면 SASL negotiation를 <STRONG>지원 되지 않는</STRONG>것으로 설정 해야 합니다. XMPP 서비스를 사용 하 여 TLS 및 SASL에 적합 한 협상 스트림 또는 서비스 중단이 발생할 지 여부를 확인 합니다.

        
        </div>
        
          - <span></span>  
            **필요**합니다. XMPP 서비스에는 SASL 협상이 필요 합니다.
        
          - <span></span>  
            **선택 사항**입니다. XMPP 서비스는 SASL이 필수적으로 협상 됨을 나타냅니다.
        
          - <span></span>  
            **지원 되지 않습니다**. XMPP 서비스는 SASL을 지원 하지 않습니다.
    
      - **Dialback 협상**. Dialback 협상은 XSF에서 문서 **Xep-220: Server Dialback** <http://xmpp.org/extensions/xep-0220.html>에 의해 정의 됩니다. 서버 dialback 프로세스는 DNS (domain name system) 및 권한 있는 서버를 사용 하 여 해당 요청이 유효한 XMPP 파트너 로부터 제공 되었는지 확인 합니다. 이렇게 하려면 원래 서버에서 생성 된 dialback 키를 사용 하 여 특정 유형의 메시지를 만들고 DNS에서 받는 서버를 조회 합니다. 원래 서버는 XML 스트림의 키를 결과 DNS 조회로 보내고 받는 서버를 검색 합니다. XML 스트림을 통해 키를 수신 하면 받는 서버는 원래 서버에 응답 하지 않지만 알려진 신뢰할 수 있는 서버로 키를 보냅니다. 권한이 있는 서버는 키가 유효 하거나 유효 하지 않은지 확인 합니다. 유효 하지 않은 경우 받는 서버는 원래 서버에 응답 하지 않습니다. 키가 유효 하면 받는 서버는 id 및 키가 유효 하 고 대화를 시작할 수 있음을 원래 서버에 알립니다.
        
        **Dialback 협상**에는 다음과 같은 두 가지 유효한 상태가 있습니다.
        
          - <span></span>  
            **True**입니다. 원본 서버에서 요청을 받아야 하는 경우 XMPP 서버는 Dialback 협상을 사용 하도록 구성 되어 있습니다.
        
          - <span></span>  
            **False**입니다. XMPP 서버는 Dialback 협상을 사용 하도록 구성 되어 있지 않으며 원래 서버에서 요청을 수신 해야 하는 경우 무시 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

