---
title: 'Lync Server 2013: 영구 채팅 서버용 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862635d091a216df61058c0f0ff00eaa9d32a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버용 구성 요소 및 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

영구 채팅 서버는 단일 서버 구성과 다중 서버 구성을 모두 지원 합니다. 또한 지속적인 채팅 서버는 Lync Server 2013 Standard Edition Server에서 실행할 수 있습니다. 이러한 구성은 다음 영구 채팅 서버 구성 요소 및 토폴로지로 구성 됩니다.

<div>

## <a name="persistent-chat-server-components"></a>영구 채팅 서버 구성 요소

최신 버전의 영구 채팅 서버를 설치 하려면 다음 구성 요소가 필요 합니다.

  - 영구 채팅 서버를 실행 하 고 다음 서비스를 제공 하는 하나 이상의 컴퓨터:
    
      - 영구 채팅 서비스
    
      - 준수를 사용 하도록 설정 된 규정 준수 서비스
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013에서 파일 업로드/다운로드에 대 한 영구 채팅 웹 서비스는 이제 Lync Server 2013&nbsp;프런트 엔드 서버와 collocated.<BR>채팅방 관리를 위한 영구 채팅 웹 서비스는 Lync Server 2013&nbsp;프런트 엔드 서버와도 collocated 됩니다.

    
    </div>

  - 채팅방 콘텐츠, 채팅방 및 범주가 저장 된 영구 채팅 콘텐츠 데이터베이스를 호스팅하기 위한 SQL Server 백 엔드 데이터베이스를 호스트 하는 서버 (미러링이 사용 되는 경우 둘 이상의 서버)
    
    <div>
    

    > [!NOTE]  
    > 백 엔드 데이터베이스에는 범주 및 생성 된 영구 채팅방에 대 한 정보를 포함 하 여 채팅 기록 데이터가 저장 됩니다.

    
    </div>

  - 준수를 사용 하는 경우 지속적인 채팅 준수 데이터베이스를 호스팅하기 위해 SQL Server 백 엔드 데이터베이스를 호스트 하는 서버 (미러링이 사용 되는 두 개 이상)가 저장 되며, 준수 이벤트 및 채팅 콘텐츠는 호환성을 위해 유지 됩니다.

별도의 컴퓨터 (예: 관리 콘솔)에서 영구 채팅 서버를 관리 하려면 컴퓨터의 Lync Server 제어판을 사용 합니다. 그런 다음 포리스트 루트에서 하나 이상의 글로벌 카탈로그 서버를 사용 하 여 Active Directory 도메인 서비스 도메인에이 컴퓨터를 배포 해야 합니다.

영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 [Lync server 2013의 영구 채팅 서버에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-persistent-chat-server.md), lync server [2013의 지원 되는 하드웨어](lync-server-2013-supported-hardware.md), 지원 가능성 설명서의 [lync server 2013에서 서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md) 에 대해 알아보세요.

</div>

<div>

## <a name="supported-collocation"></a>지원 되는 Collocation

Lync Server 2013는 특정 서버에서 여러 구성 요소를 실행 하 여 하드웨어 비용을 절약할 수 있는 융통성을 제공 하는 다양 한 collocation 시나리오를 지원 합니다 (소규모 조직의 경우). 또는 다른 서버에서 개별 구성 요소를 실행 하려면 확장성과 성능이 필요한 대규모 조직 구성 요소를 collocate 여부를 결정 하기 전에 확장성 요인을 고려해 야 합니다.

준수를 사용 하는 경우 지속적인 채팅 준수 서비스는 Lync Server 2013 프런트 엔드 서버를 사용 하 여 collocated 됩니다.

영구 채팅 서버는 Standard Edition 서버에 배포할 수 있습니다. 영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스가 로컬 SQL Server Express 백 엔드 서버의 스탠더드 버전 서버에서 collocated 수 있습니다. Collocated 수 있는 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 지원 되는 server collocation](lync-server-2013-supported-server-collocation.md) 을 참조 하세요.

Lync Server 2013 Enterprise Edition의 경우 엔터프라이즈 버전 서버에서 영구 채팅 서버를 collocated 수 없습니다. 영구 채팅 서버용 SQL Server 데이터베이스는 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버 데이터베이스와 collocated 수 있습니다. 영구 채팅 준수에 대 한 SQL Server 데이터베이스는 Enterprise Edition 풀의 백 엔드 서버 데이터베이스와 collocated 수 있습니다.

<div>


> [!IMPORTANT]  
> 영구 채팅 데이터베이스를 호스트 하는 서버는 다른 데이터베이스를 호스트할 수 있습니다. 그러나 다른 데이터베이스와 영구 채팅 데이터베이스를 collocating 하는 경우에는 여러 사용자의 메시지를 저장 하는 경우 영구 채팅 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 점에 주의 해야 합니다. 이 때문에 백 엔드 데이터베이스에서 영구 채팅 데이터베이스를 collocating 하지 않는 것이 좋습니다.



</div>

백 엔드 데이터베이스에 영구 채팅 데이터베이스를 collocate 경우 모든 데이터베이스에 대해 단일 SQL Server 인스턴스를 사용 하거나 각 데이터베이스에 대해 별도의 SQL Server 인스턴스를 사용 하 여 다음과 같은 제한 사항이 적용 될 수 있습니다.

  - SQL Server의 각 인스턴스에는 단일 백 엔드 데이터베이스와 단일 영구 채팅 데이터베이스만 포함 될 수 있습니다.

모든 서버 역할 및 데이터베이스의 collocation에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 지원 되는 server collocation](lync-server-2013-supported-server-collocation.md) 을 참조 하세요.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>영구 채팅 서버 토폴로지

영구 채팅 서버는 다음 토폴로지를 지원 합니다.

  - Lync Server 2013 Enterprise Edition 단일 서버 영구 채팅 서버 프런트 엔드 서버

  - Lync Server 2013 Enterprise Edition 다중 서버 영구 채팅 서버 프런트 엔드 서버

  - SQL Server Express를 사용 하는 Lync Server 2013 Standard Edition 서버

  - Lync Server 2013 Standard Edition 서버와 영구 채팅 서버는 다음 홉 서버로 표준 버전 서버를 사용 하는 별도의 서버에 있습니다.

토폴로지 작성기를 사용 하 여 Lync Server 2013 배포에 영구 채팅 서버를 추가할 수 있습니다. 토폴로지에 단일 서버 또는 다중 서버 영구 채팅 서버 풀을 추가할 수 있습니다.

<div>


> [!IMPORTANT]  
> 토폴로지 작성기를 사용 하 여 단일 서버로 영구 채팅 서버 풀을 만든 후에는 풀에 다른 서버를 추가할 수 없습니다.



</div>

<div>

## <a name="single-server-topology"></a>단일 서버 토폴로지

영구 채팅 서버용 최소 구성과 가장 간단한 배포는 단일 영구 채팅 서버 프런트 엔드 서버 토폴로지입니다. 이 배포에는 영구 채팅 서버를 실행 하는 단일 서버 (선택적으로 준수 서비스를 실행 하는 경우), SQL Server 데이터베이스를 모두 호스트 하는 서버, 준수 해야 하는 SQL Server 데이터베이스 등이 필요 합니다. 준수 데이터

<div>


> [!IMPORTANT]  
> 토폴로지 작성기에서 단일 서버 배포로 시작 되는 영구 채팅 서버 풀에는 다른 서버를 추가할 수 없습니다. 필요한 경우 나중에 서버를 추가할 수 있도록 단일 서버를 사용 하는 경우에도 다중 서버 풀 토폴로지를 사용 하는 것이 좋습니다.



</div>

다음 그림에는 단일 영구 채팅 서버 프런트 엔드 서버에 대 한 모든 필수 및 선택적 구성 요소 (준수)가 나와 있습니다.

**단일 영구 채팅 서버**

![Compliance Service를 사용하는 단일 서버 토폴로지](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Compliance Service를 사용하는 단일 서버 토폴로지")

</div>

<div>

## <a name="multiple-server-topology"></a>다중 서버 토폴로지

더 나은 용량과 안정성을 제공 하기 위해 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)에서 설명한 대로 다중 서버 토폴로지를 배포할 수 있습니다. 다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 4 대의 활성 컴퓨터가 포함 될 수 있습니다 (고가용성 및 재해 복구 구성은 최대 8 개까지 허용 되지만, 나머지 4 개는 활성 상태로 유지 될 수 있습니다). 각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대에서 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자를 지원 합니다. 다중 서버 토폴로지는 여러 서버에서 영구 채팅 서버를 호스트 하는 것을 제외 하 고 단일 서버 토폴로지와 동일 하며 더 높은 배율을 확장할 수 있습니다. 영구 채팅 서버를 실행 하는 여러 컴퓨터는 Lync Server 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있어야 합니다.

다음 그림은 영구 채팅 서버, 선택적 준수 서비스, 별도 규정 준수 데이터베이스를 실행 하는 여러 컴퓨터가 있는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.

**여러 영구 채팅 서버**

![다중 서버 토폴로지](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "다중 서버 토폴로지")

다중 서버 토폴로지는 서버 기능 풀링을 제공 합니다. 서버 풀에서 영구 채팅 서비스는 데이터를 통신 하 고 공유 합니다. 예를 들어 원래 하나의 영구 채팅 서비스에 게시 된 채팅 기록을 시스템의 모든 영구 채팅 서비스에서 사용할 수 있습니다. 하나의 영구 채팅 서비스를 통해 업로드 되는 파일은 영구 채팅 서비스에서 액세스할 수 있습니다. 사용자는 서로 다른 영구 채팅 서버 프런트 엔드 서버에 연결 되어 서로 채팅 하 고 통신할 수 있습니다.

TCP 8011의 기본 포트는 서버를 서버 풀에 연결 하 고 영구 채팅 서비스에서 자신과 관리 목적으로 통신 하는 데 사용 됩니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

