---
title: 'Lync Server 2013: 사용자의 전화 접속 회의 PIN 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258c6e5da1dc5b78d53bbc3779d50890935d7b58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-10_

전화 접속 회의에 인증 된 사용자로 참가 하려면 AD DS (Active Directory 도메인 서비스) 자격 증명을 사용 하는 Lync Server 2013 사용자에 게 PIN (개인 식별 번호)이 필요 합니다. 사용자가 전화 접속 회의 PIN을 잊어버린 경우 또는 Lync Server를 사용 하 여 PIN을 설정 하지 않은 경우 Lync Server 제어판에서 사용자의 PIN을 설정할 수 있습니다. 자동으로 PIN을 생성 하거나 수동으로 새로 만들 수 있습니다.

<div>


> [!NOTE]  
> 최소 길이와 같은 PIN의 특정 특성은 정책으로 구성할 수 있습니다. 전역 정책 외에도 개별 사이트 또는 사용자에 대 한 PIN 정책을 구성할 수 있습니다. PIN 정책 구성에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성을</A>참조 하세요.



</div>

<div>

## <a name="to-set-a-users-pin"></a>사용자의 PIN을 설정 하려면

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

6.  검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음, **PIN 설정을**클릭 합니다.

7.  **핀 설정** 대화 상자에서 다음 중 하나를 수행 합니다.
    
      - Lync Server 2013에서 사용자 PIN을 생성 하도록 허용 하려면 **자동으로 유효한 PIN** (기본값) 생성을 선택 합니다.
    
      - 고유한 PIN을 만들려면 **수동으로 특정 pin 입력**을 클릭 하 고 텍스트 상자를 클릭 한 다음 pin 정책 설정에 지정 된 pin 요구 사항에 맞는 pin을 입력 합니다.

8.  **확인**을 클릭합니다.

9.  **SET 핀**에서 다음 중 하나를 수행 합니다.
    
      - Pin **표시** 확인란을 선택 하 여 pin을 표시 한 다음, pin을 복사 하 고 조직의 기본 설정 메서드를 사용 하 여 사용자에 게 통신 합니다.
    
      - **내 전자 메일 응용 프로그램 열기를 클릭 하 여 새 pin을 사용자에 게 보내어** 전자 메일로 pin을 보냅니다. Microsoft Office Outlook이 전자 메일 클라이언트 이면 PIN이 새 전자 메일 메시지에 자동으로 복사 됩니다. 다른 전자 메일 클라이언트를 사용 하는 경우에는 pin **표시** 확인란을 선택 하 여 pin을 표시 한 다음 전자 메일 메시지에 복사 합니다.

10. **닫기를**클릭 합니다.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 PIN 할당

또한 Set CsClientPin cmdlet을 사용 하 여 PIN 번호를 할당할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>사용자에 게 자동으로 PIN 번호 할당

  - 다음 명령은 사용자: 진구 Myer에 PIN 번호를 할당 합니다. Pin 매개 변수는 포함 되지 않기 때문에 Lync Server는 자동으로 PIN 번호를 생성 하 고 할당 합니다.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>특정 PIN 번호를 사용자에 게 할당 하려면

  - 이 명령은 Pin 매개 변수를 사용 하 여 사용자: 진구 Myer에 PIN 번호 121989를 할당 합니다.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

자세한 내용은 [집합 CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[전화 접속 액세스 번호](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))  


[Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

