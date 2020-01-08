---
title: 'Lync Server 2013: 지원되는 서버 마이그레이션 경로 및 동시 사용 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33b2ce878fef53f444e3834e8b1cd40286c24b0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Lync Server 2013의 지원되는 서버 마이그레이션 경로 및 동시 사용 시나리오

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-16_

Lync Server 2013는 다음 중 한 가지 방법으로 마이그레이션을 지원 합니다.

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

이러한 이전 버전을 모두 실행 하는 환경에서 마이그레이션하는 것은 지원 되지 않습니다. Microsoft Office Communications Server 2007 또는 Live Communications Server 2005 등 이전 버전에서의 마이그레이션은 지원 되지 않습니다. 이전 배포에 그룹 채팅이 포함 된 경우 별도로 마이그레이션해야 합니다.

<div>

## <a name="migration-methods"></a>마이그레이션 방법

모든 Lync Server 토폴로지 및 서버 역할의 마이그레이션이 지원 됩니다. 표준 버전 서버와 Enterprise Edition server를 포함 하 여 한 토폴로지에서 다른 토폴로지로 마이그레이션할 수 있습니다.

Lync 서버 2013는 다음 마이그레이션 메서드만 지원 합니다.

  - <span></span>  
    **나란히 마이그레이션.** 병렬 마이그레이션에서는 Lync Server 2013이 기존 Microsoft Lync Server 2010 또는 Office Communications Server 2007 R2 배포와 함께 배포 된 다음 새 서버로 작업을 전송 하 고 사용자를 Lync Server 2013로 이동 합니다. 이 방법을 사용 하려면 마이그레이션 도중 하드웨어 및 소프트웨어를 비롯 한 추가 서버 플랫폼 및 시스템 이름 및 풀 이름이 새 구성에 따라 달라 집니다. 이전 버전으로 롤백하는 데 필요한 경우 이전 서버로 작업을 다시 이동할 수 있습니다.

Active Directory 도메인 서비스 포리스트 간 마이그레이션은 지원 되지 않습니다.

권장 되는 마이그레이션 경로는 단계별 방법입니다. 구성 요소 배포의 적절 한 단계을 포함 하 여 이전 릴리스에서 마이그레이션하는 방법에 대 한 자세한 내용은 마이그레이션 설명서의 다음 항목을 참조 하세요.

  - [Lync Server 2010에서 Lync Server 2013으로 마이그레이션](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에서 Lync Server 2013, 영구 채팅 서버로 마이그레이션](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>공존 시나리오

Lync Server 2013는 Lync Server 2010 배포 또는 Office Communications Server 2007 R2 배포의 구성 요소와 공존할 수 있습니다. Lync Server 2010 및 Office Communications Server 2007 R2를 둘 다 사용 하 여 Lync Server 2013을 동시에 배포할 수 있습니다 (모든 세 버전의 동시 배포).

이전 Lync Server 2010 또는 Office Communications Server 2007 R2 배포가 일시적으로 새 Lync Server 2013 배포를 사용 하 여 진행 되는 동안에는 혼합 버전 라우팅에 대 한 지원이 제한 됩니다. 자세한 내용은 마이그레이션 설명서를 참조 하세요.

Lync Server 2013 데이터베이스 인스턴스에 대해 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012를 실행 하는 별개의 컴퓨터를 사용 해야 합니다. Lync server 2010 또는 Office Communications Server 2007 R2 프런트 엔드 풀에 사용 하는 Lync Server 2013 프런트 엔드 풀에 대해서도 동일한 SQL Server 인스턴스를 사용할 수 없습니다. Lync server 2010 또는 Office Communications Server 2007 R2가 배포 된 배포에 대 한 토폴로지 작성기에서 Lync Server 2013을 정의 하 고 구성 하는 경우에는 토폴로지 작성기를 통해 이미 사용 중인 Lync Server 2013의 인스턴스를 정의할 수 없습니다. 토폴로지.

토폴로지 작성기에는 "서버의 \[\] SQL server FQDN에 sql 인스턴스 호스팅 역할 ' 사용자 저장소가 이미 포함 되어 있습니다." 라는 메시지가 표시 됩니다.

<div>


> [!NOTE]  
> Lync Server 2013 배포에 새로운 서버 역할을 배포 하려는 경우 먼저 마이그레이션 설명서 및 배포 설명서에 설명 된 대로 기존 배포를 업그레이드 한 다음 아래에 설명 된 대로 새 서버 역할을 배포 해야 합니다. 계획 문서 및 배포 설명서입니다. 이전 버전의 그룹 채팅을 마이그레이션하는 경우 Lync Server 2010 또는 Office Communications Server 2007 R2의 다른 모든 구성 요소 마이그레이션 프로세스를 완료 한 후에 마지막으로 마이그레이션하십시오.



</div>

Lync Server 2010 또는 Office Communications Server 2007 R2 및 Lync Server 2013 구성 요소의 공존 및 마이그레이션에 대 한 자세한 공존 요구 사항 및 기타 자세한 내용은 마이그레이션 설명서의 [Lync server 2010에서 Lync server 2013로 마이그레이션](migration-from-lync-server-2010-to-lync-server-2013.md) 및 [Office Communications server 2007 R2에서 lync Server로의 마이그레이션을](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 참조 하세요. 클라이언트의 혼합 버전 지원에 대 한 자세한 내용은 [Lync Server 2013의 이전 배포에서 지원 되는 클라이언트](lync-server-2013-supported-clients-from-previous-deployments.md)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

