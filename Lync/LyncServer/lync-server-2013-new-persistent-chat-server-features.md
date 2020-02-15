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
ms.openlocfilehash: 5257490dc63e1626c0cdb6dcf7e6ce1f17e75cd1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Lync Server 2013의 새 영구 채팅 서버 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

Lync Server 2013, 영구 채팅 서버를 사용 하면 시간이 지남에 따라 지속 되는 단체 및 토픽 기반 대화에 참가할 수 있습니다. 영구 채팅 서버는 조직에서 다음을 수행 하는 데 도움이 될 수 있습니다.

  - 지리적으로 분산되고 업무가 연관된 팀 간의 통신을 향상시킵니다.

  - 보다 많은 구성원과 정보를 보다 많이 공유할 수 있습니다.

  - 조직 내외부에서 광범위하게 정보를 공유할 수 있습니다.

  - 효율적인 정보 공유로 정보 오버로드를 줄여 줍니다.

  - 정보 인식을 향상시킵니다.

  - 중요한 지식과 정보의 배포를 향상시킵니다.

Lync Server 2013, 영구 채팅 서버는 Microsoft Office 365에서 사용할 수 없습니다. 현재 온-프레미스 Lync 2013 고객 에게만 제공 됩니다.

Lync 2013에서는 영구 채팅 기능이 Lync 2013 클라이언트에 통합 되어 있습니다. 따라서 사용자는 Lync 2013 클라이언트에서 인스턴트 메시징/현재 상태, 오디오/비디오, 회의 및 영구 채팅에 액세스할 수 있습니다. Lync 2013 클라이언트에 대 한 자세한 내용은를 참조 <http://go.microsoft.com/fwlink/p/?linkid=270877>하세요.

이 항목에서는 새 버전의 Lync Server 2013, 영구 채팅 서버와 이전 버전 (Microsoft Lync Server 2010, 그룹 채팅) 간의 기능 변경 사항에 대해 설명 합니다.

  - Lync Server 제어판의 관리 환경을 제공 하 고 그룹 채팅 관리 도구 제거

  - 그룹 채팅 구성 도구를 제거 하 여 영구 채팅 서버에 대 한 구성 설정을 토폴로지 작성기에 통합

  - 이전 버전의 영구 채팅 서버에서 쉽게 마이그레이션 및 업그레이드

  - 고가용성 및 재해 복구 솔루션 제공

최신 버전의 영구 채팅 서버에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

  - 영구 채팅 기능의 자세한 목록과 <http://go.microsoft.com/fwlink/p/?linkid=270945> 작동 방식, 그리고 영구 채팅 서버를 실행 하는 동안 사용 하는 방법에 대 한 자세한 정보를 제공 하는 영구적 채팅 도움말입니다.

  - 계획 설명서에서 [Lync Server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) lync server 2008에서 [영구 채팅 서버 배포 배포](lync-server-2013-deploying-persistent-chat-server.md) 설명서, 2013 [Lync server 2010, 그룹 채팅 또는 Office Communications server 2007 R2 그룹 채팅에서 Lync Server 2013, 영구 채팅 서버](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) (마이그레이션 설명서) 및 작업 설명서에서 [Lync server 2013, 영구 채팅 서버 관리](managing-lync-server-2013-persistent-chat-server.md) , 모든 설정에 대 한 지침을 제공 합니다. 영구 채팅 서버

  - 영구 채팅 서버 설명서 .msi 파일 (Windows Installer 파일)을 사용 하면 영구 채팅 서버에 대 한 포괄적인 오프 라인 설명서에 액세스할 수 있습니다.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>영구 채팅 서버에 대 한 주요 토폴로지 변경 사항

영구 채팅 서버에 대 한 다음과 같은 높은 수준의 변경 사항에는 다음이 포함 됩니다.

영구 채팅 서버는 이제 서버 역할입니다. Microsoft Lync Server 2010에서 그룹 채팅 서버는 Microsoft Lync Server 2010에 대 한 타사 트러스트 응용 프로그램입니다. 토폴로지 작성기를 사용 하 여 Lync Server 2013 토폴로지에 영구 채팅을 추가할 수 있습니다. Lync Server 2013에서는 다음과 같은 세 가지 새 서버 역할을 사용 하 여 영구 채팅 서버 기능을 구현 합니다.

  - **PersistentChatService:** 영구 채팅에 대 한 프런트 엔드 역할입니다. Standard Edition 배포에서 영구 채팅 서버 서비스 역할은 다른 Lync Server 역할과 마찬가지로 부트스트래퍼가 배포 하는 Standard Edition 서버에 배치 된 됩니다. Enterprise Edition 배포에서 영구 채팅 서비스 역할은 다른 Lync Server 역할과 마찬가지로 부트스트래퍼에 의해 독립 실행형 컴퓨터에 배포 됩니다.

  - **PersistentChatStore:** 모든 채팅 콘텐츠가 저장 되는 영구 채팅 콘텐츠 데이터베이스에 해당 하는 백 엔드 서버입니다.

  - **PersistentChatComplianceStore:** 모든 준수 이벤트가 저장 되는 영구 채팅 준수 데이터베이스에 해당 하는 백 엔드 서버 역할입니다.

이러한 영구 채팅 서버 역할은 선택적 이며, 포괄적인 영구 채팅 서버 기능을 원하는 고객 에게만 설치 됩니다. **PersistentChatComplianceStore** 역할은 영구 채팅 준수를 배포 하도록 선택한 경우에만 필요 합니다.

**PersistentChatService** 역할은 다음과 같은 두 가지 서비스를 실행 합니다.

  - 영구 채팅 서비스

  - 영구 채팅 준수 서비스

이러한 서비스가 각 영구 채팅 서버에서 실행 되도록 하면 다중 서버 영구 채팅 서버 풀에서 이러한 서비스에 고가용성이 제공 됩니다.

또한 영구 채팅방에서 파일 업로드 및 다운로드를 지원 하기 위해 영구 채팅 서버에는 웹 서비스가 포함 되어 있습니다. 이전에는이 서비스를 필수 구성 요소로 설치 하기 위해 영구 채팅 서버, 프런트 엔드 서버 및 필요한 IIS (인터넷 정보 서비스)에 배치 된 되었습니다. Lync Server 2013 영구 채팅 서버에서 파일 업로드/다운로드 웹 서비스는 Lync Server 2013 프런트 엔드 서버와 배치 된 됩니다. 부작용으로, IIS (인터넷 정보 서비스)가 더 이상 영구 채팅 서버에 대 한 필수 구성 요소가 아닙니다. 파일 업로드/다운로드 웹 서비스는 IIS (인터넷 정보 서비스) 관리자에서 **atl-persistentchat** 로 식별 됩니다.

<div>


> [!IMPORTANT]  
> <STRONG>PersistentChatService</STRONG> 역할은 해당 프런트 엔드 서버가 Standard Edition&nbsp;&nbsp;프런트 엔드 서버인 경우에만 Lync server 2013 프런트 엔드 서버와 동일한 서버에서 실행 될 수 있습니다. <STRONG>PersistentChatService</STRONG> 역할은 Lync server 2013&nbsp;프런트 엔드 서버와 독립적으로 실행할 수 없습니다. Lync Server 2013 배포의 컨텍스트에서만 설치할 수 있습니다.



</div>

영구 채팅 서버에서는 조회 서비스가 제거 되었습니다. Lync Server 2010, 그룹 채팅에서 조회 서비스는 모든 그룹 채팅 서버 프런트 엔드 서버에서 실행 되 고 채널 서버 중 하나로 라우팅을 수행 했습니다. Lync Server 2013에서는 각 영구 채팅 서버 풀을 적절 한 영구 채팅 서버 풀로 식별 하 고 라우트 하기 위해 Lync Server 프런트 엔드 서버에서 사용 하는 연락처 개체로 표시 되는 연락처 개체를 사용 하 여 라우팅에 의존 합니다. 풀에서 영구 채팅 서버를 실행 하는 컴퓨터 중 하나입니다.

Lync Server 2013에는 준수 서비스 수정 사항이 있습니다.

  - Lync Server 2010에서는 준수 서비스가 독립 실행형 (배치 된) 및 단일 서버 에서만 실행 됩니다. 이제 준수 서비스는 영구 채팅 서비스와 함께 모든 영구 채팅 서버 프런트 엔드 서버에서 실행 되며, 따라서 다중 서버 영구 채팅 서버 풀에서 고가용성을 제공 합니다. 준수 데이터베이스에서 데이터를 추출 하 고 다른 시스템 중 하나 (XML 파일, Exchange 호스팅 보관 함 등)로 단일 준수 어댑터를 구성할 수 있습니다. 영구 채팅 서버에는 XML 어댑터가 포함 됩니다.

  - 영구 채팅 서비스와 각 영구 채팅 서버 프런트 엔드 서버의 준수 서비스에서 공유 되는 메시지 큐 (MSMQ 라고도 함) 큐는 이제 두 서비스에 의해서만 공유 되는 개인 큐입니다. 모든 준수 서비스가 동일한 준수 백 엔드 데이터베이스에 기록 합니다. 또한 어댑터의 인스턴스에 데이터를 전송 하기 위해 해당 데이터베이스에서 모두 읽습니다. 준수 백 엔드 서버는 새 백 엔드 서버 역할로 표시 됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이전 버전과 마찬가지로 모든 준수 데이터는 한 번만 처리 됩니다. 데이터는 다양 한 Lync Server 2013, 영구 채팅 서버 컴퓨터에서 실행 되는 준수 서비스에 의해 호출 되는 모든 어댑터 인스턴스에서 처리 될 수 있습니다. 영구 채팅 서버에서 어댑터 인스턴스 중 하나를 통해 데이터를 처리할 수 있습니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 메시지 큐를 설치 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">서버에 Lync Server 2013의 운영 체제 및 필수 구성 요소 소프트웨어 설치</A> 를 참조 하십시오.

    
    </div>

Lync Server 2013에서는 고가용성 및 재해 복구를 모두 개선할 수 있습니다.

  - 고가용성 향상: SQL Server 미러링은 데이터 센터 (현장)에서 영구 채팅 서버 콘텐츠 데이터베이스 및 영구 채팅 준수 데이터베이스에 대 한 고가용성을 제공 하는 데 사용 됩니다.

  - 향상 된 재해 복구 기능: 영구 채팅 서버는 단일 영구 채팅 서버 풀을 두 사이트, 즉 토폴로지의 단일 논리 풀에서 실제로 풀의 서버와 물리적으로 늘릴 수 있도록 하는 스트레치 된 풀 아키텍처를 지원 합니다. 두 사이트에 위치) 사이트 간 재해 복구를 위해 SQL Server 로그 전달이 사용 됩니다.

고가용성 및 재해 복구에 대 한 자세한 내용은 배포 설명서의 " [Lync server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) "을 참조 하십시오.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>영구 채팅 서버에 대 한 주요 관리 및 관리 변경 사항

Lync Server 2013에서는 다음을 제공 하 여 영구 채팅 서버를 보다 쉽게 관리 하 고 관리할 수 있게 되었습니다.

  - 통합 관리 및 관리 Lync Server 2013에서는 Lync 관리자에 게 이미 익숙한 도구를 사용 하 여 영구 채팅 서버를 보다 쉽게 관리 하 고 관리할 수 있습니다. 영구 채팅 서버에는 Lync Server 제어판과 통합 되어 이전 버전의 그룹 채팅 서버 사용자 인터페이스와 관련 된 성능 문제를 해결 하는 관리 사용자 인터페이스 환경이 포함 되어 있습니다. 또한 영구 채팅 서버에는 영구 채팅 서버 범주를 관리 하 고 관리 하는 Windows PowerShell cmdlet 모음, 영구 채팅 서버 대화방 (채팅방 삭제 및 더 이상 사용 되지 않는 콘텐츠 제거) 및 추가 기능이 포함 되어 있습니다.

  - 간소화 된 관리 모델 Lync Server 2013는 다음과 같은 주요 고객 요구 사항을 해결 하 여 영구 채팅 서버 모델을 변경 하 고 단순화 했습니다.
    
      - 범위 및 범주에 대 한 중첩 된 복잡 한 계층 구조를 제거 합니다.
    
      - 영구 채팅 서버로 마이그레이션할 현재 MindAlign 고객에 대해 거부 목록 및 허용 목록 (범위)을 정의할 수 있도록 지원 합니다.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전의 사용자 역할에 대 한 달라진 점은 무엇 인가요?

Lync Server 2010, 그룹 채팅에는 사용자 관리자 역할, 대화방 관리자 역할 및 추가 기능을 관리할 수 있는 Lync Server 관리자 역할이 있었습니다. 영구 채팅 서버는 단순히 영구 채팅 관리자 역할 (다른 Lync와 비슷함)을 제공 합니다. 서버 RBAC (역할 기반 액세스 제어) 역할) 이 RBAC 역할의 구성원 인 사람은 대화방, 추가 기능 및 범주를 관리 하 고 (따라서 이러한 범주에 대 한 사용자 액세스 권한 획득) 영구 채팅 서버 풀을 구성할 수 있습니다.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전의 채팅방 범주에는 어떤 차이가 있나요?

채팅방 범주는 더 이상 중첩 될 수 없으며 루트 범주는 더 이상 수정할 수 없습니다. AllowedMembers/DeniedMembers는 이전 그룹 채팅 서버 버전에서 사용 되는 범위를 구성 합니다 (거부 목록 지정은 지원 하지 않음). 중첩 된 범주가 없기 때문에 범위를 더 이상 재정의할 수 없습니다. Lync Server 2013의 영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다. 대화방 범주를 만들고 관리 하는 과정에서 영구 채팅 관리자는 특정 범주의 대화방에 대 한 구성원/작성자가 될 수 있는 보안 주체 (Active Directory 그룹/컨테이너/사용자)를 구성할 수 있습니다. 영구 채팅 관리자는 DeniedMembers을 범주에 추가할 수도 있으며, 이러한 항목은 허용 목록에 대 한 명시적 제외가 됩니다. DeniedMembers는 AllowedMembers에 포함된 항목을 재정의합니다.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전의 대화방 속성에 대 한 다양 한 정보

Lync Server 2013, 영구 채팅 서버에는 열려 있는 대화방의 새로운 개념이 있습니다. 허용 된 모든 구성원은 단독 구성원 자격 없이 대화방에 참가할 수 있습니다.

이전 버전의 영구 채팅 서버에 포함 된 다음과 같은 대화방 속성이 제거 되었습니다.

  - 항목: 이제 대화방에 설명이 있습니다.

  - 새 구성원 목록 만들기: 영구 채팅 서버에서 모든 대화방은 빈 구성원으로 시작 되며 허용 되는 구성원에 게 equaling 멤버 자격을 최대화할 수 있습니다.

  - 파일 업로드: 대화방 당 설정으로 파일 업로드/다운로드가 허용 되는지 여부를 제어 하는 데 사용 됩니다. 이제 범주 수준만 설정 되며 해당 범주의 모든 채팅방에 적용 됩니다.

  - 채팅 기록: 채팅 기록이 사용 하도록 설정 된 경우이를 제어할 수 있도록 대화방 별로 설정 하는 데 사용 되지만 이제 범주 수준 에서만 설정 되며 해당 범주의 모든 채팅방에 적용 됩니다.

  - 초대: 룸은 항상 범주에 대 한 초대 설정을 상속 합니다. 또는 대화방에서 기능을 끌 수 있습니다. 범주가 이전에 초대로 설정 된 경우에는 대화방에서 초대를 켤 수 없습니다.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>이전 그룹 채팅 서버 버전의 정책에는 어떤 차이가 있나요?

영구 채팅 서버에는 사용자/풀/사이트/전역 설정에 따라 영구 채팅을 사용 하 여 새로운 Lync 정책이 사용 하도록 설정 되어 있습니다. Lync 2013 클라이언트에서 영구 채팅 환경은 영구 채팅에 대 한 정책에 따라 직접 또는 풀/사이트/전역 설정을 통해 사용 하도록 설정 된 사용자만 사용할 수 있습니다.

이전 버전의 그룹 채팅 서버에는 Lync Server 정책에 통합 된 정책이 없었습니다. 사용자별 및 범주별/대화방 별로 사용자 당 **파일 업로드** 기능을 사용 하 여 사용자를 사용자 관리자로 지정 하거나, 대화방 관리자로 만들거나, 파일을 업로드 하는 사용자 기능을 구성할 수 있습니다. 영구 채팅 서버 **파일 업로드** 기능은 범주별로만 구성 됩니다.

</div>

<div>

## <a name="logging"></a>기록을

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

