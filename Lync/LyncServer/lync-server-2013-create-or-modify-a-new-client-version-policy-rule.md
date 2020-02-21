---
title: 'Lync Server 2013: 새 클라이언트 버전 정책 규칙 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fec7930b8ebd7aa6bb7f50c71a1f163cdb83f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Lync Server 2013에서 새 클라이언트 버전 정책 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-21_

클라이언트 버전 정책 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온 하려고 할 때 수행 해야 하는 작업을 정의 합니다. Lync Server 2013 제어판에서 클라이언트 버전 정책에 대 한 개별 규칙을 만들거나 수정할 수 있습니다.

<div>


> [!IMPORTANT]  
> 규칙은 우선 순위에 나열 되어 있습니다. 예를 들어 버전 1.5을 실행 하는 클라이언트를 연결할 수 있도록 하 고 2.0 보다 이전 버전을 실행 하는 클라이언트를 차단 하는 규칙을 사용 하는 경우 첫 번째 규칙이 우선 순위를 가지 며 버전 1.5을 실행 하는 클라이언트는 연결할 수 있습니다.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 버전 정책 규칙을 만들거나 수정 하려면

1.  Lync server 제어판을 사용 하 여 [Lync server 2013에서 새 클라이언트 버전 정책을 만들거나 수정](lync-server-2013-create-or-modify-a-new-client-version-policy.md) 합니다.

2.  **클라이언트 버전 정책 편집** 페이지에서 다음 중 하나를 수행 합니다.
    
      - **새로** 만들기를 클릭 하 여 새 클라이언트 버전 규칙을 만듭니다.
    
      - 목록에서 정의 된 클라이언트 유형 중 하나를 클릭 한 다음 **자세한 정보 표시**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 와일드 카드를 사용 하 여 클라이언트 유형을 나타낼 수 있습니다.

    
    </div>

3.  **사용자 에이전트**에서 클라이언트 유형을 선택 합니다.

4.  **버전 번호**에서 다음을 수행 합니다.
    
      - **주 버전**에서 클라이언트의 주요 릴리스에 해당 하는 번호를 입력 합니다.
    
      - **부 버전**에서 클라이언트의 보조 릴리스에 해당 하는 번호를 입력 합니다.
    
      - **빌드**에 클라이언트의 주 버전 및 보조 릴리스에 해당 하는 번호를 입력 합니다.
    
      - **업데이트**에 클라이언트의 업데이트 된 버전에 해당 하는 번호를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 와일드 카드를 사용 하 여 클라이언트 버전 번호를 지정할 수 있습니다.

    
    </div>

5.  이전 단계에서 지정한 클라이언트 버전에 대 한 일치 작업을 지정 하려면 **비교 작업**에서 다음 중 하나를 클릭 합니다.
    
      - **과 동일**
    
      - **아닌**
    
      - **보다 최근**
    
      - **보다 최근 이거나 같음**
    
      - **보다 오래 됨**
    
      - **보다 오래 되거나 같음**

6.  이전 단계의 조건이 충족 될 때 수행할 작업을 지정 하려면 **작업**에서 다음 중 하나를 클릭 합니다.
    
      - 클라이언트가 로그온 하도록 허용 하려면 **허용**을 클릭 합니다.
    
      - 클라이언트가 Windows Server 업데이트 서비스 또는 Microsoft 업데이트에서 로그온 하 고 업데이트를 받을 수 있도록 하려면 **허용 및 업그레이드**를 클릭 합니다. 이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.
        
        <div>
        

        > [!NOTE]  
        > 이 작업을 선택 하면 다음에 사용자가 Lync 2013에 로그인 할 때 알림이 표시 됩니다. 알림에는 Windows Server Update Service 또는 Microsoft Update에 업데이트가 아직 게시되지 않았더라도 사용할 수 있는 업데이트가 표시됩니다. 혼란을 방지하기 위해서는 업데이트를 사용할 수 있게 된 뒤에만 이 작업을 선택해야 합니다.

        
        </div>
    
      - 클라이언트의 로그온을 허용 하 고 다른 클라이언트 버전을 다운로드할 위치에 대 한 메시지를 표시 하려면 **URL로 허용**을 클릭 합니다. 이 절차의 뒷부분에서 URL을 지정 합니다.
    
      - 클라이언트가 로그온 할 수 없도록 하려면 **차단을**클릭 합니다.
    
      - 클라이언트가 로그온 하지 못하게 하 고 클라이언트가 Windows Server 업데이트 서비스 또는 Microsoft 업데이트에서 업데이트를 받을 수 없도록 하려면 **차단 및 업그레이드**를 클릭 합니다. 이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.
    
      - 클라이언트가 로그온 할 수 없도록 하 고 다른 클라이언트 버전을 다운로드할 위치에 대 한 메시지를 표시 하려면 **URL로 차단을**클릭 합니다. 이 절차의 뒷부분에서 URL을 지정 합니다.

7.  반드시 이전 단계에서 **url로 허용** 또는 **url로 차단을** 클릭 한 경우 **url**에 메시지에 포함할 클라이언트 다운로드 URL을 입력 합니다.

8.  **확인**을 클릭 한 다음 **커밋을**클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

