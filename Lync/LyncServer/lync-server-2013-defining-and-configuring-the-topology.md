---
title: 'Lync Server 2013: 토폴로지 정의 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a443aaa7cf523e1cb02beb3d944ec53632732291
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 정의 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-14_

토폴로지 작성기를 사용 하 여 토폴로지를 정의 하 고 구성 합니다. 토폴로지 작성기에서는 로컬 Administrators 그룹의 구성원 이거나 도메인 관리자와 같은 권한이 부여 된 도메인 그룹 일 필요는 없습니다. 표준 사용자로 토폴로지를 정의할 수 있습니다. 최초 사용 시와 후속 편집 세션에서 토폴로지 작성기를 시작하면 토폴로지 작성기에서 현재 구성 문서를 로드할 위치를 선택하라는 메시지가 표시됩니다. 다음 옵션을 선택할 수 있습니다.

  - 기존 배포에서 토폴로지 다운로드

  - 로컬 파일에서 토폴로지 열기

  - 새 토폴로지

이미 토폴로지를 정의 했 고 중앙 관리 저장소를 설정한 경우 기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다. 그러면 토폴로지 작성기에서 데이터베이스를 읽고 현재 정의를 검색합니다. 기존 중앙 관리 저장소를 보유 하 고 있는 경우 항상이 옵션을 선택 해야 합니다.

중앙 관리 저장소를 설정 하지 않은 경우 이전에 저장 한 구성을 편집 하려면 로컬 파일에서 토폴로지를 열도록 선택 해야 합니다. 이때 이전 세션에서 저장한 구성 파일을 열게 됩니다. 이 옵션을 사용하여 이전에 저장한 토폴로지를 편집할 수 있습니다.

<div>


> [!WARNING]  
> 이미 게시된 토폴로지가 있는 경우에는 로컬 구성 파일을 로드하지 않아야 하며, 기존 배포에서 토폴로지를 다운로드하도록 선택해야 합니다.



</div>

새 토폴로지 작성기 구성을 만들려면 새 토폴로지를 만들도록 선택 합니다. 새 토폴로지를 이전 설계 세션에서 만든 것과 같은 파일로 저장하도록 선택하는 경우가 아니면, 이전에 저장한 설계를 덮어쓰지 않습니다.

이러한 각 옵션에서 토폴로지 작성기 구성 파일을 저장할 위치를 입력 하 라는 메시지가 표시 됩니다. 파일의 위치는 로컬 위치, 설정된 파일 저장소의 공유 위치 또는 이동식 미디어일 수 있습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013에서 재해 복구를 위한 페어링된 프런트 엔드 풀 배포](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Lync Server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Lync Server 2013에서 단순 Url 편집 또는 구성](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Lync Server 2013에서 중앙 관리 서버 선택](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

