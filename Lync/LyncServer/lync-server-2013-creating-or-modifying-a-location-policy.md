---
title: 'Lync Server 2013: 위치 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eda2410891d19ba777e4aa57879e3ad8e2afb67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Lync Server 2013에서 위치 정책 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

Lync Server 2013에서는 위치 정책을 사용 하 여 E9-1-1 (고급 9-1-1) 기능 및 사용자 또는 연락처의 위치 설정과 관련 된 설정을 적용할 수 있습니다. 위치 정책은 사용자가 E9-1-1을 사용하도록 설정되어 있는지 여부를 확인하고, 설정된 경우 긴급 통화에 대한 동작을 결정합니다. 예를 들어 위치 정책을 사용하여 긴급 통화 번호(예: 한국의 경우 119), 회사 보안 부서에 자동으로 알림을 제공할지 여부 및 통화를 라우팅할 방법을 정의할 수 있습니다.

Lync Server 2013 제어판의 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다. Lync Server 제어판에서 위치 정책을 보거나 만들거나 수정 하거나 삭제할 수 있습니다. 이 섹션의 절차에 따라 위치 정책을 만들거나 수정합니다. 위치 정책을 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 삭제](lync-server-2013-deleting-a-location-policy.md)를 참조 하십시오.

Lync Server 2013에서는 위치 정보 서비스에서 위치 업데이트에 대 한 클라이언트 요청 사이의 기본 시간을 다시 정의할 수 있습니다. 기본값은 4시간입니다. 기본값을 재정의하려면 LocationRefreshInterval 매개 변수를 포함하여 **Set-CsLocationPolicy** cmdlet을 사용합니다.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Lync Server 제어판에서 새 위치 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **위치 정책**을 클릭합니다.

4.  **위치 정책** 페이지에서 **새로 만들기**를 클릭하고 만들려는 정책의 유형을 선택합니다.
    
      - 사이트 정책을 만들려면 **사이트 정책**을 클릭합니다. **사이트 선택**에서 정책을 적용할 사이트를 선택하고 **확인**을 클릭합니다. **새 위치 정책** 페이지의 **범위** 필드에는 **사이트** 값이 있고, **이름** 필드에는 선택한 사이트의 이름이 있습니다. 이러한 필드는 수정할 수 없습니다. 사이트 정책은 지정된 사이트의 모든 사용자에게 자동으로 적용되며 이러한 사용자에 대한 글로벌 정책을 재정의합니다.
    
      - **사용자 정책**을 만들려면 **사용자 정책**을 클릭합니다. **새 위치 정책**의 **범위** 필드에는 **사용자** 값이 있습니다. 이 값은 수정할 수 없습니다. **이름** 필드에 이 정책의 이름을 입력합니다. 사용자 정책은 어떤 사용자에게도 자동으로 적용되지 않습니다. 사용자 정책을 만든 후 정책을 적용할 사용자 또는 네트워크 사이트에 정책을 수동으로 부여해야 합니다.

5.  나머지 필드를 다음과 같이 채웁니다.
    
      - **고급 응급 서비스**   사용 E9-1-1에 대해이 정책과 연결 된 사용자를 사용 하도록 설정 하려면이 확인란을 선택 합니다. 응급 서비스를 사용 하도록 설정 하면 Lync Server 클라이언트에서 등록에 대 한 위치 정보를 검색 하 고 긴급 통화를 수행할 때 해당 정보를 포함 합니다.
    
      - **위치**   다음 값 중 하나를 지정 합니다.
        
          - **필수**   사용자는 클라이언트가 새 위치에서 등록할 때 위치 정보를 입력 하 라는 메시지가 표시 됩니다. 사용자는 정보를 입력하지 않은 상태로 메시지를 취소할 수 있습니다. 정보를 입력 하면 비상 서비스 공급자가 긴급 통화에 응답 하 여 공용 안전 응답 지점 (PSAP) 교환원에 게 라우팅되도록 (즉, 911 교환원) 전에 해당 위치를 확인 합니다.
        
          - **필요 하지 않음**   사용자에 게 위치를 입력 하 라는 메시지가 표시 되지 않습니다. 위치 정보 없이 통화를 수행 하면 응급 서비스 공급자가 통화에 응답 하 고 위치를 요청 합니다.
        
          - **고 지**   사항이 옵션은 사용자가 위치 정보를 입력 하지 않고 메시지를 해제할 수 없다는 점만 제외 하면 **필요한** 경우와 동일 합니다. 사용자는 여전히 긴급 통화를 완료할 수 있지만, 정보를 입력 하지 않으면 다른 전화를 완료할 수 없습니다. 또한 위치 정보 입력에 대 한 거부 결과를 알리는 고 지 사항 텍스트가 사용자에 게 표시 됩니다. 고 지 사항 텍스트를 설정 하려면 Lync Server 관리 셸을 사용 하 여 Microsoft.rtc.management.writableconfig.policy.location.enhancedemergencyservicedisclaimer 유형의 매개 변수를 통해 **설정 된 CsLocationPolicy** Cmdlet 또는 **새-cslocationpolicy** cmdlet을 실행 해야 합니다. 자세한 내용은 Lync Server 관리 셸 설명서에서 [Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 또는 [New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 를 참조 하십시오.
            
            <div>
            

            > [!NOTE]  
            > Lync Server 2013에서는 위치 정책을 사용 하 여 전체 조직에 대 한 전역 고 지만 지정할 수 있는 Lync Server 2010과는 달리, 여러 로캘 또는 다양 한 사용자 집합에 대해 서로 다른 부인를 설정할 수 있습니다.

            
            </div>
    
      - **비상 서비스에 위치 사용**   Lync는 다양 한 이유로 위치 정보를 사용할 수 있습니다 (예: 팀 구성원에 게 현재 위치를 알릴 때). 위치 정보를 긴급 통화에만 사용할 수 있도록 하려면 이 확인란을 선택합니다.
    
      - **Pstn 사용**   이 프로필을 사용 하 여 클라이언트 로부터 긴급 통화를 라우팅하는 데 사용 되는 음성 경로를 결정 하는 데 사용 되는 pstn (공중 전화망) 사용입니다. 이 사용과 연결 된 경로는 긴급 통화 전용 SIP 트렁크 또는 가장 가까운 PSAP (공개 안전 응답 지점)로 긴급 통화를 라우팅하는 비상 위치 Id 번호 (ELIN) 게이트웨이를 가리켜야 합니다.
    
      - **비상 다이얼 번호**   응급 서비스에 연락 하기 위해 전화를 걸 번호입니다. 미국의 경우 이 값은 911입니다. 이 문자열은 0에서 9 사이의 숫자로 구성되어야 하며 1자에서 10자 사이일 수 있습니다.
    
      - **비상 다이얼 마스크**   전화를 걸 때 비상 다이얼 번호 값의 값으로 변환 하려는 숫자입니다. 예를 들어이 필드에 212 값을 입력 하 고 긴급 전화 걸기 번호 필드의 값이 911 이면 사용자가 212 전화를 건 것이 911로 변경 됩니다. 이를 통해 대체 응급 번호에 전화를 걸 수 있으며, 다른 비상 번호로 전화를 걸 수 있는 국가 또는 지역 사용자가 해당 국가나 지역 번호를 사용 하 여 통화를 시도 하는 경우 (예: 현재 거주 하는 국가 또는 지역입니다. 예를 들어 응급 번호가 다른 국가의 사용자가 외국에서 그 나라의 번호 대신 자신의 국가에서 사용되는 번호로 전화를 거는 경우에 유용합니다. 예: 212; 414 문자열의 최대 길이는 100자입니다. 각 문자는 0부터 9까지의 숫자여야 합니다.
        
        <div>
        

        > [!IMPORTANT]  
        > 지정된 전화 마스크 값은 통화 대기 파킹된 통화 번호 범위와 달라야 합니다. 통화 대기 라우팅은 긴급 전화 문자열 변환보다 우선합니다. 기존 통화 대기 파킹된 통화 번호 범위를 보려면 왼쪽 탐색 모음에서 <STRONG>음성 기능</STRONG>을 클릭한 다음 <STRONG>통화 대기</STRONG>를 클릭합니다. 자세한 내용은 <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성을</A>참조 하십시오.

        
        </div>
    
      - **알림 URI**   비상 통화가 발생 했을 때 알릴 하나 이상의 SIP uri (Uniform resource identifier)입니다. 예를 들어 회사의 보안 부서에서 응급 통화가 걸려 올 때마다 메신저 대화를 통해 알림을 받을 수 있습니다. 발신자의 위치를 파악할 수 있는 경우 해당 위치가 알림에 포함됩니다. 여러 SIP Uri를 쉼표로 구분 된 목록으로 포함할 수 있습니다. 예를 들어, "sip: security@litwareinc .com", "sip: kmyer@litwareinc .com" 등이 있습니다. 메일 그룹을 지원 합니다. 문자열의 길이는 1에서 256 자 사이 여야 하며 접두사 "sip:"로 시작 해야 합니다. 알림 URI 필드를 클릭 하기 전에 예제가 표시 됩니다.
    
      - **전화 회의 uri**   SIP uri (이 경우에는 비상 통화에 정책을 지 원하는 타사의 전화 번호)입니다. 예를 들어 **전화 회의 모드** 필드에 제공 된 값에 따라 전화를 통해 전화를 걸거나이 통화에 참가할 때 회사 보안 office에서 전화를 받을 수 있습니다. 이 문자열은 1자에서 256자 사이여야 하며 접두사 sip:로 시작해야 합니다. 이 필드의 내부를 클릭할 때까지 예가 표시 됩니다.
    
      - **전화 회의 모드**    **전화 회의 URI** 필드에 값을 지정 하는 경우 **전화 회의 모드** 에서 타사가 통화에 참가할 수 있는지 또는 수신 대기만 하도록 할지를 결정 합니다. 다음 옵션 중 하나를 지정 합니다.
        
          - **단방향**제 3 자가 발신자와 psap 교환원을 통해서만 대화를 수신할 수 있습니다.   
        
          - **양방향**제 3 자가 발신자와 psap 교환원 간의 전화를 듣고 통화에 참가할 수 있습니다.   

6.  **커밋**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 사용자 정책을 만든 경우 처음에는 이 정책이 사용자 또는 네트워크 사이트에 적용되지 않습니다. 정책을 사용자에게 적용하려면 왼쪽 탐색 모음에서 <STRONG>사용자</STRONG>를 클릭합니다. 그런 다음 정책을 적용할 사용자를 찾습니다. <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG>를 클릭합니다. <STRONG>Lync Server 사용자 편집</STRONG> 페이지의 <STRONG>위치 정책</STRONG> 드롭다운 목록에서 새 위치 정책을 선택한 다음 <STRONG>커밋</STRONG>을 클릭합니다.<BR>정책을 네트워크 사이트에 적용하려면 왼쪽 탐색 모음에서 <STRONG>네트워크 구성</STRONG>을 클릭한 다음 <STRONG>사이트</STRONG>를 클릭합니다. 그런 다음 정책을 적용할 네트워크 사이트를 찾습니다. <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG>를 클릭합니다. <STRONG>사이트 편집</STRONG>의 <STRONG>위치 정책</STRONG> 드롭다운 목록에서 새 위치 정책을 선택한 다음 <STRONG>커밋</STRONG>을 클릭합니다.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Lync Server 제어판에서 위치 정책을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **위치 정책**을 클릭합니다.

4.  **위치 정책** 페이지에서 수정할 위치 정책을 선택합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.

6.  **위치 정책 편집** 페이지에서 필요에 따라 필드를 수정합니다. 자세한 내용은 이 항목의 앞부분에 설명된 "새 위치 정책을 만들려면" 절차의 5단계를 참조하십시오.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 위치 정책 삭제](lync-server-2013-deleting-a-location-policy.md)  


[Lync Server 2013에 대 한 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)  


[Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

