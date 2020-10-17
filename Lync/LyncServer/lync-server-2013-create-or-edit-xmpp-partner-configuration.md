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
ms.openlocfilehash: 1517ef4a7515a46b9237b1788c457c3aee10953d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514805"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Lync Server 2013에서 XMPP 파트너 구성 만들기 또는 편집

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-09-03_

Microsoft Lync Server 2013는 Edge 서버 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이와 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 프록시를 통합 합니다. 다른 XMPP 배포 로부터의 연결을 허용 하려면 Lync Server 제어판에서 XMPP를 구성 해야 합니다. XMPP 도메인별로 설정을 구성합니다. 새 파트너 연결을 만들려면 다음을 수행합니다.

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>새 페더레이션 파트너를 만들거나 기존 구성을 편집 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭한 다음 **XMPP 페더레이션 파트너**를 클릭합니다.

4.  새 구성을 만들려면 **새로 만들기**를 클릭합니다.

5.  기존 구성을 편집하려면 구성을 선택하고 **편집**을 클릭합니다.

6.  **XMPP 페더레이션 파트너**에 대한 구성을 만들거나 편집하려면 다음 설정을 정의합니다.

7.  **주 도메인** (필수) 주 도메인은 XMPP 파트너의 기본 도메인입니다. 예를 들어 XMPP 파트너 도메인 이름에는 **fabrikam.com** 를 입력 합니다. 필수 항목입니다.

8.  **설명**입니다. 설명은 이러한 특정 구성에 대 한 메모 또는 기타 식별 정보에 대 한 설명입니다. 이 항목은 선택 사항입니다.

9.  **추가 도메인** 추가 도메인은 허용 되는 XMPP 통신의 일부로 포함 되어야 하는 XMPP 파트너 도메인의 일부인 도메인입니다. 예를 들어 주 도메인이 **fabrikam.com**인 경우에는 xmpp를 사용 하 여 통신 하는 fabrikam.com 아래의 다른 모든 도메인을 나열 합니다. 예를 들어 회사 XMPP 도메인 및 정보 기술 XMPP 도메인에 대해 **corp.fabrikam.com** 및 **it.fabrikam.com** 를 fabrikam의 주 xmpp 도메인에 입력할 수 있습니다.

10. **파트너 유형**입니다. **파트너 유형은** 필수 설정 이며 드롭다운 메뉴에서 세 가지 선택 항목을 선택할 수 있습니다. 추가할 수 있는 연락처를 설명 하 고 적용 하려면 다음 중 하나를 선택 해야 합니다. 다음 중에서 선택할 수 있습니다.
    
      - **페더레이션** **페더레이션** 파트너 종류는 Lync Server 또는 Office Communications Server 2007 R2 파트너 배포 간의 트러스트 된 연결입니다.
    
      - **공용 확인** **공용으로 확인** 된 파트너는 공급자가 확인 한 배포에 포함 된 연락처를 사용자의 대화 상대 목록에 추가할 수 있는 경우입니다. Lync 사용자 로부터 초대를 보내거나, Lync 사용자가 파트너 연락처의 초대를 수락할 수 있습니다.
    
      - **공용**확인 되지 않음 **공용** 확인 되지 않은 관계는 두 배포 사이에 설정 및 확인이 가능 하지 않은 상태를 의미 합니다. Lync 사용자가 자신의 대화 상대 목록에 Lync 사용자를 추가할 수 있으려면 해당 연락처의 확인 되지 않은 연락처를 초대 해야 합니다. 예를 들어 Google GTalk는 Lync Server와 관련 된 공용 확인 된 XMPP 서비스가 아닙니다. GTalk 사용자는 Lync 사용자가 명시적인 초대를 보내지 않은 경우에는 Lync 사용자를 연락처로 추가할 수 없습니다.

11. 스트림 협상 및 보안 방법 TLS(전송 계층 보안) 및 SASL(Software Authentication and Security Layer)에 대한 참고 사항
    
    XSF(**XMPP Standards Foundation**) 및 IETF(**Internet Engineering Task Force**)에서는 TLS 클라이언트 인증서, TLS 서버 인증서 및 SASL 메커니즘 사용/관리에 대한 규칙 및 표준 집합을 정의합니다. XMLL 스트림을 보호하려면 TLS 및 SASL을 사용해야 합니다. XMPP Standards 문서 **XEP-0178**에서 "PKIX 인증서를 사용하는 SASL EXTERNAL 메커니즘 사용을 위해 권장 프로토콜 흐름을 지정(특히 XMPP 서비스에서 TLS 협상을 필수로 지정하는 경우)"하는 작업은 PKI(공용 키 인프라)로 지칭됩니다.
    
    XEP 요구 사항에 대 한 자세한 내용은 XSF 문서 XEP-0178를 참조 하세요. 자세한 내용은 "XEP-0178: SASL 외부의 인증서 사용에 대 한 모범 사례"를 참조 하세요. <http://xmpp.org/extensions/xep-0178.html>
    
    IETF 문서 "확장 가능 메시징 및 현재 상태 프로토콜 (XMPP): 코어", 섹션 5.0, STARTTLS 협상을 참조 하십시오 <https://tools.ietf.org/html/rfc6120> .
    
      - **TLS 협상** TLS 협상 규칙을 정의합니다. XMPP 서비스에 대해 TLS를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다. "선택 사항"으로 설정하는 경우 협상 필수 항목 결정을 위해 요구 사항을 최대한 XMPP 서비스까지 그대로 둘 수 있습니다. 유효 및 알려진 오류 구성을 포함 하 여 SASL, TLS 및 전화 접속 회의 협상에 대해 가능한 모든 설정 및 세부 정보를 확인 하려면 [Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정을](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)참조 하세요.
        
          - <span></span>  
            **필수**입니다. XMPP 서비스에 TLS 협상이 필요합니다.
        
          - <span></span>  
            **선택 사항**입니다. XMPP 서비스는 TLS가 협상 필수 항목임을 나타냅니다.
        
          - <span></span>  
            **지원 되지 않습니다**. XMPP 서비스가 TLS를 지원하지 않습니다.
    
      - **SASL 협상** SASL 협상 규칙을 정의합니다. XMPP 서비스에 대해 SASL를 필수, 선택 사항 또는 지원 안 됨으로 설정할 수 있습니다. 선택을 선택하면 파트너 XMPP 서비스에서 필수/협상에 대한 요구 사항을 결정합니다.
        
        <div>
        

        > [!WARNING]  
        > SASL에는 TLS가 필요합니다. SASL을 사용하려면 TLS가 필수 또는 선택이어야 합니다. SASL을 필수 또는 선택으로 정의하는 모든 구성에서는 TLS를 지원해야 합니다. TLS를 필수 또는 옵션으로 설정하지 않은 상태에서 <STRONG>커밋</STRONG>을 클릭하여 변경 내용을 저장하면 SASL에서 TLS를 지원해야 하며 변경 내용이 저장되지 않는다는 경고가 표시됩니다. 이 오류를 해결하려면 TLS를 <STRONG>필수</STRONG> 또는 <STRONG>선택</STRONG>으로 설정합니다. SASL 사용이 선택 사항이며 TLS 협상을 지원할 수 없는 경우에는 SASL 협상을 <STRONG>지원되지 않음</STRONG>으로 설정해야 합니다. XMPP 서비스에서 TLS 및 SASL에 대해 사용해야 하는 적절한 협상 스트림을 확인해야 하며, 그렇지 않으면 서비스가 중단됩니다.

        
        </div>
        
          - <span></span>  
            **필수**입니다. XMPP 서비스에 SASL 협상이 필요합니다.
        
          - <span></span>  
            **선택 사항**입니다. XMPP 서비스는 SASL가 협상 필수 항목임을 나타냅니다.
        
          - <span></span>  
            **지원 되지 않습니다**. XMPP 서비스가 SASL를 지원하지 않습니다.
    
      - **전화 접속 회의 협상** 전화 접속 회의 협상은 .XSF에서 문서 **Xep-220: Server 전화 접속 회의** 에 의해 정의 됩니다 <http://xmpp.org/extensions/xep-0220.html> . Server 전화 접속 회의 프로세스는 DNS (domain name system) 및 신뢰할 수 있는 서버를 사용 하 여 요청이 유효한 XMPP 파트너 로부터 온 것을 확인 합니다. 이 작업을 수행 하기 위해 원래 서버는 생성 된 전화 접속 회의 키를 사용 하 여 특정 유형의 메시지를 만들고 DNS에서 수신 서버를 조회 합니다. 원본 서버가 XML 스트림의 키를 결과 DNS 조회로 전송 하 고 받는 서버를 제공 합니다. XML stream에서 키를 받으면 수신 서버가 원래 서버에 응답 하지 않지만 알려진 신뢰할 수 있는 서버로 키를 보냅니다. 신뢰할 수 있는 서버에서 키가 유효 하거나 올바르지 않은지 확인 합니다. 올바르지 않으면 받는 서버가 원래 서버에 응답 하지 않습니다. 키가 올바르면 받는 서버가 원래 서버에 id 및 키가 유효 하며 대화를 시작할 수 있음을 알립니다.
        
        **전화 접속 회의 협상**의 유효한 두 상태는 다음과 같습니다.
        
          - <span></span>  
            **True**입니다. 원본 서버에서 요청을 받아야 하는 경우 XMPP 서버가 전화 접속 회의 협상을 사용 하도록 구성 되어 있습니다.
        
          - <span></span>  
            **False**입니다. XMPP 서버가 전화 접속 회의 협상을 사용하도록 구성되지 않으며, 원본 서버에서 요청을 받아야 하는 경우 해당 요청은 무시됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

