---
title: 마이그레이션 프로세스 - 세부 정보
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>마이그레이션 프로세스 - 세부 정보

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하려면 다음 필수 구성 요소와 세부 단계를 사용 합니다.

<div>

## <a name="prerequisites-for-migration"></a>마이그레이션 필수 조건

Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하기 전에 다음 전제 조건을 충족 해야 합니다.

1.  하나 이상의 Lync Server 2013 풀을 배포 합니다. Lync Server 2013 풀이 여러 개 있는 경우 새 Lync Server 2013 영구 채팅 서버 풀에 대 한 홈 풀이 될 Lync Server 2013 풀을 결정 합니다.

2.  Lync Server 2013, 영구 채팅 서버 풀을 설치 합니다. 비어 있는 항목 (범주, 방 또는 추가 기능은 없음)이 됩니다. 레거시 범주, 회의실 또는 추가 기능을 마이그레이션하기 전에 Lync Server 2013, 영구 채팅 서버 배포에서 회의실, 범주 또는 추가 기능을 만들 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 새로 만든 이러한 항목은 마이그레이션하는 레거시 항목과 충돌할 수 있으므로 주의 해야 합니다. 명명 충돌을 방지 합니다. 그렇지 않으면 레거시 데이터를 마이그레이션할 때 덮어쓰게 됩니다.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>마이그레이션에 대 한 원본 데이터 준비

마이그레이션에 사용할 원본 데이터를 적절 하 게 준비 하려면 다음 단계를 수행 합니다.

1.  Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 원본 데이터베이스를 백업 합니다. SQL Server를 백업 하는 방법에 대 한 자세한 내용은에서 <http://go.microsoft.com/fwlink/p/?linkid=254851>"백업 개요 (SQL Server)"를 참조 하세요.
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory 도메인 서비스는 동일 해야 합니다. 마이그레이션에 대 한 조건으로 다른 배포의 풀로 마이그레이션할 수 없습니다 (특히, 다른 Active Directory 포리스트에서).

    
    </div>

2.  Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 채팅방과 범주 구성을 검사 합니다. 기존 레거시 배포의 범주, 회의실 또는 추가 기능에 대 한 변경 내용은 그룹 채팅 관리 도구를 통해 수행 됩니다.
    
    <div>
    

    > [!TIP]  
    > Lync Server 2013의 범주, 회의실 또는 추가 기능에 대 한 변경 내용은 Lync Server 제어판 또는 Windows PowerShell cmdlet에서 수행 됩니다.

    
    </div>
    
    다음 단계에 따라 마이그레이션에 대 한 레거시 시스템을 준비 합니다.
    
    1.  영구 채팅 서버는 범주에 대 한 깊은 계층 구조 집합과 달리 단일 수준의 범주를 지원 합니다. 마이그레이션 후 하위 범주에는 전체 상위 범주 이름이 접두사로 사용 됩니다. 결과 구조가 요구 사항을 충족 하도록 기존 범주 구조를 단순화 하 고 결합 하는 것이 좋습니다.
    
    2.  루트 범주에서 **관리자** 를 확인 합니다. 이 수준에 관리자가 있는 경우 이러한 사용자는 마이그레이션 후 **모든 채팅방에 관리자로** 추가 됩니다. 조직에 대 한 요구 사항이 아닌 경우 루트 범주에서 이러한 관리자를 제거 해야 합니다.
    
    3.  방 이름의 길이를 확인 합니다. 마이그레이션 후에는 간소화 된 범주 구조로 인해 해당 채팅방이 하위 범주 아래에 있는 경우 전체 상위 범주 이름을 접두사로 사용 합니다. 이름 제한은 상위 범주 이름을 포함 하 여 256 자입니다. 방 이름의 길이를 확인 하 여 길이가 너무 긴 경우 길이를 줄여야 합니다.
    
    4.  Lync Server 2013에서 범주 **초대** 설정이 true로 설정 된 경우 해당 범주 아래에 있는 채팅방에 대 한 초대에 대해 true 또는 false를 선택할 수 있습니다. 그러나 범주 초대 설정이 false로 설정 된 경우 해당 범주의 채팅방에는 초대가 해제 되어 있습니다. 특정 범주 아래에 방 (들)이 존재 하도록 하려면 마이그레이션하기 전에 레거시 Lync Server 그룹 채팅 서버 버전에서 초대 설정을 다시 설정 해야 합니다. 그렇지 않으면 마이그레이션 중에 Lync Server 2013에서 경고가 표시 되 고 채팅방이 기본값 false로 설정 됩니다.
    
    5.  채팅방에서 파일을 사용한 경우에는 마이그레이션한 후 새 영구 채팅 파일 저장소에 파일을 수동으로 XCOPY 해야 합니다. 도구가이 작업을 수행 하지 않습니다.
    
    6.  페더레이션 사용자와 페더레이션 사용자 및 채팅방을 사용 하는 경우 영구 채팅 서버가 페더레이션을 지원 하지 않는다는 점에 유의 하세요. 페더레이션 사용자가 있는 채팅방은 마이그레이션됩니다. 그러나 페더레이션 액세스는 지원 되지 않으므로 사용자 자체는 콘텐츠에 액세스할 수 없습니다.
    
    7.  마이그레이션하지 않으려는 채팅방을 확인 하 고 사용 안 함으로 표시 합니다.
    
    8.  채팅방 콘텐츠를 마이그레이션할 이후 날짜를 확인 합니다. 예를 들어, 2010 년 1 월 1 일 이전에는 이러한 메시지가 오래 되거나 마이그레이션과 관련이 없기 때문에이 메시지를 마이그레이션하지 않을 수 있습니다.

</div>

<div>

## <a name="performing-the-migration"></a>마이그레이션 수행

다음 단계를 수행 하 여 이전 그룹 채팅 서버를 마이그레이션합니다.

1.  Lync Server 2010, 그룹 채팅, Office Communications Server 2007 R2 그룹 채팅 또는 Lync Server 2013, 영구 채팅 서버 서비스를 종료 합니다. 모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분할 때이 작업을 수행할 계획입니다. 앞에서 설명한 대로 현재 그룹 채팅 데이터베이스를 백업 해야 합니다.

2.  Windows PowerShell **내보내기-CsPersistentChatData** Cmdlet을 영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 실행 합니다. 내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하세요.
    
    내보낸 콘텐츠를 검사 합니다.

3.  가져오기 전에 Lync Server 2013, 영구 채팅 서버 서비스를 종료 하세요. 모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분 한 경우에이 작업을 수행 하도록 계획 합니다.

4.  마이그레이션 전에 Lync Server 2013 배포에서 범주, 방 또는 추가 기능을 만든 경우 영구 채팅 데이터베이스의 백업을 수행 합니다. 내보내기/가져오기 프로세스는 레거시 데이터를 Lync Server 2013 배포에 병합할 수 있지만, 해당 콘텐츠를 실수로 덮어쓴 경우 (예: 이름 충돌이 여전히 존재 하는 경우)에는 데이터베이스를 백업 하는 것이 좋습니다.

5.  Windows PowerShell **가져오기-CsPersistentChatData** cmdlet (가져오기 도구)을 실행 하 여 **WhatIf** 명령을 사용 하 여 영구 채팅 서버 풀의 백 엔드 서버를 마이그레이션된 데이터로 채웁니다. 간단한 관리 모델을 수용 하기 위해 일부 변환이 진행 중에 발생 합니다. 표시 되는 오류 또는 경고를 수정 합니다.

6.  영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 지속적인 채팅 서버 Windows PowerShell **CsPersistentChatData** cmdlet을 실행 합니다. 내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하세요.

7.  모든 업로드 된 파일 (전체 폴더)을 새 Lync Server 2013, 영구 채팅 파일 저장소에 XCOPY 해야 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (클라이언트)는 채팅방에서 파일을 업로드 하거나 보는 것을 지원 하지 않습니다. 여전히 레거시 클라이언트를 사용 하 여 룸에서 파일을 게시 하 고 볼 수 있습니다.

    
    </div>

8.  Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 조회 서버 URI를 Lync Server 2013, 영구 채팅 서버 contact 개체에 이식 합니다. Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅 클라이언트가 클라이언트쪽 구성 변경 없이 마이그레이션 후 최신 Lync 2013, 영구 채팅 (클라이언트)에 연결 해야 하는 경우 다음 단계가 필요 합니다.
    
      - Ocschat@\<DomainName\>조회 서버 사용자 계정을 삭제 합니다. 이는 Lync Server 2010, 그룹 채팅에서 조회 서비스를 가리키는 데 사용 됩니다. 풀을 제거 하 고 나중에 신뢰 된 항목을 제거할 수 있습니다.
    
      - 서비스를 다시 시작할 때 레거시 클라이언트가 효과적으로 작동할 수 있도록 동일한 SIP URI를 사용 하 여 Windows PowerShell cmdlet 인 **CsPersistentChatEndpoint**를 실행 하 여 레거시 끝점 (영구 채팅 서버 contact 개체)을 만듭니다.
    
    필수 마이그레이션 프로세스는이 시점에 완료 됩니다. Lync 2010 그룹 채팅 (클라이언트) 또는 Office Communicator 2007 R2 그룹 채팅 (클라이언트)이 새 영구 채팅 서버 풀에 투명 하 게 연결할 수 있습니다.
    
    Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 다음 추가 폐기 단계를 따르세요.

9.  새로운 영구 채팅 서버 풀에서 모든 컴퓨터를 설정 하 여 영구 채팅 서버 서비스를 시작 합니다.

10. Lync Server 제어판 및 Windows PowerShell cmdlet을 사용 하 여 데이터가 성공적으로 마이그레이션 되었는지 확인 합니다.

11. 그룹 채팅 서버 풀의 컴퓨터에서 Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅을 제거 합니다.

12. Windows PowerShell cmdlet을 사용 하 여 신뢰할 수 있는 응용 프로그램 및 신뢰 된 응용 프로그램 풀을 삭제 합니다. 이렇게 하면 중앙 관리 저장소에서 이러한 항목이 삭제 되 고 Active Directory에서 TSEs (신뢰할 수 있는 서비스 항목)가 연결 됩니다. 또는이 단계는 토폴로지 작성기를 사용 하 여 작동 합니다 (신뢰할 수 있는 응용 프로그램/풀에도 전용 노드가 있습니다.).

13. 이제 새 클라이언트를 통해 영구 채팅 서버 기능을 사용 하도록 설정할 수 있습니다. 영구 채팅 서버를 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md)를 참조 하세요.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013는 여러 영구 채팅 서버 풀을 지원 합니다. 그러나 Lync 2010 그룹 채팅 또는 Office Communications Server 2007 R2&nbsp;그룹 채팅 풀을 단일 Lync 서버 2013, 영구 채팅 서버 풀로 마이그레이션할 수 있습니다. 배포에 새 영구 채팅 서버 풀을 추가 하 여 규정 요구를 충족 시킬 수 있습니다 (예: 지정 된 지리 내에 데이터 유지).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

