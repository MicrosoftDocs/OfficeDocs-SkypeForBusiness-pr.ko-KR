---
title: 'Lync Server 2013: 사용자 PIN 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb3d854f68e9e22e8d8fb1fa0d26f555f09af1ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Lync Server 2013에서 사용자 PIN 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

전화 접속 회의에 인증 된 사용자로 참가 하려면 AD DS (Active Directory 도메인 서비스) 자격 증명을 사용 하는 Lync Server 2013 사용자에 게 PIN (개인 식별 번호)이 필요 합니다. Lync Server 2013 제어판에서 사용자의 PIN 정보를 볼 수 있습니다.

<div>


> [!NOTE]  
> 핀이 설정 되었는지 또는 핀이 마지막으로 변경 된 시점 등의 PIN 상태 정보를 볼 수 있지만 PIN 상태에서 현재 PIN이 표시 되지 않습니다. 사용자가 PIN을 잃어버린 경우 <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정</A> 의 절차에 따라 다시 설정할 수 있습니다.



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>Lync Server 제어판에서 사용자의 PIN을 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.
    
      - 사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.
    
      - 저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.

5.  ) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.
    
    1.  **필터 추가**를 클릭 합니다.
    
    2.  사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.
    
    3.  다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.
    
    4.  선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.
        
        <div>
        

        > [!TIP]  
        > 쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.

        
        </div>
    
    5.  **찾기를**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > PIN이 잠겨 있으면 PIN을 설정 하기 전에 잠금을 해제 해야 합니다. PIN의 잠금을 해제 하려면 사용자를 클릭 하 고 <STRONG>동작</STRONG>을 클릭 한 다음 <STRONG>pin 잠금 해제</STRONG>를 클릭 합니다.

    
    </div>

6.  검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **핀 상태 보기**를 클릭 합니다.

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 사용자 PIN 정보 보기

Get-CsClientPinInfo cmdlet을 사용 하 여 사용자 PIN 정보를 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-user-pin-information"></a>사용자 PIN 정보를 보려면

  - 사용자의 PIN 정보를 보려면 Lync Server 관리 셸에서 다음과 유사한 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) 을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Lync Server 2013에서 사용자 PIN 잠금 또는 잠금 해제](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

