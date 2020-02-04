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
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 정의 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-14_

토폴로지 작성기를 사용 하 여 토폴로지를 정의 하 고 구성 합니다. 토폴로지 작성기를 사용할 경우 로컬 관리자 그룹의 구성원 이거나 도메인 관리자와 같은 특권 수준의 도메인 그룹이 될 필요는 없습니다. 토폴로지를 표준 사용자로 정의할 수 있습니다. 첫 번째 사용 및 후속 편집 세션에서 토폴로지 작성기를 시작 하면 토폴로지 작성기가 현재 구성 문서를 로드할 위치를 묻는 메시지가 표시 됩니다. 선택 항목은 다음과 같습니다.

  - 기존 배포에서 토폴로지 다운로드

  - 로컬 파일에서 토폴로지 열기

  - 새 토폴로지

이미 토폴로지를 정의 하 고 중앙 관리 저장소를 설정한 경우 기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다. 토폴로지 작성기는 데이터베이스를 읽고 현재 정의를 검색 합니다. 기존 중앙 관리 저장소가 있는 경우 항상이 옵션을 선택 해야 합니다.

중앙 관리 저장소를 설정 하지 않은 경우 이전에 저장 된 구성을 편집 하려면 로컬 파일에서 토폴로지를 열도록 선택 해야 합니다. 열려고 하는 파일은 이전 세션에서 저장 된 구성 파일입니다. 이 옵션을 사용 하 여 이전에 저장 된 토폴로지를 편집할 수 있습니다.

<div>


> [!WARNING]  
> 이미 게시 된 토폴로지가 있는 경우 로컬 구성 파일을 로드 하지 않아야 합니다. 기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다.



</div>

새 토폴로지 작성기 구성을 만들려는 경우 새 토폴로지를 만들도록 선택 합니다. 이전 디자인 세션에서 만든 파일과 동일한 파일로 저장 하도록 선택 하지 않는 한 이전에 저장 된 디자인을 덮어쓰지 않습니다.

이러한 옵션 각각에 대해 토폴로지 작성기 구성 파일을 저장할 위치를 입력 하 라는 메시지가 표시 됩니다. 파일의 위치는 로컬 위치, 설정 된 파일 공유 상의 공유 위치 또는 이동식 미디어 일 수 있습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대한 토폴로지 작성기에서 토폴로지 정의 및 구성](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013에서 재해 복구를 위해 연결된 프런트 엔드 풀 배포](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Lync Server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Lync Server 2013에서 단순 URL 편집 또는 구성](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Lync Server 2013에서 중앙 관리 서버 선택](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

