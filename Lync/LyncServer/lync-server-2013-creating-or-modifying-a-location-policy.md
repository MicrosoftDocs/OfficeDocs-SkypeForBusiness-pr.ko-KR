---
title: 'Lync Server 2013: 위치 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173cfd6ce158a089e03a9eded12c3c6920183463
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Lync Server 2013에서 위치 정책 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Lync Server 2013에서 위치 정책을 사용 하 여 향상 된 9-1-1 (E9--1) 기능 및 사용자 또는 연락처에 대 한 위치 설정에 관련 있는 설정을 적용할 수 있습니다. 위치 정책은 사용자가 E9을 사용할 수 있는지 여부를 결정 합니다 (예를 들어, 긴급 통화의 경우). 예를 들어 위치 정책을 사용 하 여 전화 통화를 구성 하는 번호 (예: 미국 내 911), 회사 보안에서 자동으로 알릴 지 여부, 통화를 라우팅하는 방법 등을 정의할 수 있습니다.

Lync Server 2013 제어판의 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다. Lync Server 제어판에서 위치 정책을 보고, 만들고, 수정 하 고, 삭제할 수 있습니다. 이 섹션의 절차를 사용 하 여 위치 정책을 만들거나 수정 합니다. 위치 정책 삭제에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 삭제](lync-server-2013-deleting-a-location-policy.md)를 참조 하세요.

Lync Server 2013에서 위치 정보 서비스에서 위치 업데이트에 대 한 클라이언트 요청 사이의 기본 시간 간격을 무시할 수 있습니다. 기본값은 4 시간입니다. LocationRefreshInterval 매개 변수와 함께 **Set-CsLocationPolicy** cmdlet을 사용 하 여 기본값을 재정의 합니다.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Lync Server 제어판에서 새 위치 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **위치 정책을**클릭 합니다.

4.  **위치 정책** 페이지에서 **새로 만들기** 를 클릭 하 고 만들려는 정책 유형을 선택 합니다.
    
      - 사이트 정책을 만들려면 **사이트 정책을**클릭 합니다. **사이트 선택**에서 정책을 적용 하려는 사이트를 선택 하 고 **확인**을 클릭 합니다. **새 위치 정책** 페이지의 **범위** 필드에는 값 **사이트가**포함 되며, **이름** 필드에는 사용자가 선택한 사이트의 이름이 표시 됩니다. 이러한 필드는 수정할 수 없습니다. 사이트 정책은 지정 된 사이트의 모든 사용자에 게 자동으로 적용 되며 해당 사용자에 대 한 전역 정책 보다 우선 합니다.
    
      - **사용자 정책을**만들려면 **사용자 정책을**클릭 합니다. **새 위치 정책**에서 **범위** 필드에는 값 **사용자가**포함 됩니다. 이 값을 수정할 수 없습니다. **이름** 필드에이 정책에 지정할 이름을 입력 합니다. 사용자 정책은 사용자에 게 자동으로 적용 되지 않습니다. 사용자 정책을 만든 후에는 정책을 적용 하려는 사용자 또는 네트워크 사이트에 정책을 수동으로 부여 해야 합니다.

5.  나머지 필드를 다음과 같이 입력 합니다.
    
      - **향상 된 응급 서비스**   사용 E9에 대해이 정책에 연결 되는 사용자를 사용 하려면이 확인란을 선택 합니다-1-1입니다. 응급 서비스를 사용 하도록 설정 하면 Lync Server 클라이언트에서 등록에 대 한 위치 정보를 검색 하 고 비상 통화가 이루어지면 해당 정보를 포함 합니다.
    
      - **위치**   다음 값 중 하나를 지정 합니다.
        
          - **필수**   사용자는 클라이언트가 새 위치에 등록할 때 위치 정보를 입력 하 라는 메시지가 표시 됩니다. 사용자는 정보를 입력 하지 않고 메시지를 닫을 수 있습니다. 정보를 입력 하는 경우 비상 서비스 공급자가 긴급 통화에 먼저 응답 하 여 공용 안전 응답 시점 (PSAP) 교환원 (즉, 911 연산자)에 라우팅되지 않기 전에 위치를 확인 합니다.
        
          - **필요 하지 않음**   사용자에 게 위치를 묻는 메시지가 표시 되지 않습니다. 위치 정보 없이 통화가 이루어지면 비상 서비스 공급자가 전화에 응답 하 고 위치를 요청 합니다.
        
          - **고 지**   사항이 옵션은 사용자가 위치 정보를 입력 하지 않고 메시지를 해제할 수 없다는 점을 제외 하 고 **필요한** 경우와 동일 합니다. 사용자는 계속 해 서 비상 전화를 받을 수 있지만, 정보를 입력 하지 않고 다른 전화를 완료할 수 없습니다. 또한 사용자에 게 위치 정보 입력에 대해 거절 하는 결과를 알릴 수 있는 고 지 사항 텍스트가 표시 됩니다. 고 지 사항 텍스트를 설정 하려면 Lync Server Management Shell을 사용 하 여 EnhancedEmergencyServiceDisclaimer 매개 변수를 사용 하 여 **Set CsLocationPolicy** Cmdlet 또는 **새-cslocationpolicy** cmdlet을 실행 해야 합니다. 자세한 내용은 Lync Server 관리 셸 설명서의 [Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 또는 [새-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 를 참조 하세요.
            
            <div>
            

            > [!NOTE]  
            > Lync Server 2013에서 위치 정책을 사용 하 여 전체 조직에 대 한 전역 부인만 지정할 수 있는 Lync Server 2010와는 달리 다양 한 로캘 또는 다른 사용자 집합에 대해 다른 법적 고 지를 설정할 수 있습니다.

            
            </div>
    
      - **응급 서비스에 대 한 위치 사용**   Lync는 다양 한 이유로 위치 정보를 사용할 수 있습니다 (예를 들어 팀 구성원을 현재 위치로 알릴 경우). 이 확인란을 선택 하 여 위치 정보를 비상 전화에만 사용할 수 있도록 합니다.
    
      - **Pstn 사용**   이 프로필을 사용 하 여 클라이언트에서 비상 전화를 라우팅하는 데 사용할 음성 경로를 결정 하는 데 사용 되는 pstn (공개 통신 네트워크) 사용입니다. 이 사용과 관련 된 경로는 비상 전화 전용 SIP 트렁크 또는 가까운 공공 안전 응답 시점 (PSAP)으로 긴급 통화를 라우팅하는 비상 위치 Id 번호 (ELIN) 게이트웨이를 가리켜야 합니다.
    
      - **비상 전화 번호**   비상 서비스에 연결 하기 위해 거는 번호입니다. 미국에서이 값은 911입니다. 문자열은 0 ~ 9의 숫자 이며 1 ~ 10 자리 길이의 숫자로 구성 되어야 합니다.
    
      - **비상 다이얼 마스크**   전화를 걸 때 비상 다이얼 번호 값으로 번역 하려는 번호입니다. 예를 들어이 필드에 212의 값을 입력 하 고 긴급 전화 걸기 번호 필드에 911 값이 있으면 사용자가 212에 전화를 거는 경우 911로 통화를 요청 하 게 됩니다. 이렇게 하면 대체 긴급 번호로 전화를 걸 수 있으며, 다른 비상 번호로 전화를 걸 수 있는 국가 또는 지역 사용자가 해당 국가나 지역 번호를 사용 하는 경우, 예를 들어 현재 거주 하 고 있는 국가 또는 지역입니다. 세미콜론으로 값을 구분 하 여 여러 응급 전화 접속 마스크를 정의할 수 있습니다. 예를 들어 212; 414. 문자열의 최대 길이는 100 자입니다. 각 문자는 0 ~ 9의 숫자 여야 합니다.
        
        <div>
        

        > [!IMPORTANT]  
        > 지정 된 다이얼 마스크 값이 통화 공원 범위에 있는 숫자와 같지 않은지 확인 합니다. 통화 대기 라우팅에 따라 긴급 다이얼 문자열 변환이 우선권을 갖습니다. 기존 통화 공원 궤도 범위를 보려면 왼쪽 탐색 모음에서 <STRONG>음성 기능</STRONG> 을 클릭 한 다음 <STRONG>통화</STRONG>대기를 클릭 합니다. 자세한 내용은 <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Lync Server 2013에서 파킹 전화 내선 번호 구성을</A>참조 하세요.

        
        </div>
    
      - ****   긴급 통화가 이루어질 때 알림을 받을 하나 이상의 SIP uri (Uniform resource identifier)입니다. 예를 들어, 긴급 통화가 발생할 때마다 회사 보안 office에 인스턴트 메시지를 보낼 수 있습니다. 호출자의 위치를 사용할 수 있는 경우 해당 위치가 알림에 포함 됩니다. 여러 SIP Uri를 쉼표로 구분 된 목록으로 포함할 수 있습니다. 예를 들어 "sip: security@litwareinc .com", "sip: kmyer@litwareinc .com"이 있습니다. 메일 그룹이 지원 됩니다. 문자열의 길이는 1 ~ 256 자 여야 하며 "sip:" 접두사로 시작 해야 합니다. 알림 URI 필드를 클릭 하기 전에 예제가 표시 됩니다.
    
      - **전화 회의 uri**   SIP uri (이 경우에는 비상 통화를 conferenced는 타사의 전화 번호) 예를 들어 회사 보안 office에서 긴급 통화를 할 때 전화를 걸거나 해당 통화에 참가할 수 있습니다 ( **컨퍼런스 모드** 필드에 제공 되는 값에 따라 다름). 문자열의 길이는 1 ~ 256 자 여야 하며 sip: 라는 접두사로 시작 해야 합니다. 이 필드의 내부를 클릭할 때까지 예가 표시 됩니다.
    
      - **회의 모드**    **전화 회의 URI** 필드에 값을 지정 하면 **회의 모드** 에서 타사가 통화에 참가할 수 있는지 또는 수신만 할 수 있는 경우를 결정 합니다. 다음 옵션 중 하나를 지정 합니다.
        
          - ****   제 3 자는 호출자와 psap 연산자 간의 대화만 수신할 수 있는 단방향입니다.
        
          - ****   제 3 자는 호출자와 psap 연산자 간의 통화를 수신 대기 하 고이에 참여할 수 있는 양방향입니다.

6.  **커밋**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 사용자 정책을 만들면 처음에는 해당 정책이 사용자 또는 네트워크 사이트에 적용 되지 않습니다. 사용자에 게 정책을 적용 하려면 왼쪽 탐색 모음에서 <STRONG>사용자</STRONG> 를 클릭 합니다. 정책을 적용 하려는 사용자를 찾습니다. <STRONG>편집</STRONG> 메뉴에서 <STRONG>세부 정보 표시</STRONG>를 클릭 합니다. <STRONG>Lync Server 사용자 편집</STRONG> 페이지의 <STRONG>위치 정책</STRONG> 드롭다운 목록에서 새 위치 정책을 선택한 다음 <STRONG>커밋을</STRONG>클릭 합니다.<BR>네트워크 사이트에 정책을 적용 하려면 왼쪽 탐색 모음에서 <STRONG>네트워크 구성을</STRONG> 클릭 한 다음 <STRONG>사이트</STRONG>를 클릭 합니다. 정책을 적용 하려는 네트워크 사이트를 찾습니다. <STRONG>편집</STRONG> 메뉴에서 <STRONG>세부 정보 표시</STRONG>를 클릭 합니다. <STRONG>사이트 편집</STRONG>의 <STRONG>위치 정책</STRONG> 드롭다운 목록에서 새 위치 정책을 선택한 다음 <STRONG>커밋을</STRONG>클릭 합니다.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Lync Server 제어판에서 위치 정책을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **위치 정책을**클릭 합니다.

4.  **위치 정책** 페이지에서 수정 하려는 위치 정책을 선택 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **위치 편집 정책** 페이지에서 필요에 따라 필드를 수정 합니다 (자세한 내용은이 항목의 앞부분에 나오는 "새 위치 정책 만들기" 절차의 5 단계 참조).

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 위치 정책 삭제](lync-server-2013-deleting-a-location-policy.md)  


[Lync Server 2013의 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)  


[Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

