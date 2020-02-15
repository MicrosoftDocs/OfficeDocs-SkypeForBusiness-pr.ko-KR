---
title: 'Lync Server 2013: 사용자별 위치 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec78fd434706ec3e1c5f28c256b38a5f4463ac7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044030"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자별 위치 정책 할당

 


위치 정책은 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.

필요한 경우 하나 이상의 사용자별 위치 정책을 배포할 수 있습니다. 또한 전역 수준 위치 정책이나 서브넷 수준 위치 정책을 배포할 수도 있습니다. 사용자별 정책을 배포하는 경우에는 해당 정책을 사용자, 그룹 또는 연락처 개체에 명시적으로 할당해야 합니다. 특정 서브넷 수준 또는 사용자별 정책이 할당되지 않으면 E9-1-1(고급 9-1-1) 설정은 전역 수준 위치 정책에 정의된 값을 자동으로 기본 사용합니다.

사용자별 위치 정책을 하나 이상 만든 후에는 이 항목의 절차에 따라 특정 사용자가 거는 긴급 통화에 대해 서버에서 적용하도록 할 설정을 지정하는 정책에 할당합니다.

사용 가능한 모든 위치 정책 설정 목록은 [Lync Server 2013에 대 한 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)를 참조 하십시오.

위치 정책 만들기에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 만들기](lync-server-2013-create-location-policies.md)를 참조 하세요.

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 사용자별 위치 정책을 할당 하려면

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
    > 동일한 사용자별 위치 정책을 여러 사용자에게 적용하려면 검색 결과에서 원하는 사용자를 모두 선택하고 <STRONG>동작</STRONG>을 클릭한 후에 <STRONG>정책 할당</STRONG>을 클릭합니다.



7.  **정책 할당**의 **위치 정책**에서 다음 중 하나를 수행합니다.
    

    > [!NOTE]  
    > <STRONG>정책 할당</STRONG> 대화 <STRONG> &lt;상자를&gt; 사용</STRONG> 하 여 구성할 수 있는 정책이 여러 개 있으므로 대화 상자의 모든 정책에 대해 다음 사용자가 기본적으로 선택 됩니다. 이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.

    
      - Lync Server 2013에서 글로벌 수준 정책을 자동으로 선택 하도록 허용 하거나, 정의 된 경우 서브넷 수준 정책
    
      - **New-CsLocationPolicy** cmdlet을 실행하여 이전에 정의한 사용자별 위치 정책의 이름을 클릭합니다.
        

        > [!TIP]  
        > 할당할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후에 <STRONG>보기</STRONG>를 클릭하여 해당 정책에 정의된 사용자 권한을 봅니다.



8.  작업을 마쳤으면 **확인**을 클릭합니다.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Lync Server 관리 셸 Cmdlet을 사용 하 여 사용자별 위치 정책 할당

Grant-CsLocationPolicy cmdlet을 사용 하 여 사용자별 위치 정책을 할당할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>단일 사용자에 대해 사용자별 위치 정책을 할당하려면

  - 다음 명령은 사용자 Ken Myer에게 사용자별 위치 정책 RedmondLocationPolicy를 할당합니다.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>여러 사용자에 대해 사용자별 위치 정책을 할당하려면

  - 다음 명령은 Accounting 부서에서 근무하는 모든 사용자에 대해 사용자별 위치 정책 AccountingDepartmentLocationPolicy를 할당합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [csuser, user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하십시오.
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>사용자별 위치 정책 할당을 취소하려면

  - 다음 명령은 이전에 Ken Myer에게 할당된 사용자별 위치 정책의 할당을 취소합니다. 사용자별 정책 할당을 취소하면 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용하여 관리됩니다. 사이트 정책이 글로벌 정책보다 우선합니다.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

자세한 내용은 [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

