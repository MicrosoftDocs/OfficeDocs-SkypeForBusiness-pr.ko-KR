---
title: 마이그레이션 프로세스-세부 정보
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76624475b86427d8e3b1aa4f9efa75c127afcb85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>마이그레이션 프로세스-세부 정보

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하려면 다음 필수 구성 요소 및 세부 단계를 사용 합니다.

<div>

## <a name="prerequisites-for-migration"></a>마이그레이션을 위한 사전 요구 사항

Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하기 전에 다음 필수 구성 요소를 충족 해야 합니다.

1.  하나 이상의 Lync Server 2013 풀을 배포 합니다. Lync Server 2013 풀이 여러 개 있는 경우 새 Lync Server 2013 영구 채팅 서버 풀에 대 한 홈 풀이 될 Lync Server 2013 풀을 결정 합니다.

2.  Lync Server 2013, 영구 채팅 서버 풀을 설치 합니다. 범주, 채팅방, 추가 기능 등이 전혀 없이 빈 상태일 것입니다. 레거시 범주, 회의실 또는 추가 기능을 마이그레이션하기 전에 Lync Server 2013, 영구 채팅 서버 배포에 회의실, 범주 또는 추가 기능을 만들 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Be aware that these newly created items may conflict with legacy items that you migrate. Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>마이그레이션을 위해 원본 데이터 준비

다음 단계를 수행하여 마이그레이션을 위해 원본 데이터를 올바로 준비합니다.

1.  Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 원본 데이터베이스를 백업 합니다. SQL Server를 백업 하는 방법에 대 한 자세한 내용은의 "백업 개요 (SQL Server)"를 참조 하십시오 <https://go.microsoft.com/fwlink/p/?linkid=254851> .
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory 도메인 서비스는 동일 해야 합니다. 마이그레이션을 위한 조건으로, 특히, 다른 Active Directory 포리스트에서 다른 배포의 풀로 마이그레이션할 수 없습니다.

    
    </div>

2.  Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 대화방 및 범주 구성을 검사 합니다. 기존 레거시 배포의 범주, 대화방 또는 추가 기능에 대 한 변경 내용은 그룹 채팅 관리 도구를 통해 수행 됩니다.
    
    <div>
    

    > [!TIP]  
    > Lync Server 2013, 영구 채팅 서버 배포의 범주, 대화방 또는 추가 기능에 대 한 변경 내용은 Lync Server 제어판 또는 Windows PowerShell cmdlet을 통해 수행 됩니다.

    
    </div>
    
    다음 단계를 수행하여 기존 시스템을 마이그레이션할 준비를 합니다.
    
    1.  영구 채팅 서버는 범주에 대 한 심도 깊은 계층 집합과 달리 단일 수준의 범주를 지원 합니다. 마이그레이션이 완료되면 하위 범주 앞에 전체 상위 범주 이름이 붙습니다. 기존 범주 구조를 단일 계층으로 단순화하여 요구 사항에 맞는 결과 구조를 만들 수도 있습니다.
    
    2.  Verify the **Managers** at the root Category. If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration. If this is not a requirement for your organization, you need to remove these Managers from the root Category.
    
    3.  Verify the length of room names. After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names. The naming limit is 256 characters, including parent category names. You must verify the length of the room names and possibly shorten the length, if they are too long.
    
    4.  Lync Server 2013에서 범주 **초대** 설정이 true로 설정 된 경우 해당 범주의 대화방에 대 한 초대에 대해 true 또는 false를 선택할 수 있습니다. 하지만 범주 초대 설정이 거짓으로 설정된 경우 해당 범주 아래의 채팅방은 해제됩니다. 특정 범주에 해당 하는 대화방을 만들려는 경우 마이그레이션 전에 레거시 Lync Server 그룹 채팅 서버 버전에서 초대 설정을 다시 설정 해야 합니다. 그렇지 않으면 마이그레이션 중에 Lync Server 2013에서 경고를 표시 하 고 대화방을 기본값인 false로 설정 합니다.
    
    5.  채팅방에서 파일을 사용한 경우에는 마이그레이션 후에 새 영구 채팅 파일 저장소로 파일을 수동으로 XCOPY 해야 합니다. 이는 자동으로 수행되지 않습니다.
    
    6.  페더레이션 사용자와 대화방을 연결 해야 하는 경우 영구 채팅 서버가 페더레이션을 지원 하지 않는다는 것을 염두에 두어야 합니다. 페더레이션 사용자가 있는 채팅방은 마이그레이션되지만 페더레이션 액세스가 지원되지 않으므로 사용자 자신은 콘텐츠에 액세스할 수 없습니다.
    
    7.  마이그레이션하지 않으려는 채팅방을 식별하여 사용 안 함으로 표시합니다.
    
    8.  Identify the date beyond which you want to migrate the chat room content. For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.

</div>

<div>

## <a name="performing-the-migration"></a>마이그레이션 수행

다음 단계를 수행 하 여 레거시 그룹 채팅 서버를 마이그레이션합니다.

1.  Lync Server 2010, 그룹 채팅, Office Communications Server 2007 R2 그룹 채팅 또는 Lync Server 2013, 영구 채팅 서버 서비스를 종료 합니다. 모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분 한 시간에이 작업을 수행 하도록 계획 합니다. 앞에서 설명한 것 처럼 현재 그룹 채팅 데이터베이스를 백업 해야 합니다.

2.  Windows PowerShell **export-cspersistentchatdata** Cmdlet을 영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 실행 합니다. 내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하십시오.
    
    내보낸 콘텐츠를 조사합니다.

3.  가져오기 전에 Lync Server 2013, 영구 채팅 서버 서비스를 종료 합니다. 모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분 한 시간에이 작업을 수행 하도록 계획 합니다.

4.  마이그레이션 전에 Lync Server 2013 배포에서 범주, 대화방 또는 추가 기능을 만든 경우 영구 채팅 데이터베이스의 백업을 수행 합니다. 내보내기/가져오기 프로세스를 통해 레거시 데이터를 Lync Server 2013 배포에 병합할 수는 있지만, 그래도 이름 충돌이 여전히 존재 하는 경우에는 콘텐츠를 실수로 덮어쓰는 경우에 대비 하 여 데이터베이스를 백업 하는 것이 좋습니다.

5.  **WhatIf** 명령을 사용 하 여 Windows PowerShell **export-cspersistentchatdata** cmdlet (가져오기 도구)을 실행 하 여 영구 채팅 서버 풀의 백 엔드 서버를 마이그레이션된 데이터로 채웁니다. 단순화된 관리 모델을 적용하는 과정에서 일부 메시지가 표시될 수 있습니다. 나타나는 오류 또는 경고를 수정합니다.

6.  영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 영구 채팅 서버 Windows PowerShell **export-cspersistentchatdata** cmdlet을 실행 합니다. 내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하십시오.

7.  업로드 된 모든 파일 (전체 폴더)을 새 Lync Server 2013, 영구 채팅 파일 저장소로 XCOPY 해야 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (클라이언트)은 대화방에서 파일을 업로드 하거나 보는 것을 지원 하지 않습니다. 채팅방의 파일을 보고 게시하기 위해 기존 클라이언트를 계속 사용할 수 있습니다.

    
    </div>

8.  Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 조회 서버 URI를 Lync Server 2013, 영구 채팅 서버 연락처 개체에 이식 합니다. 다음 단계는 Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅 클라이언트가 클라이언트 쪽 구성 변경 없이 마이그레이션 후 최신 Lync 2013, 영구 채팅 (클라이언트)에 연결 해야 하는 경우에 필요 합니다.
    
      - Ocschat@ \<domainName\> .Com 조회 서버 사용자 계정을 삭제 합니다. 이는 Lync Server 2010, 그룹 채팅의 조회 서비스를 가리키는 데 사용 됩니다. 풀을 제거하고 신뢰할 수 있는 항목을 나중에 제거할 수 있습니다.
    
      - 레거시 클라이언트가 서비스를 다시 시작할 때 효과적으로 작동 하도록 하려면 Windows PowerShell cmdlet **get-cspersistentchatendpoint**를 실행 하 여 동일한 SIP URI를 사용 하 여 레거시 끝점 (영구 채팅 서버 대화 상대 개체)을 만듭니다.
    
    이제 필수 마이그레이션 프로세스를 완료했습니다. Lync 2010 그룹 채팅 (클라이언트) 또는 Office Communicator 2007 R2 그룹 채팅 (클라이언트)은 이제 새 영구 채팅 서버 풀에 투명 하 게 연결할 수 있습니다.
    
    Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 다음 추가 폐기 단계를 수행 합니다.

9.  새 영구 채팅 서버 풀의 모든 컴퓨터를 설정 하 여 영구 채팅 서버 서비스를 시작 합니다.

10. Lync Server 제어판 및 Windows PowerShell cmdlet을 사용 하 여 데이터가 제대로 마이그레이션 되었는지 확인 합니다.

11. 그룹 채팅 서버 풀의 컴퓨터에서 Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅을 제거 합니다.

12. Windows PowerShell cmdlet을 사용 하 여 신뢰할 수 있는 응용 프로그램 및 트러스트 된 응용 프로그램 풀을 삭제 합니다. 이렇게 하면 중앙 관리 저장소에서 이러한 항목과 Active Directory에서 연결 된 TSEs (신뢰할 수 있는 서비스 항목)가 삭제 됩니다. 또한 토폴로지 작성기를 사용 하 여이 단계를 수행할 수도 있습니다 (신뢰할 수 있는 응용 프로그램/풀에도 전용 노드가 있습니다.).

13. 이제 새 클라이언트를 통해 영구 채팅 서버 기능을 사용 하도록 설정할 수 있습니다. 영구 채팅 서버를 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md)를 참조 하십시오.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013에서는 여러 영구 채팅 서버 풀을 지원 합니다. 그러나 microsoft는 Lync 2010 그룹 채팅 또는 Office Communications Server 2007 R2 &nbsp; 그룹 채팅 풀을 단일 Lync Server 2013, 영구 채팅 서버 풀로 마이그레이션하는 것을 지원 합니다. 배포에 새 영구 채팅 서버 풀을 추가 하 여 규정 요구 사항 (예: 지정 된 지리 내의 데이터 유지)을 충족할 수 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

