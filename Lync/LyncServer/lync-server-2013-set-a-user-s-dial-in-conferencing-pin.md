---
title: 'Lync Server 2013: 사용자의 전화 접속 회의 PIN 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c344a848050d53027c094ad549f0285fbae09489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Lync Server 2013에서 사용자의 전화 접속 회의 PIN 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-10_

전화 접속 회의에 인증 된 사용자로 참가 하려면 AD DS (Active Directory 도메인 서비스) 자격 증명을 사용 하는 Lync Server 2013 사용자에 게 PIN (개인 식별 번호)이 필요 합니다. 사용자가 전화 접속 회의 PIN을 잊어버린 경우 Lync Server를 사용 하 여 PIN을 설정 하지 않은 경우 Lync Server 제어판에서 사용자의 PIN을 설정할 수 있습니다. PIN은 자동으로 생성할 수도 있고 수동으로 만들 수도 있습니다.

<div>


> [!NOTE]  
> 최소 길이와 같은 PIN의 특정 특성을 정책으로 구성할 수 있습니다. 글로벌 정책뿐 아니라, 개별 사이트 또는 사용자에 대한 PIN 정책도 구성할 수 있습니다. PIN 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성을</A>참조 하십시오.



</div>

<div>

## <a name="to-set-a-users-pin"></a>사용자 PIN을 설정하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭합니다.

4.  다음 방법 중 하나를 통해 사용자를 찾습니다.
    
      - **사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기**를 클릭합니다.
    
      - 저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기**를 클릭합니다.

5.  (선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.
    
    1.  **필터 추가**를 클릭합니다.
    
    2.  사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.
    
    3.  **같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.
    
    4.  선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.
        
        <div>
        

        > [!TIP]  
        > 쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.

        
        </div>
    
    5.  **찾기**를 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > PIN이 잠겨 있는 경우에는 PIN 잠금을 해제해야 설정할 수 있습니다. PIN 잠금을 해제하려면 사용자를 클릭하고 <STRONG>동작</STRONG>을 클릭한 후에 <STRONG>PIN 잠금 해제</STRONG>를 클릭합니다.

    
    </div>

6.  검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후에 **PIN 설정**을 클릭합니다.

7.  **PIN 설정** 대화 상자에서 다음 중 하나를 수행합니다.
    
      - Lync Server 2013에서 사용자의 PIN을 생성 하도록 하려면 **자동으로 올바른 PIN 생성** (기본값)을 선택 합니다.
    
      - PIN을 직접 만들려면 **특정 PIN을 수동으로 입력**을 클릭하고 텍스트 상자를 클릭한 후에 PIN 정책 설정에 지정된 PIN 요구 사항을 충족하는 PIN을 입력합니다.

8.  **확인**을 클릭합니다.

9.  **PIN 설정**에서 다음 중 하나를 수행합니다.
    
      - **PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 PIN을 복사하여 조직에서 사용하는 기본 방법을 통해 사용자에게 전달합니다.
    
      - PIN을 전자 메일로 보내려면 **내 전자 메일 응용 프로그램을 열어 새 PIN을 사용자에게 보내기**를 클릭합니다. Microsoft Office Outlook이 전자 메일 클라이언트인 경우 PIN이 새 전자 메일 메시지에 자동으로 복사됩니다. 다른 전자 메일 클라이언트를 사용하는 경우에는 **PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 전자 메일 메시지에 PIN을 복사합니다.

10. **닫기**를 클릭합니다.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 PIN 할당

또한 CsClientPin cmdlet을 사용 하 여 PIN 번호를 할당할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>사용자에 게 PIN 번호를 자동으로 할당 하려면

  - 다음 명령은 Myer라는 사용자에게 PIN 번호를 지정합니다. Pin 매개 변수는 포함 되지 않으므로 Lync Server에서는 PIN 번호를 자동으로 생성 및 할당 합니다.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>사용자에 게 특정 PIN 번호를 할당 하려면

  - 이 명령은 Pin 매개 변수를 사용해서 Ken Myer라는 사용자에게 PIN 번호 121989를 지정합니다.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

자세한 내용은 [CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[전화 접속 액세스 번호](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

