---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 구성 요소 및 토폴로지'
description: 'Lync Server 2013: 영구 채팅 서버에 대 한 구성 요소 및 토폴로지'
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
ms.openlocfilehash: 937b3d6f2716d9471e61cffd651847f6de9d83f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576814"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버에 대 한 구성 요소 및 토폴로지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

영구 채팅 서버는 단일 서버 구성과 다중 서버 구성을 모두 지원 합니다. 영구 채팅 서버는 Lync Server 2013 Standard Edition Server 에서도 실행할 수 있습니다. 이러한 구성은 다음과 같은 영구 채팅 서버 구성 요소 및 토폴로지로 구성 됩니다.

<div>

## <a name="persistent-chat-server-components"></a>영구 채팅 서버 구성 요소

최신 버전의 영구 채팅 서버를 설치 하려면 다음 구성 요소가 필요 합니다.

  - 영구 채팅 서버를 실행 하며 다음 서비스를 제공 하는 하나 이상의 컴퓨터:
    
      - 영구 채팅 서비스
    
      - 준수를 사용 하도록 설정 된 경우 설정 되는 준수 서비스
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013에서 파일 업로드/다운로드를 위한 영구 채팅 웹 서비스는 이제 Lync Server 2013 프런트 엔드 서버를 사용 하 여 배치 된 &nbsp; .<BR>또한 대화방 용 영구 채팅 웹 서비스는 Lync Server 2013 프런트 엔드 서버를 사용 하 여 배치 된 됩니다 &nbsp; .

    
    </div>

  - 대화방 콘텐츠, 대화방 및 범주가 저장 되는 영구 채팅 콘텐츠 데이터베이스를 호스팅하기 위한 SQL Server 백 엔드 데이터베이스를 호스트 하는 서버 (미러링이 사용 되는 경우 둘 이상의 서버)
    
    <div>
    

    > [!NOTE]  
    > 백 엔드 데이터베이스에는 범주 및 만들어지는 영구 채팅방에 대 한 정보를 비롯 하 여 채팅 기록 데이터가 저장 됩니다.

    
    </div>

  - 규정 준수를 사용 하도록 설정 하면 영구 채팅 준수 데이터베이스 호스팅을 위한 SQL Server 백 엔드 데이터베이스를 호스트 하는 서버 (미러링이 사용 되는 경우 둘 이상의 서버)가 저장 되며, 준수 이벤트 및 준수 목적에 대 한 채팅 콘텐츠를 저장할 수 있습니다.

관리 콘솔과 같은 별도의 컴퓨터에서 영구 채팅 서버를 관리 하려면 컴퓨터에서 Lync Server 제어판을 사용 합니다. 그런 다음 포리스트 루트에 하나 이상의 글로벌 카탈로그 서버가 있는 Active Directory 도메인 서비스 도메인에이 컴퓨터를 배포 해야 합니다.

영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 lync server 2013, [지원 되는 하드웨어](lync-server-2013-supported-hardware.md)및 lync server 2013에서 lync server [2013의 서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md) [에서 영구 채팅 서버에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-persistent-chat-server.md)참조 하세요.

</div>

<div>

## <a name="supported-collocation"></a>지원되는 배치

Lync Server 2013에서는 한 서버에서 여러 구성 요소를 실행 하거나 (소규모 조직이 있는 경우) 각 서버에서 개별 구성 요소를 실행 하 여 하드웨어 비용을 절약할 수 있도록 하는 다양 한 위치 시나리오를 지원 합니다 (확장성과 성능이 필요한 대규모 조직이 있는 경우). 구성 요소를 배치할지 여부를 결정하기 전에 확장성 요인을 분명하게 고려해야 합니다.

준수를 사용 하도록 설정 된 경우 영구 채팅 준수 서비스는 Lync Server 2013 프런트 엔드 서버를 사용 하 여 배치 된 됩니다.

Standard Edition 서버에 영구 채팅 서버를 배포할 수 있습니다. 영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스는 로컬 SQL Server Express 백 엔드 서버의 Standard Edition 서버에서 배치 된 수 있습니다. 배치 된 수 있는 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.

Lync Server 2013 Enterprise Edition의 경우 Enterprise Edition 서버에서 영구 채팅 서버를 배치 된 수 없습니다. 영구 채팅 서버용 SQL Server 데이터베이스는 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버 데이터베이스와 배치 된 될 수 있습니다. 영구 채팅 준수에 대 한 SQL Server 데이터베이스는 Enterprise Edition 풀의 백 엔드 서버 데이터베이스와 배치 된 수도 있습니다.

<div>


> [!IMPORTANT]  
> 영구 채팅 데이터베이스를 호스트 하는 서버는 다른 데이터베이스를 호스트할 수 있습니다. 그러나 영구 채팅 데이터베이스를 다른 데이터베이스와 배치 하는 경우에는 여러 사용자에 게 메시지를 저장 하는 경우 영구 채팅 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 사실을 염두에 두어야 합니다. 따라서 영구 채팅 데이터베이스를 백 엔드 데이터베이스와 배치 않는 것이 좋습니다.



</div>

영구 채팅 데이터베이스에 백 엔드 데이터베이스를 함께 배치할 하는 경우 데이터베이스 중 일부 또는 전체에 대해 단일 SQL Server 인스턴스를 사용 하거나 다음과 같은 제한 사항과 함께 각 데이터베이스에 대해 별도의 SQL Server 인스턴스를 사용할 수 있습니다.

  - 각 SQL Server 인스턴스는 단일 백 엔드 데이터베이스 및 단일 영구 채팅 데이터베이스만 포함할 수 있습니다.

모든 서버 역할 및 데이터베이스의 배치에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>영구 채팅 서버 토폴로지

영구 채팅 서버는 다음 토폴로지를 지원 합니다.

  - Lync Server 2013 Enterprise Edition 단일 서버 영구 채팅 서버 프런트 엔드 서버

  - Lync Server 2013 Enterprise Edition 다중 서버 영구 채팅 서버 프런트 엔드 서버

  - SQL Server Express를 사용 하는 Lync Server 2013 Standard Edition 서버

  - Lync Server 2013 Standard Edition server 및 영구 채팅 서버는 다음 홉 서버로 Standard Edition server를 사용 하는 별도의 서버에 있습니다.

토폴로지 작성기를 사용 하 여 Lync Server 2013 배포에 영구 채팅 서버를 추가할 수 있습니다. 토폴로지에 단일 서버 또는 다중 서버 영구 채팅 서버 풀을 추가할 수 있습니다.

<div>


> [!IMPORTANT]  
> 토폴로지 작성기를 사용 하 여 단일 서버에서 영구 채팅 서버 풀을 만든 후에는 풀에 서버를 더 추가할 수 없습니다.



</div>

<div>

## <a name="single-server-topology"></a>단일 서버 토폴로지

영구 채팅 서버에 대 한 최소 구성 및 가장 간단한 배포는 단일 영구 채팅 서버 프런트 엔드 서버 토폴로지입니다. 이 배포를 사용 하려면 영구 채팅 서버를 실행 하는 단일 서버 (필요한 경우 준수 서비스를 실행 하는 경우), SQL Server 데이터베이스를 모두 호스트 하는 서버, 준수 해야 하는 경우 SQL Server 데이터베이스에서 준수 데이터를 저장 해야 합니다.

<div>


> [!IMPORTANT]  
> 토폴로지 작성기에서 단일 서버 배포로 시작 된 영구 채팅 서버 풀에는 서버를 더 추가할 수 없습니다. 필요한 경우 나중에 서버를 더 추가할 수 있도록 단일 서버를 사용 하는 경우에도 다중 서버 풀 토폴로지를 사용 하는 것이 좋습니다.



</div>

다음 그림에서는 준수와 함께 단일 영구 채팅 서버 프런트 엔드 서버에 대 한 토폴로지의 모든 필수 및 선택적 구성 요소를 보여 줍니다.

**단일 영구 채팅 서버**

![준수 서비스를 사용 하는 단일 서버 토폴로지](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "준수 서비스를 사용 하는 단일 서버 토폴로지")

</div>

<div>

## <a name="multiple-server-topology"></a>다중 서버 토폴로지

더 많은 용량과 안정성을 제공 하기 위해 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)에 설명 된 대로 다중 서버 토폴로지를 배포할 수 있습니다. 다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 활성 컴퓨터가 최대 4 개까지 포함 될 수 있습니다 (고가용성 및 재해 복구 구성의 경우 8 개까지 가능 하지만 4 개만 활성화 될 수 있으며 나머지 4 개는 대기 중에 있음). 각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대와 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자에 게 해당 합니다. 다중 서버 토폴로지는 다중 서버가 영구 채팅 서버를 호스트 하는 것을 제외 하 고는 단일 서버 토폴로지와 동일 하며 더 높은 규모를 높일 수 있습니다. 영구 채팅 서버를 실행 하는 여러 컴퓨터가 Lync Server 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있어야 합니다.

다음 그림에서는 영구 채팅 서버, 선택적 준수 서비스 및 별도의 준수 데이터베이스를 실행 하는 여러 컴퓨터를 사용 하는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.

**여러 영구 채팅 서버**

![다중 서버 토폴로지](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "다중 서버 토폴로지")

다중 서버 토폴로지는 서버 기능 풀링을 제공 합니다. 서버 풀에서는 영구 채팅 서비스가 데이터를 전달 하 고 공유 합니다. 예를 들어 원래 하나의 영구 채팅 서비스에 게시 된 채팅 기록을 시스템의 모든 영구 채팅 서비스에서 사용할 수 있습니다. 하나의 영구 채팅 서비스를 통해 업로드 되는 파일은 모든 영구 채팅 서비스에서 액세스할 수 있습니다. 사용자는 서로 다른 영구 채팅 서버 프런트 엔드 서버에 연결 하 고 채팅 하 여 서로 통신할 수 있습니다.

TCP 8011의 기본 포트는 서버를 서버 풀에 연결 하며 영구 채팅 서비스가 자신과 관리 목적으로 통신 하는 데 사용 됩니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

