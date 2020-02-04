---
title: 'Lync Server 2013: 새 영구 채팅 서버 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Lync Server 2013의 새 영구 채팅 서버 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

Lync Server 2013, 영구 채팅 서버를 사용 하면 시간에 따라 유지 되는 단체의 토픽 기반 대화에 참여할 수 있습니다. 영구 채팅 서버는 조직에서 다음을 수행할 수 있도록 지원 합니다.

  - 지리적으로 분산 된 팀과 부서간 업무 흐름도 간의 의사 소통 개선

  - 정보 인식 및 참가

  - 확장 된 조직과의 통신 개선

  - 정보 오버 로드 줄이기

  - 정보 인식 향상

  - 중요 한 지식 및 정보의 dispersion 증가

Lync Server 2013, 영구 채팅 서버는 Microsoft Office 365에서 사용할 수 없습니다. 현재 온-프레미스 Lync 2013 고객 에게만 제공 됩니다.

Lync 2013에서 영구 채팅 기능이 Lync 2013 클라이언트에 통합 되었습니다. 따라서 사용자는 Lync 2013 클라이언트에서 인스턴트 메시징/현재 상태, 오디오/비디오, 회의 및 영구 채팅에 액세스할 수 있습니다. Lync 2013 클라이언트에 대 한 자세한 내용은을 참조 <http://go.microsoft.com/fwlink/p/?linkid=270877>하세요.

이 항목에서는 다음을 포함 하 여 Lync Server 2013, 영구 채팅 서버 및 이전 버전 (Microsoft Lync Server 2010, 그룹 채팅)의 새 버전 간 기능 변경 사항에 대해 설명 합니다.

  - Lync Server 제어판에서 관리 환경을 제공 하 고 그룹 채팅 관리 도구 제거

  - 그룹 채팅 구성 도구를 제거 하 여 영구 채팅 서버의 구성 설정을 토폴로지 작성기에 통합

  - 이전 버전의 영구 채팅 서버에서 쉽게 마이그레이션 및 업그레이드

  - 고가용성 및 재해 복구 솔루션 제공

최신 버전의 영구 채팅 서버에 대 한 자세한 내용은 다음을 참조 하세요.

  - 영구 채팅 기능에 대 <http://go.microsoft.com/fwlink/p/?linkid=270945> 한 자세한 목록과 작동 방식, 영구 채팅 서버를 실행 하는 동안 사용 하는 방법 등을 제공 하는 영구 채팅 도움말입니다.

  - [Lync server 2013의 영구 채팅 서버 계획에 대 한 자세한](lync-server-2013-planning-for-persistent-chat-server.md) 내용은 다음 문서를 참조 하세요. [lync Server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) 배포 설명서의 [Lync server 2010, 그룹 채팅 또는 Office Communications server 2007 R2 그룹 채팅, lync Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) 에 대 한 영구 채팅 서버, 운영 설명서에서 지속적인 채팅 서버로의 관리, [설정](managing-lync-server-2013-persistent-chat-server.md) 2013에 대 한 지침을 제공 하는 모든 정보 2013 영구 채팅 서버.

  - 영구 채팅 서버 문서 .msi 파일 (Windows Installer 파일)을 통해 사용자는 영구 채팅 서버에 대 한 종합적인 오프 라인 설명서에 액세스할 수 있습니다.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>영구 채팅 서버의 키 토폴로지 변경 사항

영구 채팅 서버에 대 한 다음과 같은 상위 수준의 변경 사항에는 다음이 포함 됩니다.

영구 채팅 서버는 이제 서버 역할입니다. Microsoft Lync Server 2010에서 그룹 채팅 서버는 Microsoft Lync Server 2010 용 타사 신뢰할 수 있는 응용 프로그램입니다. 토폴로지 작성기를 사용 하 여 Lync Server 2013 토폴로지에 영구 채팅을 추가할 수 있습니다. Lync Server 2013에서 영구 채팅 서버 기능은 다음과 같은 세 가지 새로운 서버 역할을 사용 하 여 구현 됩니다.

  - **PersistentChatService:** 영구 채팅에 대 한 프런트 엔드 역할입니다. Standard Edition 배포에서 영구 채팅 서버 서비스 역할은 다른 Lync Server 역할과 같이 부트스트래퍼가 배포 하는 스탠더드 버전 서버에 collocated 됩니다. Enterprise Edition 배포에서 영구 채팅 서비스 역할은 다른 Lync Server 역할과 같은 부트스트래퍼를 통해 독립 실행형 컴퓨터에 배포 됩니다.

  - **PersistentChatStore:** 모든 채팅 콘텐츠가 저장 되는 영구 채팅 콘텐츠 데이터베이스에 해당 하는 백 엔드 서버입니다.

  - **PersistentChatComplianceStore:** 모든 규정 준수 이벤트가 저장 되는 영구 채팅 준수 데이터베이스에 해당 하는 백 엔드 서버 역할입니다.

이러한 영구 채팅 서버 역할은 선택 사항이 며, 종합적인 영구 채팅 서버 기능을 원하는 고객 에게만 설치 됩니다. **PersistentChatComplianceStore** 역할은 영구 채팅 준수를 배포 하기로 선택 하는 경우에만 필요 합니다.

**PersistentChatService** 역할은 다음 두 가지 서비스를 실행 합니다.

  - 영구 채팅 서비스

  - 영구 채팅 준수 서비스

이러한 서비스는 각 영구 채팅 서버에서 실행 되도록 하는 것이 다중 서버 영구 채팅 서버 풀에서 높은 가용성을 제공 합니다.

또한 영구 채팅방에서 파일 업로드 및 다운로드를 지원 하기 위해 지속적인 채팅 서버에는 웹 서비스가 포함 되어 있습니다. 이전에이 서비스는 영구 채팅 서버, 프런트 엔드 서버, 필요한 IIS (인터넷 정보 서비스)를 필수 구성 요소로 설치 하는 collocated 되었습니다. Lync Server 2013 영구 채팅 서버에서는 Lync Server 2013 프런트 엔드 서버를 사용 하 여 파일 업로드/다운로드 웹 서비스를 collocated 수 있습니다. 부작용으로 서, IIS (인터넷 정보 서비스)는 더 이상 영구 채팅 서버의 선행 조건이 아닙니다. 파일 업로드/다운로드 웹 서비스는 IIS (인터넷 정보 서비스) 관리자에서 **PersistentChat** 로 식별 됩니다.

<div>


> [!IMPORTANT]  
> <STRONG>PersistentChatService</STRONG> 역할은 Lync server 2013&nbsp;프런트 엔드 서버와 동일한 서버에서 실행할 수 있습니다 (해당 프런트 엔드 서버가 표준 Edition&nbsp;프런트 엔드 서버인 경우에만 해당). <STRONG>PersistentChatService</STRONG> 역할은 Lync server 2013&nbsp;프런트 엔드 서버와 독립적으로 실행할 수 없습니다. Lync Server 2013 배포의 컨텍스트에서만 설치 될 수 있습니다.



</div>

영구 채팅 서버에서 조회 서비스는 제거 되었습니다. Lync Server 2010의 그룹 채팅에서 조회 서비스는 모든 그룹 채팅 서버 프런트 엔드 서버에서 실행 되며 채널 서버 중 하나로 라우팅을 수행 합니다. Lync Server 2013는 연락처 개체를 사용 하 여 라우팅에 의존 하며, 각 영구 채팅 서버 풀이 Lync Server 프런트 엔드 서버에서 해당 영구 채팅 서버 풀로 요청을 식별 하 고 라우팅하는 데 사용 되는 contact 개체로 표시 됩니다. 풀에서 영구 채팅 서버를 실행 하는 컴퓨터 중 하나입니다.

Lync Server 2013에는 준수 서비스 수정 사항이 있습니다.

  - Lync Server 2010에서 준수 서비스는 독립 실행형 (비 collocated) 및 단일 서버 에서만 실행 됩니다. 이제 준수 서비스는 영구 채팅 서비스와 함께 모든 영구 채팅 서버 프런트 엔드 서버에서 실행 되며,이를 통해 다중 서버 영구 채팅 서버 풀에서 높은 가용성을 제공 합니다. 규정 준수 데이터베이스에서 데이터를 추출 하 고 다른 시스템 중 하나 (XML 파일, Exchange에서 호스트 된 아카이브 등)로 단일 준수 어댑터를 구성할 수 있습니다. 영구 채팅 서버에는 XML 어댑터가 포함 됩니다.

  - 영구 채팅 서비스 및 각 영구 채팅 서버 프런트 엔드 서버에서 공유 되는 메시지 큐 (MSMQ 라고도 함) 큐는 이제 두 서비스 에서만 공유 하는 개인 큐입니다. 모든 준수 서비스는 동일한 준수 백 엔드 데이터베이스에 기록 됩니다. 또한 해당 데이터베이스에서 모두 읽었으며 해당 사용자의 어댑터 인스턴스에 데이터를 보내는 목적으로 사용할 수 있습니다. 규정 준수 백 엔드 서버는 새 백 엔드 서버 역할로 표시 됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이전 버전과 마찬가지로 모든 준수 데이터는 한 번만 처리 됩니다. 다양 한 Lync Server 2013, 영구 채팅 서버 컴퓨터에서 실행 되는 규정 준수 서비스에서 호출한 어댑터 인스턴스가 데이터를 처리할 수 있습니다. 영구 채팅 서버에서 어댑터 인스턴스 중 하나가 데이터를 처리할 수 있습니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 메시지 큐 설치에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치</A> 를 참조 하세요.

    
    </div>

Lync Server 2013에는 고가용성 및 재해 복구가 모두 개선 되었습니다.

  - 고가용성 개선: SQL Server 미러링은 데이터 센터 내에서 영구 채팅 서버 콘텐츠 데이터베이스와 영구 채팅 준수 데이터베이스에 높은 가용성을 제공 하는 데 사용 됩니다 (사이트 내).

  - 재해 복구 개선 사항: 영구 채팅 서버는 두 사이트 (즉, 토폴로지에 있는 단일 논리 풀)에서 단일 영구 채팅 서버 풀을 물리적으로 확장 가능 하 게 하는 스트레치 된 풀 아키텍처를 지원 합니다. 두 사이트에 위치 함). 사이트 간 재난 복구에 사용 되는 SQL Server 로그 전달.

고가용성 및 장애 복구에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 고가용성 및 재해 복구용으로 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 참조 하세요.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>영구 채팅 서버의 주요 관리 및 관리 변경 사항

Lync Server 2013을 통해 다음을 제공 하 여 영구 채팅 서버를 더욱 쉽게 관리 하 고 관리할 수 있습니다.

  - 통합 된 관리 및 관리. Lync Server 2013을 통해 Lync 관리자에 게 이미 익숙한 도구를 사용 하 여 영구 채팅 서버를 쉽게 관리 하 고 관리할 수 있습니다. 영구 채팅 서버에는 Lync Server 제어판과 통합 된 관리 사용자 인터페이스 환경이 포함 되어 있어 이전 버전의 그룹 채팅 서버 사용자 인터페이스에 대 한 성능 문제를 해결할 수 있습니다. 또한 영구 채팅 서버에는 영구 채팅 서버 범주를 관리 하 고 관리 하는 Windows PowerShell cmdlet 모음, 채팅방 삭제 및 오래 된 콘텐츠 제거를 비롯 한 추가 기능이 포함 되어 있습니다.

  - 간단한 관리 모델 Lync Server 2013에서 다음 주요 고객 요구 사항을 해결 하 여 영구 채팅 서버 모델을 변경 하 고 단순화 했습니다.
    
      - 범위 및 범주에 대 한 복잡 하 게 중첩 된 계층 구조를 제거 합니다.
    
      - 영구 채팅 서버로 마이그레이션하도록 계획 중인 현재 MindAlign 고객에 대해 거부 목록 및 허용 목록 (범위)을 정의 하는 지원.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전과의 사용자 역할에 대 한 차이점은 무엇 인가요?

Lync Server 2010의 그룹 채팅에는 사용자 관리자 역할이 있으며, 채팅방 관리자 역할 및 추가 기능을 관리할 수 있는 Lync Server 관리자 역할이 있습니다. 영구 채팅 서버는 단순히 영구 채팅 관리자 역할을 제공 합니다 (다른 Lync와 유사). 서버 역할 기반 액세스 제어 (RBAC) 역할. 이 RBAC 역할의 구성원 인 사용자는 채팅방, 추가 기능, 범주를 관리 하 고 (따라서 이러한 범주에 대 한 사용자 액세스 권한 획득) 영구 채팅 서버 풀을 구성할 수 있습니다.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전의 채팅방 범주에 대 한 차이점은 무엇 인가요?

채팅방 범주는 더 이상 중첩할 수 없으며 루트 범주는 더 이상 수정할 수 없습니다. AllowedMembers/DeniedMembers는 레거시 그룹 채팅 서버 버전에 사용 되는 범위를 구성 합니다 (거부 목록 지정을 지원 하지 않는다는 점만 제외). 중첩 범주가 없기 때문에 범위를 더 이상 재정의할 수 없습니다. Lync Server 2013의 영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다. 채팅방 범주를 만들고 관리 하는 과정에서 영구 채팅 관리자는 특정 범주에 대 한 채팅방의 구성원/작성자로 액세스할 수 있는 사용자 (Active Directory 그룹/컨테이너/사용자)를 구성할 수 있습니다. 영구 채팅 관리자는 범주에 DeniedMembers를 추가할 수 있으며, 허용 목록에 대 한 명시적 제외가 됩니다. DeniedMembers는 AllowedMembers에 포함된 항목에 우선합니다.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전의 채팅방 속성에 대 한 차이점은 무엇 인가요?

Lync Server 2013, 영구 채팅 서버에 열려 있는 채팅방의 새로운 개념이 있습니다. 허용 된 모든 구성원은 독점 구성원 없이 채팅방에 참가할 수 있습니다.

이전 버전의 영구 채팅 서버에 포함 된 다음 채팅방 속성이 제거 되었습니다.

  - 주제: 이제 채팅방에 대 한 설명만 있습니다.

  - 새 구성원 목록 만들기: 영구 채팅 서버에서 모든 채팅방은 빈 구성원으로 시작 되며 허용 된 회원에 게 equaling 구성원 자격을 최대화할 수 있습니다.

  - 파일 업로드: 파일 업로드/다운로드가 허용 되는지 여부를 제어 하기 위해 채팅방 별로 설정 하는 데 사용 됩니다. 이제 범주 수준만 설정 하 고 해당 범주의 모든 채팅방에 적용 됩니다.

  - 채팅 기록: 채팅 기록의 사용 가능 여부를 제어 하기 위해 채팅방 별로 설정 하는 데 사용 되지만, 이제 범주 수준 에서만 설정 되 고 해당 범주의 모든 채팅방에 적용 됩니다.

  - 초대: 룸은 항상 범주에 대 한 초대 설정을 상속 합니다. 또는 룸에서 기능을 끌 수 있습니다. 범주가 이전에 초대를 해제 하도록 설정 된 경우에는 채팅방이 초대를 켤 수 없습니다.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전의 정책에 대 한 차이점은 무엇 인가요?

영구 채팅 서버에는 사용자/풀/사이트/전역 설정에 따라 영구 채팅을 사용 하는 새로운 Lync 정책이 있습니다. Lync 2013 클라이언트에서는 영구 채팅을 위해 정책에 따라 설정 되는 사용자 (직접 또는 풀/사이트/전역 설정)에 대해서만 영구 채팅 환경을 사용할 수 있습니다.

이전 버전의 그룹 채팅 서버에는 Lync Server 정책에 통합 된 정책이 없었습니다. 사용자 당 및 범주/방에 따라 사용자에 게 **파일 업로드** 기능을 사용 하 여 사용자를 사용자 관리자 또는 채팅방 관리자로 설정 하거나 파일을 업로드 하는 사용자의 기능을 구성할 수 있습니다. 영구 채팅 서버 **파일 업로드** 기능은 범주 당 한 가지입니다.

</div>

<div>

## <a name="logging"></a>로깅하

영구 채팅 서버 및 System Center Operations Manager에 대 한 로깅은 Lync Server 2013 추적 로깅에 통합 되어 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

