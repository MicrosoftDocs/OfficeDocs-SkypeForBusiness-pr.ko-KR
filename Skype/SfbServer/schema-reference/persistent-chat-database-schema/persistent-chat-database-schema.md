---
title: 영구 채팅 데이터베이스 스키마
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 이 문서는 비즈니스용 Skype 서버의 영구 채팅 데이터베이스 스키마를 설명 합니다.
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814746"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="773f2-103">영구 채팅 데이터베이스 스키마</span><span class="sxs-lookup"><span data-stu-id="773f2-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="773f2-104">이 문서는 비즈니스용 Skype 서버의 영구 채팅 데이터베이스 스키마를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="773f2-105">영구 채팅 데이터베이스는 비즈니스용 Skype Server 백 엔드 서버 역할 **PersistentChatStore** (mgc 데이터베이스에 해당) 및 **PersistentChatComplianceStore** (mgccomp 데이터베이스에 해당)에 해당 하는 데이터베이스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="773f2-106">이 스키마를 게시 하는 목적은 쿼리를 작성 하 고 채팅 사용, 활성 회의실, 인기 포스터 등의 유용한 보고를 작성 하는 데 필요한 정보를 얻을 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="773f2-107">이 스키마를 발전시키는 권한을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="773f2-108">Microsoft는이 게시 된 스키마와의 완전 한 이전 호환성을 유지 하기 위해 어떠한 보증도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="773f2-109">다음 모범 사례를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="773f2-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="773f2-110">SELECT\* //는 열 목록이 커질 수 있으므로 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="773f2-111">사용자가 생성 한 스키마 수정은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="773f2-112">쓰기 작업은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="773f2-113">Representatively 크기의 데이터베이스에서 작성 하는 모든 쿼리를 테스트 하 여 쿼리가 필요에 맞게 수준에서 수행 될 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="773f2-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="773f2-114">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="773f2-114">In this section</span></span>

- [<span data-ttu-id="773f2-115">영구적 채팅 서버 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="773f2-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="773f2-116">비즈니스용 Skype 서버의 영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="773f2-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="773f2-117">영구적 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="773f2-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="773f2-118">샘플 영구적 채팅 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="773f2-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

