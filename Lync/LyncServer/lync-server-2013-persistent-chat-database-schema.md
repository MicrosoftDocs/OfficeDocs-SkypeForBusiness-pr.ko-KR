---
title: 'Lync Server 2013: 영구 채팅 데이터베이스 스키마'
description: 'Lync Server 2013: 영구 채팅 데이터베이스 스키마'
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
ms.openlocfilehash: 66151201f65310cc8e6d3f2251be4f86ce2be15d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545154"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="d1d80-103">Lync Server 2013의 영구 채팅 데이터베이스 스키마</span><span class="sxs-lookup"><span data-stu-id="d1d80-103">Persistent Chat database schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1d80-104">_**마지막으로 수정 된 항목:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="d1d80-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="d1d80-105">이 문서에서는 Lync Server 2013 통신 소프트웨어의 영구 채팅 데이터베이스에 대 한 스키마를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-105">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="d1d80-106">영구 채팅 데이터베이스는 Lync Server 2013 백 엔드 서버 역할 **PersistentChatStore** (mgc 데이터베이스에 해당) 및 **PersistentChatComplianceStore** (mgccomp 데이터베이스에 해당)에 해당 하는 데이터베이스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-106">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="d1d80-107">이 스키마를 게시하는 목적은 사용자가 쿼리를 작성하고 채팅 사용, 활성 방, 최상위 게시자 등에 대한 유용한 보고서를 작성할 수 있는 몇 가지 통찰력을 얻을 수 있도록 지원하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-107">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1d80-p102">Microsoft는 이 스키마를 개선시킬 수 있는 권한을 보유하며, 이 게시된 스키마의 이전 버전과의 호환성을 유지 관리하는 데 대해 어떠한 보장도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="d1d80-110">다음과 같은 모범 사례를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="d1d80-110">Follow these best practices:</span></span>

  - <span data-ttu-id="d1d80-111">SELECT \* //는 열 목록이 증가할 수 있으므로 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-111">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="d1d80-112">사용자가 생성한 스키마 수정은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-112">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="d1d80-113">쓰기 작업은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-113">No write operations are supported.</span></span>

  - <span data-ttu-id="d1d80-114">쿼리가 사용자의 요구 사항을 충족할 수 있는 수준으로 수행될 수 있는지 확인하기 위해 대표적인 크기의 데이터베이스에서 작성하는 모든 쿼리를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-114">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d1d80-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d1d80-115">In This Section</span></span>

  - [<span data-ttu-id="d1d80-116">Lync Server 2013의 영구 채팅 서버 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="d1d80-116">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="d1d80-117">Lync Server 2013의 영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="d1d80-117">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="d1d80-118">Lync Server 2013의 영구 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="d1d80-118">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="d1d80-119">Lync Server 2013에 대 한 샘플 영구 채팅 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="d1d80-119">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

