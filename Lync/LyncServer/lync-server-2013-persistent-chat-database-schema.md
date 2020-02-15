---
title: 'Lync Server 2013: 영구 채팅 데이터베이스 스키마'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51ee4506a22d866a5ba0f771db47546a8fa15e6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 데이터베이스 스키마

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-18_

이 문서에서는 Lync Server 2013 통신 소프트웨어의 영구 채팅 데이터베이스에 대 한 스키마를 설명 합니다.

영구 채팅 데이터베이스는 Lync Server 2013 백 엔드 서버 역할 **PersistentChatStore** (mgc 데이터베이스에 해당) 및 **PersistentChatComplianceStore** (mgccomp 데이터베이스에 해당)에 해당 하는 데이터베이스를 참조 합니다. 이 스키마를 게시하는 목적은 사용자가 쿼리를 작성하고 채팅 사용, 활성 방, 최상위 게시자 등에 대한 유용한 보고서를 작성할 수 있는 몇 가지 통찰력을 얻을 수 있도록 지원하기 위한 것입니다.

<div>


> [!IMPORTANT]  
> Microsoft는 이 스키마를 개선시킬 수 있는 권한을 보유하며, 이 게시된 스키마의 이전 버전과의 호환성을 유지 관리하는 데 대해 어떠한 보장도 하지 않습니다.



</div>

다음과 같은 모범 사례를 따르십시오.

  - SELECT\* //는 열 목록이 증가할 수 있으므로 지원 되지 않습니다.

  - 사용자가 생성한 스키마 수정은 지원되지 않습니다.

  - 쓰기 작업은 지원되지 않습니다.

  - 쿼리가 사용자의 요구 사항을 충족할 수 있는 수준으로 수행될 수 있는지 확인하기 위해 대표적인 크기의 데이터베이스에서 작성하는 모든 쿼리를 테스트합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 영구 채팅 서버 테이블 목록](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013의 영구 채팅 서버 준수 테이블 목록](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013의 영구 채팅 서버 테이블 세부 정보](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013에 대 한 샘플 영구 채팅 데이터베이스 쿼리](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

