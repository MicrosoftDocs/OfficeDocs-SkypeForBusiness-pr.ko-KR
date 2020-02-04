---
title: 'Lync Server 2013: 토폴로지에 영구 채팅 서버 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f8c65f561a0f2c7b1937d60344c0177d221ba8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지에 영구 채팅 서버 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

영구 채팅 서버를 지원 하도록 배포를 구성할 수 있으려면 먼저 토폴로지에 Lync Server 2013, 영구 채팅 서버 지원을 통합 해야 합니다. 이 항목의 정보는 토폴로지 작성기를 사용 하 여 기존 토폴로지에 영구 채팅 서버 지원을 추가 하는 방법에 대해 설명 합니다.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>토폴로지에 영구 채팅 서버 추가

재해 복구 구성 없이 단일 영구 채팅 서버 풀을 설치 하려면 다음 단계를 수행 합니다. 고가용성 및 재해 복구용으로 늘어난 영구 채팅 서버 풀을 구성 하려면 배포 설명서의 [Lync Server 2013에서 고가용성 및 재해 복구용으로 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 참조 하세요.

여러 영구 채팅 서버 풀을 배포 하려면 각 풀에 대해 동일한 프로세스를 반복 합니다.

1.  Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정을 사용 하거나 해당 사용자 권한이 있는 계정으로 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만, Lync Server 2013 서버를 설치 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 하며 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있는지 확인 합니다 (즉, 토폴로지 작성기가 필수 dacl을 구성할 수 있도록). 또는 해당 권한이 있는 계정

    
    </div>

2.  토폴로지 작성기를 시작 합니다.

3.  콘솔 트리에서 **영구 채팅 풀** 노드로 이동한 다음 확장 하 여 영구 채팅 서버 풀을 선택 하거나 노드를 마우스 오른쪽 단추로 클릭 하 고 **새 영구 채팅 풀**을 선택 합니다. 풀의 FQDN (정규화 된 도메인 이름)을 정의 하 고 풀이 단일 서버 풀 또는 다중 서버 풀 배포 인지 여부를 표시 해야 합니다.
    
    **여러 컴퓨터 풀** 또는 **단일 컴퓨터 풀**을 선택할 수 있습니다. 영구 채팅 서버 풀에 둘 이상의 영구 채팅 서버 프런트 엔드 서버가 있는 경우에는 이전을 선택 합니다. 이 옵션을 지금 설정 하거나, 나중에 단일 컴퓨터 풀을 만든 후 나중에 추가 서버를 추가할 수 없기 때문입니다. 여러 컴퓨터 풀을 선택 하는 경우 풀을 구성 하는 개별 영구 채팅 서버 프런트 엔드 서버의 이름을 입력 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 영구 채팅 서버 역할이 Lync Server 2013&nbsp;standard edition server에 설치 되는 경우 Fqdn은 스탠더드 버전 서버의 fqdn과 일치 해야 합니다.

    
    </div>

4.  영구 채팅 서버 풀에 대 한 간단한 **표시 이름을** 정의 합니다. 표시 이름은 사용자 지정 클라이언트 (특히 영구 채팅 서버 풀이 여러 개 있는 경우)를 사용 하 여 채팅방을 구분 합니다.

5.  Lync Server 프런트 엔드 서버와 통신 하기 위해 영구 채팅 서버에서 사용 하는 포트를 정의 합니다. 기본 포트는 5041입니다.

6.  조직에 준수 지원이 필요한 경우 **준수 사용** 확인란을 선택 합니다. 선택 하는 경우 영구 채팅 서버 준수 서비스는 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 설치 됩니다. 나중에 영구 채팅 서버 준수에 대 한 SQL Server 백 엔드 서버를 선택 하 라는 메시지가 표시 됩니다.

7.  영구 채팅 서버 풀에 대 한 사이트 선호도를 할당 합니다. **사이트 \<SiteName\> 에이 풀을 기본값으로 사용** 확인란을 선택 하거나이 **풀을 모든 사이트의 기본값으로 사용** 하 여이 영구 채팅 서버 풀을 현재 사이트 또는 모든 사이트의 기본 풀로 지정 합니다. Lync 2013 클라이언트를 사용 하 여 회의실을 만들고 관리 하는 경우, 사용자의 사이트와 연결 된 기본 풀을 룸 만들기 및 관리 환경에서 사용 하 여 룸 만들기 및 관리 작업을 해당 풀에 라우팅할 수 있습니다. 이는 여러 영구 채팅 서버 풀이 배포 되어 있고 영구 채팅 서버의 채팅방 만들기 및 관리 기능을 사용 하려는 경우에만 적용 됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 채팅방 만들기 및 관리 기능을 사용자 지정할 수 있습니다.<BR>장애 복구용 SQL Server 백업 데이터베이스를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구용 영구 채팅 서버 구성을</A> 참조 하세요.

    
    </div>

8.  다음 중 하나를 실행 하 여 **영구 채팅 서버 백 엔드 (채팅방 콘텐츠 저장)에 대 한 SQL 저장소** 를 정의 합니다.
    
      - 기존 SQL Server 데이터베이스를 사용 하려면 드롭다운 목록에서 사용 하려는 SQL Server 데이터베이스의 이름을 클릭 합니다.
    
      - 새 SQL Server 데이터베이스를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 sql 저장소 정의**에서 다음을 수행 합니다.
    
    <!-- end list -->
    
      - **Sql SERVER fqdn**에서 새 sql server 데이터베이스를 만들 대상 sql SERVER의 fqdn을 지정 합니다.
    
      - 기본 인스턴스를 사용 하려면 **기본 인스턴스를 선택 하** 고, 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 선택 하 고 사용 하려는 인스턴스를 지정 합니다.

9.  준수를 사용 하도록 설정한 경우 SQL Server 규정 준수 데이터베이스를 정의 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 영구 채팅 서버 데이터베이스와 영구 채팅 서버 준수 데이터베이스에 대해 고가용성을 위해 SQL Server 미러를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구용 영구 채팅 서버 구성을</A> 참조 하세요.

    
    </div>

10. 파일 저장소를 정의 합니다. 파일 저장소는 파일 저장소에 업로드 된 파일의 복사본이 저장 되는 폴더 (예: 채팅방에 게시 된 파일 첨부 저장)입니다. 다중 서버 영구 채팅 서버 토폴로지의 경우 UNC (범용 명명 규칙) 경로 여야 합니다. 단일 서버 영구 채팅 서버 토폴로지의 경우 로컬 파일 경로일 수 있습니다.
    
    기존 파일 저장소를 사용 하려면 다음 단계를 수행 합니다.
    
      - **파일 서버 FQDN**에 새 파일 저장소를 만들 파일 저장소의 fqdn을 지정 합니다.
    
      - **파일 공유**에서 사용 하려는 파일 저장소를 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 파일 저장소를 만들기 전에 토폴로지 작성기에서 파일 저장소를 정의할 수 있지만 토폴로지를 게시 하기 전에 정의한 위치에 파일 저장소를 만들어야 합니다.

    
    </div>

11. 이 영구 채팅 서버 풀의 다음 홉으로 사용할 프런트 엔드 서버 풀을 선택 합니다. 이 풀로 영구 채팅 서버 요청을 라우팅할 수 있는 프런트 엔드 서버 풀입니다.

12. 구성을 저장 하려면 **마침을**클릭 합니다. 토폴로지 작성기에는 특정 풀 설정에 따라 영구 채팅 서버 풀이 표시 됩니다.
    
    이제 영구 채팅 서버에 업데이트 된 토폴로지를 게시 하려면 배포 설명서의 [Lync Server 2013에 업데이트 된 토폴로지 게시](lync-server-2013-publish-the-updated-topology.md) 를 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > 토폴로지 작성기가 이미 열려 있는 경우에는 <A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013에서 업데이트 된 토폴로지 게시</A> 의 3 단계를 진행 하 여 업데이트 된 토폴로지 게시를 시작할 수 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

