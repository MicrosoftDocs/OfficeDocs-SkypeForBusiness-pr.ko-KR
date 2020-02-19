---
title: 'Lync Server 2013: 사용자별 PIN 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 889fbc962654edbd7b6d13523fc5dc43dc426de2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134404"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자별 PIN 정책 할당

 


전화 접속 회의 PIN (개인 식별 번호) 정책은 Lync Server 2013 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.

하나 이상의 사용자별 PIN 정책을 배포 하는 것은 선택 사항입니다. 또한 글로벌 수준 PIN 정책 또는 사이트 수준 PIN 정책만 배포할 수 있습니다. 사용자별 정책을 배포하는 경우에는 해당 정책을 사용자, 그룹 또는 연락처 개체에 명시적으로 할당해야 합니다. 전화 접속 회의에 대 한 Pin 사용에 대 한 사용자 권한 및 사용 권한은 특정 사이트 수준 또는 사용자별 정책이 할당 되지 않은 경우 전역 수준 PIN 정책에 정의 된 대로 자동으로 기본값으로 지정 됩니다.

하나 이상의 사용자별 PIN 정책을 만든 후이 항목의 절차를 사용 하 여 서버에서 특정 사용자가 만들고 사용 하는 Pin에 대해 설정할 제약 조건을 지정 하는 정책을 할당 합니다.

사용자별 전화 접속 회의 PIN 정책을 만드는 방법에 대 한 자세한 내용은 [사이트 또는 사용자 그룹에 대해 Lync Server 2013에서 전화 접속 회의 pin 설정 만들기 또는 수정을](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)참조 하십시오.

## <a name="to-assign-a-per-user-pin-policy"></a>사용자별 PIN 정책을 할당 하려면

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
        

        > [!TIP]  
        > 쿼리에 검색 절을 더 추가하려면 <STRONG>필터 추가</STRONG>를 클릭합니다.

    
    5.  **찾기**를 클릭합니다.

6.  검색 결과에서 사용자를 클릭하고 **동작**을 클릭한 후에 **정책 할당**을 클릭합니다.
    

    > [!TIP]  
    > 여러 사용자에 게 동일한 사용자별 PIN 정책을 적용 하려면 검색 결과에서 여러 사용자를 선택 하 고 <STRONG>동작</STRONG>을 클릭 한 후에 <STRONG>정책 할당</STRONG>을 클릭 합니다.



7.  **정책 할당**의 **PIN 정책**에서 다음 중 하나를 수행 합니다.
    

    > [!NOTE]  
    > <STRONG>정책 할당</STRONG> 대화 <STRONG> &lt;상자를&gt; 사용</STRONG> 하 여 구성할 수 있는 정책이 여러 개 있으므로 대화 상자의 모든 정책에 대해 다음 사용자가 기본적으로 선택 됩니다. 이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.

    
      - Lync Server 2013에서 전역 수준 정책을 자동으로 선택 하도록 허용 하거나, 정의 된 경우 사이트 수준 정책을 사용 합니다.
    
      - **PIN 정책** 페이지에서 이전에 정의한 사용자별 PIN 정책의 이름을 클릭 합니다.
        

        > [!TIP]  
        > 지정할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후 <STRONG>보기</STRONG>를 클릭하여 정책에 정의된 사용자 권한 및 권한을 확인합니다.



8.  작업을 마치면 **확인**을 클릭합니다.

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자별 PIN 정책 할당

Windows PowerShell 및 **get-cspinpolicy** cmdlet을 사용 하 여 사용자별 PIN 정책을 할당할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>단일 사용자에 게 사용자별 PIN 정책을 할당 하려면

  - 다음 명령은 사용자 Ken Myer에 게 사용자별 PIN 정책 Redmondpinpolicy가 포함를 할당 합니다.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>여러 사용자에 게 사용자별 PIN 정책을 할당 하려면

  - 다음 명령은 Redmond의 도시에서 근무 하는 모든 사용자에 게 사용자별 PIN 정책 RedmondUsersPinPolicy를 할당 합니다. 이 명령에서 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))를 참조 하십시오.
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a>사용자별 PIN 정책을 할당 해제 하려면

  - 다음 명령은 이전에 Ken Myer에 할당 된 사용자별 PIN 정책을 할당 해제 합니다. 사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

자세한 내용은 [Grant-get-cspinpolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\))를 참조 하십시오.

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 새 PIN 정책 만들기](lync-server-2013-create-a-new-pin-policy.md)  


[Lync Server 2013에서 사용자별 정책 할당](lync-server-2013-assigning-per-user-policies.md)

