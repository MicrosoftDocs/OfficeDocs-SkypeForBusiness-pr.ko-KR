---
title: 'Lync Server 2013: 범주 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb70397514589ac6f3cc74d84a6ae7509c9baa5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Lync Server 2013에서 범주 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

Lync Server 2013 제어판에서는 **영구 채팅** 페이지의 **범주** 섹션을 사용 하 여 범주를 구성할 수 있습니다. 영구 채팅방 범주는 채팅방을 구성 하기 위한 논리적 구조입니다. 범주는 채팅방을 만들거나 채팅방에 참가할 수 있는 사용자 및 사용자 그룹을 제어하기 위한 기본 ACL(액세스 제어 목록) 집합을 정의합니다. 범주를 사용하여 조직 내의 개별 하위 부문 간에 교신 차단 영역을 적용할 수 있습니다.

채팅방 범주는 채팅방은 포함할 수 있지만 다른 범주는 포함할 수 없습니다. 각 범주는 이름, 설명 등의 메타데이터로 해당 콘텐츠를 설명합니다. 또한 범주는 채팅 방에서 초대 또는 파일 업로드를 허용하거나 채팅 기록을 포함하는 등 범주에 속하는 채팅방의 동작을 제어하기 위해 설정할 수 있는 속성을 포함합니다.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>채팅방에 대한 범주를 구성하려면

1.  CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.

2.  **시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell cmdlet을 사용할 수도 있습니다. 자세한 내용은 배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하십시오.

    
    </div>

3.  왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **범주**를 클릭합니다.
    
    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.

4.  **범주** 페이지에서 **새로 만들기** 또는 **편집**을 클릭합니다.

5.  **서비스 선택**에서 범주를 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다. 이 서비스는 영구 채팅 (클라이언트)이 범주가 속한 풀을 식별 하는 데 사용 하는 영구 채팅 서버 풀입니다. 범주는 하나의 영구 채팅 서버 풀에만 속할 수 있으며 다른 그룹으로 이동 하거나 다른 풀과 공유 될 수 없습니다.

6.  **새 범주**에서 다음을 수행합니다.
    
    1.  **이름**에서 새 방 범주의 이름을 지정합니다.
    
    2.  **설명**에서 방 범주의 자세한 설명을 입력합니다(예: Contoso의 방 범주).
    
    3.  이 범주에 속하는 대화방에 대해 초대를 사용 하도록 설정할 수 있는지 여부를 제어 하려면 **초대 사용** 확인란을 선택 하거나 선택을 취소 합니다. 이 범주를 선택 하면이 종류의 대화방에서 초대를 보내거나 해제할 수 있습니다. 이 확인란의 선택을 취소 하면이 종류의 채팅방에 초대가 허용 되지 않습니다. 대화방에서 초대를 받은 경우 새 구성원이 대화방에 추가 되 면 영구 채팅 클라이언트에서 새 채팅방에 대 한 알림을 가져옵니다.
    
    4.  해당 범주에 속하는 채팅방에서 파일 업로드를 제어하려면 **파일 업로드 사용** 확인란을 선택하거나 선택을 취소합니다. 이 확인란을 선택하는 경우 해당 범주의 방에서 파일 업로드를 사용하거나 사용하지 않도록 설정할 수 있습니다. 이 확인란의 선택을 취소하는 경우에는 해당 범주의 방에서 파일을 업로드할 수 없습니다.
        
        <div>
        

        > [!IMPORTANT]  
        > 이 설정은 Office Communications Server 2007 R2&nbsp;그룹 채팅 서버 또는 Lync server 2010을 사용 하는 사용자 지정 응용 프로그램 또는 이전 그룹 채팅 클라이언트에서 파일을 대화방에 게시할 수 있기 때문에 서버에 적용 됩니다. Lync 2013 클라이언트에는 파일 업로드/다운로드 기능이 없으므로 순수한 Lync 2013 배포 또는 Lync 2013 클라이언트가 있으면 영구 채팅 서버 채팅방에 파일을 게시할 수 없습니다.

        
        </div>
    
    5.  채팅 기록을 제어 하려면 **채팅 기록 사용** 확인란을 선택 하거나 선택을 취소 합니다. 이 확인란을 선택하는 경우 방의 채팅 내용이 영구적으로 보존되고, 그렇지 않으면 채팅 메시지가 영구적으로 보존되지 않습니다. 준수를 사용하도록 설정한 경우에는 방의 채팅 내용이 준수에 저장되지만 사용자는 이전 메시지에 액세스할 수 없게 됩니다. 이 옵션은 채팅 기록을 영구적으로 보존하지 않아도 되는 실시간 임시 공동 작업용으로 지정된 방에 사용할 수 있습니다.

7.  **범주 편집**에서 다음을 수행합니다.
    
      - **구성원 자격**의 **허용 구성원** 섹션에서 사용자 및 기타 Active Directory 도메인 서비스 주체 (사용자, 메일 그룹, 조직 구성 단위 등)를 범주에 속하는 대화방의 구성원으로 추가할 수 있도록 추가 하거나 제거 합니다. 특정 범주에서 허용된 계정은 방의 구성원만 디렉터리에서 방을 검색할 수 있도록 방이 숨겨져 있지 않은 한 해당 범주에서 방을 검색할 수 있습니다.
    
      - **구성원 자격**의 거부 된 **구성원** 섹션에서 대화방에서 거부 되는 구성원과 연결 된 사용자 및 기타 Active Directory 보안 주체를 추가 하거나 제거 합니다.
    
      - **멤버 자격**의 **작성자** 섹션에서 해당 범주에 대해 작성자와 연결 된 사용자 및 기타 Active Directory 보안 주체를 추가 하거나 제거 합니다. 작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 할당할 권한이 있는 사용자입니다.

8.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

