---
title: 'Lync Server 2013: 사용자를 다른 풀로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Lync Server 2013에서 다른 풀로 사용자 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2018-02-09_

Lync Server 제어판을 사용 하 여 특정 서버나 풀에 사용자를 할당할 수 있습니다.

<div>


> [!TIP]  
> Lync Server 2010 이전 버전을 실행 하는 원본 풀의 모든 기존 사용자를 복잡 한 Active Directory 환경에서 Lync Server 2013 대상 풀로 이동 하면 Active Directory 복제 속도가 느려질 수 있습니다. 이를 방지 하려면 검색 필터를 사용 하 여 Lync Server 2010 이전 버전을 실행 하는 풀에서 사용자를 개별적으로 이동 하거나 Lync Server Management Shell을 사용 하 여 사용자를 cmdlet으로 이동할 수 있습니다. 또한 필터 기능은 Lync Server 2013 사용자에 게 작동 합니다.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>선택한 사용자를 다른 서버 또는 풀로 이동 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.

5.  표에서 특정 사용자 또는 목록에서 사용자를 선택 합니다.

6.  **작업** 메뉴에서 **선택한 사용자 이동을 클릭 하 여 그룹으로 이동**합니다.

7.  **사용자 이동**에서 **대상 등록자 풀**로 사용자를 이동 하려는 풀을 선택 합니다.

8.  ) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.
    
    <div>
    

    > [!Caution]  
    > <STRONG>Force (강제</STRONG>)를 선택 하면 사용자 계정이 이동 되지만, 예약 된 컨퍼런스 및 연락처와 같은 관련 사용자 데이터는 이동 되지 않습니다.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>한 서버 또는 풀의 모든 사용자를 다른 서버 또는 풀로 이동 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **작업** 메뉴에서 **모든 사용자를 풀로 이동을**클릭 합니다.

5.  **사용자 이동**에서 **원본 등록자 풀**에서 이동 하려는 사용자 계정이 포함 된 풀을 선택 합니다.

6.  **대상 등록자 풀**에서 사용자를 이동 하려는 풀을 선택 합니다.

7.  ) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.
    
    <div>
    

    > [!Caution]  
    > <STRONG>Force (강제</STRONG>)를 선택 하면 사용자 계정이 이동 되지만, 예약 된 컨퍼런스 및 연락처와 같은 관련 사용자 데이터는 이동 되지 않습니다.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>필터를 사용 하 여 한 풀에서 다른 풀로 사용자를 이동 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색**에서 **검색**을 클릭 한 다음 **필터 추가**를 클릭 합니다.

5.  검색 조건에서 **등록자 그룹**을 선택 하 고 **같음**, **현재 풀 FQDN**을 차례로 선택한 다음 **찾기를**클릭 합니다.

6.  **작업** 메뉴에서 **모든 사용자를 풀로 이동을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 기존 사용자 집합에 필터가 적용 되는 경우 <STRONG>모든 사용자를 풀로 이동 하</STRONG> 는 옵션이 사용자의 필터링 된 하위 집합에 해당 하는 것이 아니라 <STRONG><EM>모든 사용자가 사용할 수</EM></STRONG> 있습니다.

    
    </div>

7.  **사용자 이동**에서 **원본 등록자 풀**에서 이동 하려는 사용자 계정이 포함 된 풀을 선택 합니다.

8.  **대상 등록자 풀**에서 사용자를 이동 하려는 풀을 선택 합니다.

9.  ) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.
    
    <div>
    

    > [!Caution]  
    > <STRONG>Force (강제</STRONG>)를 선택 하면 사용자 계정이 이동 되지만, 예약 된 컨퍼런스 및 연락처와 같은 관련 사용자 데이터는 이동 되지 않습니다.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 한 풀에서 다른 그룹으로 사용자 이동

1.  Windows PowerShell 명령 (로컬 또는 원격)을 실행 하는 방법에 따라 아래와 같이 올바른 Lync Server 2013 관리 역할의 구성원으로 로그온 해야 합니다.
    
    1.  로컬 컴퓨터에서 명령을 실행 하는 경우 (예: 프런트 엔드 서버에 직접 로그온 하는 경우), Lync Server Management 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.
    
    2.  다른 컴퓨터에서 원격으로 명령을 실행 하는 경우 (예: 컴퓨터에 로그온 하 고 표준 Edition 프런트 엔드 서버에서 원격으로 명령을 실행 하는 경우) 다음을 수행 합니다. CsUserAdministrator 역할 또는 CsAdministrator에 할당 된 사용자 계정에서 역할을 설정 하 고 내부 배포의 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  단일 사용자를 이동 하려면 다음과 같이 Move-CsUser cmdlet을 사용 합니다.
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    이동할 사용자가 사용자 Pilar Ackerman이 고 사용자가 현재 할당 된 홈 풀에서 pool pool01.contoso.net 이동 합니다.

4.  많은 수의 사용자를 이동 하려면 **Get-csuser** cmdlet을 사용 하 여 필터를 사용 하 고 사용자의 결과 집합을 **이동-csuser**에 전달 합니다.
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    **Get csuser** 및 **Move csuser** 의 결합 된 명령은 다음과 같이 표시 될 것입니다.
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 사용자 계정 속성 수정](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

