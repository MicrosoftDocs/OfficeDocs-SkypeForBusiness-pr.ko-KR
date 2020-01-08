---
title: 'Lync Server 2013: 사용자별 영구 채팅 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 081e6724f5df2389a8ef89e83b2df91b49a1b991
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981597"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자별 영구 채팅 정책 할당

 


Lync Server 2013 제어판 또는 Lync Server 2013 Management Shell을 사용 하 여 사용자 단위 영구 채팅 정책을 할당할 수 있습니다. 영구 채팅 서버용 사용자 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 영구 채팅에 대 한 사용자 정책 만들기](lync-server-2013-create-a-user-policy-for-persistent-chat.md)를 참조 하세요.

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 사용자 단위 영구 채팅 정책을 할당 하려면

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
        

        > [!TIP]  
        > 쿼리에 추가 검색 절을 추가 하려면 <STRONG>필터 추가</STRONG>를 클릭 합니다.

    
    5.  **찾기를**클릭 합니다.

6.  검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.
    

    > [!TIP]  
    > 동일한 사용자별 영구 채팅 정책을 여러 사용자에 게 적용 하려면 검색 결과에서 여러 사용자를 선택한 다음 <STRONG>작업</STRONG>을 클릭 하 고 <STRONG>정책 할당</STRONG>을 클릭 합니다.



7.  **정책 할당**의 **영구 채팅 정책**에서 다음 중 하나를 수행 합니다.
    

    > [!NOTE]  
    > <STRONG>정책 할당</STRONG> 대화 상자를 <STRONG> &lt;&gt; </STRONG> 사용 하 여 구성할 수 있는 정책이 여러 개 있기 때문에 대화 상자에 있는 모든 정책에 대해 다음으로 유지 옵션이 기본적으로 선택 되어 있습니다. 이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.

    
      - Lync Server 2013이 전역 수준 정책을 자동으로 선택 하도록 허용 하려면 ** \<자동\> ** 을 선택 하 고, 정의 하면 사이트 수준 정책입니다.
    
      - **영구 채팅 정책** 페이지에 이전에 정의한 사용자 단위 영구 채팅 정책의 이름을 클릭 합니다.
        

        > [!TIP]  
        > 할당 하려는 정책을 결정할 수 있도록 정책 이름을 클릭 한 후 <STRONG>보기</STRONG> 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.



8.  완료 되 면 **확인**을 클릭 합니다.

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자별 영구 채팅 정책 할당

**CsPersistentChatPolicy** cmdlet을 사용 하 여 사용자별 영구 채팅 정책을 할당할 수도 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>단일 사용자에 게 사용자별 영구 채팅 정책을 할당 하려면

  - 다음 명령을 사용 하 여 사용자 단위 영구 채팅 정책 RedmondPersistentChatPolicy: 진구 Myer에 할당 합니다.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>사용자 단위 영구 채팅 정책을 여러 사용자에 게 할당 하려면

  - 이 명령은 사용자 단위 영구 채팅 정책 RedmondUsersPersistentChatPolicy를 IT 부서에 근무 하는 모든 사용자에 게 할당 합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>사용자별 영구 채팅 정책을 할당 취소 하려면

  - 다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 영구 채팅 정책을 할당 해제 합니다. 사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다. 사이트 정책이 전역 정책 보다 우선 합니다.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

자세한 내용은 [CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 영구 채팅에 대한 사용자 정책 만들기](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

