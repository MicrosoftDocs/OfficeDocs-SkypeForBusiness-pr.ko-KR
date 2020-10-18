---
title: 'Lync Server 2013: 전화 접속 회의 액세스 번호 만들기 또는 수정'
description: 'Lync Server 2013: 전화 접속 회의 액세스 번호를 만들거나 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187361ab839fe2f80fda7cb68285c8f36398f5a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577964"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속 회의 액세스 번호 만들기 또는 수정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

전화 접속 회의 액세스 번호를 만들거나 수정 하려면 다음 단계를 수행 합니다.

<div>


> [!IMPORTANT]  
> 새 전화 접속 액세스 번호를 만들기 전에 새 전화 접속 액세스 번호와 연결 된 다이얼 플랜에 전화 접속 회의 지역을 설정 해야 합니다. 여러 다이얼 플랜에서 같은 지역을 사용할 수 있습니다.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>전화 접속 액세스 번호를 만들거나 수정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **회의**를 클릭한 다음 **전화 접속 액세스 번호**를 클릭합니다.

4.  **전화 접속 액세스 번호** 페이지에서 다음 중 하나를 수행 합니다.
    
      - **새로 만들기** 를 클릭 하 여 **새 전화 접속 액세스 번호**를 엽니다.
    
      - 목록에서 전화 접속 액세스 번호 중 하나를 클릭 하 고 **편집**을 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.
        
        <div>
        

        > [!NOTE]  
        > 검색 필드를 사용 하 여 전화 접속 액세스 번호 목록에서 열의 내용을 검색 하면 예상 했던 결과가 나오지 않을 수 있습니다. 대신 관심 있는 열을 기준으로 목록을 정렬 하 여 보거나 변경 하려는 전화 접속 액세스 번호를 식별 합니다.

        
        </div>

5.  **표시 번호**에 공중 전화망 (PSTN) 전화 사용자가 회의에 참가 하기 위해 전화를 걸 수 있는 전화 번호를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.

    
    </div>

6.  **표시 이름**에 전화 접속 액세스 번호에 대 한 설명을 입력 합니다. 이 이름은 Lync 검색 결과에서 전화 접속 액세스 번호와 연결 된 이름입니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자가 액세스 번호로 전화를 걸 때이 이름이 클라이언트에 표시 됩니다.

    
    </div>

7.  **줄 URI**에서 전화 URI 형식에 + 기호를 포함 하 여 번호 앞에 *를 입력 합니다. 예를 들면 전화: + 14255550200
    
    <div>
    

    > [!NOTE]  
    > 다른 전화 접속 회의 액세스 번호에서 동일한 줄 URI를 다시 사용할 수 없습니다.

    
    </div>

8.  **SIP URI**에서 다음을 수행 합니다.
    
      - 텍스트 상자에이 전화 접속 회의 액세스 번호에 대 한 고유한 SIP URI를 입력 합니다. 이 SIP URI는 전화 알림 메시지 및 이전 버전의 Communicator 클라이언트를 포함 하는 다양 한 위치에 표시 됩니다.
        
        <div>
        

        > [!NOTE]  
        > 다른 전화 접속 회의 액세스 번호에서 동일한 SIP URI를 다시 사용할 수 없습니다. 액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다. SIP URI를 변경 하는 유일한 방법은 액세스 번호를 삭제 하 고 다시 만드는 것입니다.

        
        </div>
    
      - 드롭다운 목록 상자에서 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 응용 프로그램의 도메인을 클릭 합니다.

9.  **풀**에서이 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 인스턴스를 실행 하는 풀을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 액세스 번호를 만든 후에 풀을 변경 해야 하는 경우에는 <STRONG>CsApplicationEndpoint</STRONG> cmdlet을 사용 하거나 액세스 번호를 삭제 하 고 다시 만들어야 합니다.

    
    </div>

10. **기본 언어**에서이 전화 접속 액세스 번호에 대 한 프롬프트를 재생할 언어를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 기본 언어는 회의 수행자가 통화에 응답 하는 데 사용 하는 언어입니다. 지원 되는 언어는 전화 접속 회의 설정 웹 페이지에서 각 액세스 전화 번호 옆에 표시 됩니다.

    
    </div>

11. 반드시 **보조 언어 (최대 4 개)** 에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 발신자에 대해 지원할 추가 언어를 하나 이상 선택 하 고 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 각 전화 접속 액세스 번호에 대해 최대 4 개의 보조 언어를 선택할 수 있습니다. 사용자가 회의에 전화를 걸 때 전화 회의 ID를 입력 하기 전에 보조 언어를 선택할 수 있습니다.

    
    </div>

12. 전화 접속 액세스 번호에 대 한 지역을 추가 하려면 **연결 된 지역**아래에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 다이얼 플랜과 연결 된 하나 이상의 지역을 클릭 한 다음 **확인**을 클릭 합니다.

13. 전화 접속 액세스 번호에서 지역을 삭제 하려면 **연결 된 지역**에서 삭제할 지역을 클릭 한 다음 **제거**를 클릭 합니다.

14. **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

