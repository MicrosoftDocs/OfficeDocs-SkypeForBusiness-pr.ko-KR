---
title: 'Lync Server 2013: 사용자 PIN 잠금 또는 잠금 해제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c89923d2bd130806d84ae945720fc23d700e9f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a>Lync Server 2013에서 사용자 PIN 잠금 또는 잠금 해제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Lync Server 2013 제어판의 **사용자** 섹션에서 사용자의 PIN을 잠그거나 잠금을 해제할 수 있습니다.

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a>Lync Server 제어판에서 사용자의 PIN을 잠그려면

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
    
    6.  사용자를 클릭 하 고 **동작**을 클릭 한 다음 **핀**고정을 클릭 합니다.

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a>Lync Server 제어판에서 사용자의 PIN을 잠금 해제 하려면

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
    
    6.  사용자를 클릭 하 고 **작업**을 클릭 한 다음 **PIN 잠금 해제**를 클릭 합니다.

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 Pin 잠금 및 잠금 해제

Windows PowerShell 및 잠금-csclientpin cmdlet을 사용 하 여 사용자 Pin을 잠그고 잠금을 해제할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 이러한 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-lock-a-user-pin"></a>사용자 PIN을 잠그려면

  - 사용자의 PIN을 잠그려면 Lock-CsClientPin cmdlet을 사용 합니다. 예를 들면 다음과 같습니다.
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a>사용자 PIN의 잠금을 해제 하려면

  - 사용자 PIN의 잠금을 해제 하려면 잠금 해제-CsClientPin cmdlet을 사용 합니다. 예를 들면 다음과 같습니다.
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

자세한 내용은 [잠금 csclientpin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) 및 [잠금 해제-csclientpin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

