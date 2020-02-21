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
ms.openlocfilehash: 5ae7ca7e475fd106608dea09fedf250ef541a5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Lync Server 2013의 토폴로지에 영구 채팅 서버 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

영구 채팅 서버를 지원 하도록 배포를 구성 하기 전에 토폴로지의 Lync Server 2013, 영구 채팅 서버 지원을 통합 해야 합니다. 이 항목의 정보에서는 토폴로지 작성기를 사용 하 여 기존 토폴로지에 영구 채팅 서버 지원을 추가 하는 방법에 대해 설명 합니다.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>토폴로지에 영구 채팅 서버를 추가 하려면

재해 복구 구성 없이 단일 영구 채팅 서버 풀을 설치 하려면 다음 단계를 수행 합니다. 고가용성 및 재해 복구를 위해 확장 된 영구 채팅 서버 풀을 구성 하려면 배포 설명서의 [Lync server 2013에서 고가용성 및 재해 복구용으로 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 참조 하십시오.

여러 영구 채팅 서버 풀을 배포 하려면 각 풀에 대해 동일한 프로세스를 반복 합니다.

1.  Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정 또는 이와 동등한 사용자 권한이 있는 계정으로 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만, Lync Server 2013 서버를 설치 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 하며, 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (읽기, 쓰기 및 수정)이 포함 되어 있어야 합니다 (즉, 토폴로지 작성기에서 필요한 dacl을 구성할 수 있도록 함). 또는 이와 동등한 권한을 가진 계정

    
    </div>

2.  토폴로지 작성기를 시작합니다.

3.  콘솔 트리에서 **영구 채팅 풀** 노드로 이동한 후 확장 하 여 영구 채팅 서버 풀을 선택 하거나, 노드를 마우스 오른쪽 단추로 클릭 하 고 **새 영구 채팅 풀**을 선택 합니다. 풀의 FQDN(정규화된 도메인 이름)을 정의하고 풀이 단일 서버 풀 또는 다중 서버 풀 배포인지 여부를 나타내야 합니다.
    
    **다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀**을 선택할 수 있습니다. 영구 채팅 서버 풀에 영구 채팅 서버 프런트 엔드 서버를 두 개 이상 사용할 계획인 경우에는 이전을 선택 합니다. 이 항목을 지금 선택 하거나 나중에 단일 컴퓨터 풀을 만든 후 나중에 서버를 더 추가할 수 없기 때문입니다. 다중 컴퓨터 풀을 선택 하는 경우에는 풀을 구성 하는 개별 영구 채팅 서버 프런트 엔드 서버의 이름을 입력 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 영구 채팅 서버 역할을 Lync Server 2013&nbsp;Standard edition 서버에 설치 하는 경우 Fqdn이 Standard EDITION 서버의 fqdn과 일치 해야 합니다.

    
    </div>

4.  영구 채팅 서버 풀에 대 한 간단한 **표시 이름을** 정의 합니다. 사용자 지정 클라이언트, 특히 영구 채팅 서버 풀이 여러 개 있는 경우에는 표시 이름을 사용 하 여 대화방을 구분할 수 있습니다.

5.  영구 채팅 서버가 Lync Server 프런트 엔드 서버와 통신 하는 데 사용 하는 포트를 정의 합니다. 기본 포트는 5041입니다.

6.  조직에 준수 지원이 필요한 경우에는 **준수 사용** 확인란을 선택합니다. 선택 하는 경우 영구 채팅 서버 준수 서비스가 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 설치 됩니다. 영구 채팅 서버에 대 한 준수를 위해 SQL Server 백 엔드 서버를 선택 하 라는 메시지가 표시 됩니다.

7.  영구 채팅 서버 풀에 대해 사이트 선호도를 할당 합니다. 이 **풀을 \<사이트 SiteName\> 에 기본값으로 사용** 확인란을 선택 하거나이 **풀을 모든 사이트의 기본값으로 사용** 하 여이 영구 채팅 서버 풀을 현재 사이트 또는 모든 사이트의 기본 풀로 지정 합니다. Lync 2013 클라이언트를 사용 하 여 대화방을 만들고 관리 하는 경우에는 사용자 사이트와 연결 된 기본 풀이 대화방 만들기 및 관리 환경에서 사용 되어 대화방 만들기 및 관리 작업을 해당 풀로 라우팅할 수 있습니다. 이는 영구 채팅 서버 풀을 여러 개 배포 했으며 영구 채팅 서버의 대화방 만들기 및 관리 기능을 사용 하려는 경우에만 적용 됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 대화방 만들기 및 관리 기능을 사용자 지정할 수 있습니다.<BR>재해 복구를 위해 SQL Server 백업 데이터베이스를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 configure <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">영구 채팅 서버 구성에서 Lync Server 2013의 고가용성 및 재해 복구</A> 를 참조 하십시오.

    
    </div>

8.  다음 중 하나를 수행 하 여 **영구 채팅 서버 백 엔드에 대 한 SQL 저장소 (대화방 콘텐츠가 저장 되는 위치)** 를 정의 합니다.
    
      - 기존 SQL Server 데이터베이스를 사용 하려면 드롭다운 목록에서 사용 하려는 SQL Server 데이터베이스의 이름을 클릭 합니다.
    
      - 새 SQL Server 데이터베이스를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 sql 저장소 정의**에서 다음을 수행 합니다.
    
    <!-- end list -->
    
      - **Sql SERVER fqdn**에서 새 sql server 데이터베이스를 만들 sql SERVER의 FQDN을 지정 합니다.
    
      - 기본 인스턴스를 사용하려는 경우 **기본 인스턴스**를 선택하고, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 선택해서 사용하려는 인스턴스를 지정합니다.

9.  준수를 사용 하도록 설정한 경우 SQL Server 준수 데이터베이스를 정의 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 영구 채팅 서버 데이터베이스 및 영구 채팅 서버 준수 데이터베이스에 대 한 고가용성을 위해 SQL Server 미러를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서에서 " <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성</A> "을 참조 하십시오.

    
    </div>

10. 파일 저장소를 정의합니다. 파일 저장소는 파일 저장소에 업로드된 파일의 복사본이 저장되는 폴더입니다(예: 채팅방에 게시된 첨부 파일 저장). 다중 서버 영구 채팅 서버 토폴로지의 경우 UNC (범용 명명 규칙) 경로 여야 합니다. 단일 서버 영구 채팅 서버 토폴로지의 경우 로컬 파일 경로일 수 있습니다.
    
    기존 파일 저장소를 사용하려면 다음 단계를 수행합니다.
    
      - **파일 서버 FQDN**에 새 파일 저장소를 만들려는 파일 저장소의 FQDN을 지정합니다.
    
      - **파일 공유**에 사용하려는 파일 공유를 지정합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 파일 저장소를 만들기 전에 토폴로지 작성기에서 파일 저장소를 정의할 수 있지만 토폴로지를 게시 하기 전에 정의한 정의 된 위치에 파일 저장소를 만들어야 합니다.

    
    </div>

11. 이 영구 채팅 서버 풀의 다음 홉으로 사용할 프런트 엔드 서버 풀을 선택 합니다. 영구 채팅 서버 요청을이 풀로 라우팅할 수 있는 프런트 엔드 서버 풀입니다.

12. 구성을 저장하려면 **마침**을 클릭합니다. 영구 채팅 서버 풀은 토폴로지 작성기와 함께 특정 풀 설정을 함께 표시 합니다.
    
    이제 영구 채팅 서버에 업데이트 된 토폴로지를 게시 하려면 배포 설명서의 [Lync Server 2013에서 업데이트 한 토폴로지 게시](lync-server-2013-publish-the-updated-topology.md) 를 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > 토폴로지 작성기가 이미 열려 있으면 <A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013의 업데이트 된 토폴로지 게시</A> 에서 3 단계를 진행 하 여 업데이트 된 토폴로지 게시를 시작할 수 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

