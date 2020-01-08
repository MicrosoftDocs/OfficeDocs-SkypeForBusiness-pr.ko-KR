---
title: 'Lync Server 2013: 영구 채팅 데이터베이스 스키마'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="ca982-102">Lync Server 2013의 영구 채팅 데이터베이스 스키마</span><span class="sxs-lookup"><span data-stu-id="ca982-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca982-103">_**마지막으로 수정한 주제:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="ca982-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="ca982-104">이 문서는 Lync Server 2013 통신 소프트웨어의 영구 채팅 데이터베이스 스키마를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="ca982-105">영구 채팅 데이터베이스는 Lync Server 2013 백 엔드 서버 역할 **PersistentChatStore** (mgc 데이터베이스에 해당) 및 **PersistentChatComplianceStore** (mgccomp 데이터베이스에 해당)에 해당 하는 데이터베이스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="ca982-106">이 스키마를 게시 하는 목적은 쿼리를 작성 하 고 채팅 사용, 활성 회의실, 인기 포스터 등의 유용한 보고를 작성 하는 데 필요한 정보를 얻을 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca982-107">이 스키마를 발전시키는 권한을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="ca982-108">Microsoft는이 게시 된 스키마와의 완전 한 이전 호환성을 유지 하기 위해 어떠한 보증도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="ca982-109">다음 모범 사례를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ca982-109">Follow these best practices:</span></span>

  - <span data-ttu-id="ca982-110">SELECT\* //는 열 목록이 커질 수 있으므로 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="ca982-111">사용자가 생성 한 스키마 수정은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="ca982-112">쓰기 작업은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-112">No write operations are supported.</span></span>

  - <span data-ttu-id="ca982-113">Representatively 크기의 데이터베이스에서 작성 하는 모든 쿼리를 테스트 하 여 쿼리가 필요에 맞게 수준에서 수행 될 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca982-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ca982-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ca982-114">In This Section</span></span>

  - [<span data-ttu-id="ca982-115">Lync Server 2013의 영구 채팅 서버 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="ca982-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="ca982-116">Lync Server 2013의 영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="ca982-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="ca982-117">Lync Server 2013의 영구 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="ca982-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="ca982-118">Lync Server 2013의 샘플 영구 채팅 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="ca982-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

