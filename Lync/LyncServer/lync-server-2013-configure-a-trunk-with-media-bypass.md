---
title: 'Lync Server 2013: 미디어 바이패스로 트렁크 구성'
description: 'Lync Server 2013: 미디어 바이패스를 사용 하 여 트렁크를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51bd58a685e1f4c222a863c21022b3c9dc7c70d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566754"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스로 트렁크 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-07_

미디어 바이패스를 사용 하 여 트렁크를 구성 하려면 다음 단계를 수행 합니다. 미디어 바이패스를 사용 하지 않도록 트렁크를 구성 하려면 [Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)를 참조 하세요. 미디어 바이패스는 배포할 중재 서버 수를 최소화할 때 유용합니다. 일반적으로 중재 서버 풀은 중앙 사이트에 배포되며 분기 사이트에서 게이트웨이를 제어합니다. 미디어 바이패스를 사용하도록 설정하면 분기 사이트에서 클라이언트의 PSTN(공중 전화망) 통화에 대한 미디어가 해당 사이트에서 게이트웨이를 통과해 바로 흐르도록 할 수 있습니다. Lync Server 2013 아웃 바운드 통화 경로 및 Enterprise Voice 정책을 적절 하 게 구성 해야 분기 사이트에 있는 클라이언트의 PSTN 통화가 해당 게이트웨이로 라우팅됩니다.

미디어 바이패스를 사용 하도록 설정 하는 것이 좋습니다. 그러나 SIP 트렁크에서 미디어 바이패스를 사용 하도록 설정 하기 전에 정규화 된 SIP 트렁크 공급자가 미디어 바이패스를 지원 하며 시나리오를 성공적으로 사용 하도록 설정 하기 위한 요구 사항을 충족할 수 있는지 확인 합니다. 특히 공급자는 조직의 내부 네트워크에 있는 서버의 IP 주소를가지고 있어야 합니다. 공급자가 이 시나리오를 지원할 수 없는 경우 미디어 바이패스는 실패하게 됩니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 미디어 바이패스를 계획](lync-server-2013-planning-for-media-bypass.md) 합니다 .를 참조 하십시오.

<div>


> [!NOTE]  
> 미디어 바이패스는 모든 공중 전화망 (PSTN) 게이트웨이, IP-PBX 및 SBC (Session Border Controller)와 상호 작용 하지 않습니다. Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다. 미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 나열 된 제품과 버전 에서만 지원 됩니다 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

아래에 설명 된 트렁크 구성은이 트렁크 구성에 할당 된 트렁크에 적용 되는 매개 변수 집합을 그룹으로 지정 합니다. 특정 트렁크 구성의 범위를 전역으로(특정 사이트 또는 풀 구성을 포함하지 않는 모든 트렁크가 포함됨) 또는 사이트나 풀로 지정할 수 있습니다. 풀 수준 트렁크 구성은 특정 트렁크 구성의 범위를 단일 트렁크로 지정하는 데 사용됩니다.

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a>미디어 바이패스로 트렁크를 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭한 다음 **트렁크 구성**을 클릭합니다.

4.  **트렁크 구성** 페이지에서 다음 방법 중 하나를 사용하여 트렁크를 구성합니다.
    
      - 기존 트렁크(예: **전역** 트렁크)를 두 번 클릭하여 **트렁크 구성 편집** 대화 상자를 표시합니다.
    
      - **새로 만들기**를 클릭한 다음 새 트렁크 구성의 범위를 선택합니다.
        
          - **사이트 트렁크:** **사이트 선택**에서이 트렁크 구성에 대 한 사이트를 선택 하 고 **확인**을 클릭 합니다. 트렁크 구성이 이미 만들어진 사이트는 **사이트 선택** 대화 상자에 표시되지 않습니다. 이 트렁크 구성은 사이트의 모든 트렁크에 적용됩니다.
        
          - **풀 트렁크:** 이 트렁크 구성이 적용 되는 트렁크의 이름을 선택 합니다. 이 트렁크는 루트 트렁크 또는 토폴로지 작성기에 정의 된 추가 트렁크 될 수 있습니다. **서비스 선택**에서 **확인**을 클릭 합니다. 트렁크 구성이 이미 만들어진 특정 트렁크는 **서비스 선택** 대화 상자에 표시되지 않습니다.
    
    <div>
    

    > [!NOTE]  
    > 트렁크 구성 범위는 선택한 후에 변경할 수 없습니다.<BR><STRONG>이름</STRONG> 필드는 트렁크 구성의 연결된 사이트 또는 서비스 이름으로 미리 채워지며 변경할 수 없습니다.

    
    </div>

5.  **지원 되는 최대 초기 대화 상자**에 값을 지정 합니다. 공중 전화망 (PSTN) 게이트웨이, IP-PBX 또는 ITSP 세션 경계 컨트롤러 (SBC)가 중재 서버에 보낸 초대로 수신할 수 있는 분기 응답의 최대 개수입니다. 기본값은 20입니다.
    
    <div>
    

    > [!NOTE]  
    > 이 값을 변경하기 전에 서비스 공급자나 장치 제조업체에 시스템 용량에 대한 자세한 내용을 문의하십시오.

    
    </div>

6.  다음 **암호화 지원 수준** 옵션 중 하나를 선택합니다.
    
      - **필수 사항:** Secure SRTP (실시간 전송 프로토콜) 암호화는 중재 서버와 게이트웨이 또는 PBX (private branch exchange) 간의 트래픽을 보호 하는 데 사용 되어야 합니다.
    
      - **선택 사항:** 서비스 공급자 또는 장비 제조업체에서 지 원하는 경우 SRTP 암호화가 사용 됩니다.
    
      - **지원 되지 않음:** SRTP 암호화는 서비스 공급자 또는 장비 제조업체에서 지원 하지 않으므로 사용 되지 않습니다.

7.  트렁크 피어가 처리하도록 미디어가 중재 서버를 바이패스하도록 하려면 **미디어 바이패스 사용** 확인란을 선택합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 미디어 바이패스가 올바르게 작동하려면 PSTN 게이트웨이, IP-PBX 또는 ITSP 세션 경계 컨트롤러가 특정 기능을 지원해야 합니다. 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013에서 미디어 바이패스를 계획</A> 합니다 .를 참조 하십시오.

    
    </div>

8.  알려진 미디어 종료 지점(예: 미디어 종료 IP가 신호 종료 IP와 같은 PSTN 게이트웨이)이 있는 경우 **중앙 집중식 미디어 처리** 확인란을 선택합니다. 트렁크에 알려진 미디어 종료 지점이 없는 경우에는 이 확인란의 선택을 취소합니다.

9.  트렁크 피어가 중재 서버에서 받은 SIP를 수신 하는 것을 지원 하면 **게이트웨이를 참조로 보내기를 사용** 확인란을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>미디어 바이패스 사용</STRONG> 옵션을 선택한 상태에서 이 옵션을 사용하지 않도록 설정하면 추가 설정이 필요합니다. 트렁크 피어가 중재 서버로부터의 SIP REFER 요청 수신을 지원하지 않는데 미디어 바이패스를 사용하는 경우 미디어 바이패스에 대한 적절한 조건을 지원하기 위해 <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet도 실행하여 활성 및 대기 중인 통화에 대해 RTCP를 사용하지 않도록 설정해야 합니다. 자세한 내용은 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 관리 셸</A> 설명서를 참조 하십시오.<BR>또는 전송 된 통화가 미디어에서 무시 되 고 게이트웨이가 SIP 참조 요청을 지원 하지 않는 경우에는 <STRONG>타사 통화 제어를 사용 하 여 참조 사용</STRONG> 을 선택할 수 있습니다.

    
    </div>

10. 원하는 경우 트렁크 간 라우팅을 사용하도록 설정하려면 PSTN 사용 레코드를 이 트렁크 구성에 연결하고 구성합니다. 이 트렁크 구성에 연결되는 PSTN 사용은 Lync 끝점에서 시작되지 않은 트렁크를 통과하는 모든 수신 전화에 적용됩니다. 트렁크 구성에 연결된 PSTN 사용 레코드를 관리하려면 다음 방법 중 하나를 사용합니다.
    
      - Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다. 이 트렁크 구성과 연결할 레코드를 강조 표시하고 **확인**을 클릭합니다.
    
      - 이 트렁크 구성에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 **제거**를 클릭합니다.
    
      - 새 PSTN 사용 레코드를 정의하고 이 트렁크 구성과 연결하려면 다음을 수행합니다.
        
        1.  **새로 만들기**를 클릭합니다.
        
        2.  **이름** 필드에서 레코드를 설명하는 고유한 이름을 지정합니다.
            
            <div>
            

            > [!NOTE]  
            > PSTN 사용 레코드 이름은 Enterprise Voice 배포 내에서 고유 해야 합니다. 레코드를 저장한 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.

            
            </div>
        
        3.  다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.
            
              - Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 합니다. 이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인**을 클릭합니다.
            
              - PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거**를 클릭합니다.
            
              - 새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기**를 클릭합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.
            
              - 이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시**를 클릭합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.
        
        4.  **확인**을 클릭합니다.
    
      - 이 트렁크 구성에 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 수행합니다.
        
        1.  편집할 PSTN 사용 레코드를 선택하고 **자세한 정보 표시**를 클릭합니다.
        
        2.  다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.
            
              - Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 합니다. 이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인**을 클릭합니다.
            
              - PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거**를 클릭합니다.
            
              - 새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기**를 클릭합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.
            
              - 이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시**를 클릭합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.
        
        3.  **확인**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 구성 중인 트렁크에 연결 된 중재 서버 피어에 따라 PSTN 사용 레코드를 연결 하는 것이 중요 합니다. 중재 서버 피어가 PSTN 게이트웨이 또는 SBC (Session Border Controller) 인 경우 트렁크 구성이 pstn 대상 또는 Lync Server를 통해 연결 된 다른 다운스트림 시스템으로 경로 하는 PSTN 사용 레코드에 연결 되어 있지 않는 것이 좋습니다.

    
    </div>

11. 최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경하려면 PSTN 사용 레코드를 선택하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > PSTN 사용 레코드가 트렁크 구성에서 나열되는 순서가 중요합니다. Lync Server가 목록을 위에서 아래로 트래버스 합니다.

    
    </div>

12. **RTP 사용 래치** 를 선택 하 여 NAT (network address translation) 또는 방화벽에서 클라이언트에 대 한 우회 미디어 및 래치를 지 원하는 SBC를 사용 하도록 설정 해야 합니다.

13. 중재 서버의 게이트웨이 피어로 통화 기록 정보를 보낼 수 있도록 하려면 **착신 전환 사용 내역** 을 선택 해야 합니다.

14. No **Forward 사용-어설션 됨-설정 됨-id 데이터** 를 선택 하 여 중재 서버 쪽 및 게이트웨이 쪽 간에 전달 되는 p-어설션된-identity (pai) 호출 작성기 정보를 사용할 수 있도록 설정 해야 합니다 (있는 경우 반대의 경우도 마찬가지).

15. 빠른 장애 조치(failover)를 사용하도록 설정하려면 **아웃바운드 라우팅 장애 조치(failover) 타이머 사용**을 선택해야 합니다. 이 트렁크와 연결된 게이트웨이는 아웃바운드 통화를 처리하는 10초 이내에 알림을 제공할 수 있습니다. 중재 서버에서이 알림을 받지 못하면 다른 트렁크로 전환 하는 것이 발생 합니다. 대기 시간으로 인해 응답 시간이 지연되거나 게이트웨이가 응답하는 데 10초보다 오래 걸리는 네트워크에서는 빠른 장애 조치(failover)를 사용하지 않도록 설정해야 합니다.

16. 원하는 경우 트렁크에 대해 **호출 번호 변환 규칙**을 연결 및 구성합니다. 이러한 변환 규칙은 아웃바운드 통화의 호출 번호에 적용됩니다.
    
      - Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다. **변환 규칙 선택**에서 트렁크와 연결할 규칙을 클릭한 다음 **확인**을 클릭합니다.
    
      - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기**를 클릭합니다. 새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.
    
      - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시**를 클릭합니다. 자세한 내용은 배포 설명서에서 [Lync Server 2013의 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.
    
      - 기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사**를 클릭한 다음 **붙여넣기**를 클릭합니다. 자세한 내용은 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md)를 참조 하십시오.
    
      - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거**를 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.

    
    </div>

17. 원하는 경우 트렁크에 대해 **호출된 번호 변환 규칙**을 연결 및 구성합니다. 변환 규칙은 아웃바운드 통화의 호출된 번호에 적용됩니다.
    
      - Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다. **변환 규칙 선택**에서 트렁크와 연결할 규칙을 클릭한 다음 **확인**을 클릭합니다.
    
      - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기**를 클릭합니다. 새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.
    
      - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시**를 클릭합니다. 자세한 내용은 배포 설명서에서 [Lync Server 2013의 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.
    
      - 기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사**를 클릭한 다음 **붙여넣기**를 클릭합니다. 자세한 내용은 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md)를 참조 하십시오.
    
      - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거**를 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.

    
    </div>

18. 트렁크의 변환 규칙이 올바른 순서로 정렬 되어 있는지 확인 합니다. 목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013는 번역 규칙 목록을 위에서 아래로 이동 하 고 전화 건 번호와 일치 하는 첫 번째 규칙을 사용 합니다. 전화를 건 번호가 둘 이상의 변환 규칙과 일치할 수 있도록 트렁크를 구성하는 경우에는 제약이 많은 규칙이 제약이 적은 규칙보다 위에 정렬되어 있어야 합니다. 예를 들어 모든 11자리 숫자와 일치하는 변환 규칙과 +1425로 시작하는 11자리 숫자와만 일치하는 변환 규칙이 있는 경우 모든 11자리 숫자와 일치하는 규칙이 보다 제한적인 규칙 아래에 정렬되어야 합니다<EM>.</EM>

    
    </div>

19. 트렁크 구성을 마쳤으면 **확인**을 클릭합니다.

20. **트렁크 구성** 페이지에서 **커밋**을 클릭하고 **모두 커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 트렁크 구성을 만들거나 수정할 때는 항상 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.

    
    </div>

트렁크를 구성한 후 배포 설명서에서 [Lync Server 2013의 전역 미디어 바이패스 옵션](lync-server-2013-global-media-bypass-options.md) 에 설명 된 대로 전체 미디어 바이패스 옵션 중 하나를 선택 하 여 미디어 바이패스 구성을 계속 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[Lync Server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013의 글로벌 미디어 바이패스 옵션](lync-server-2013-global-media-bypass-options.md)  


[Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

