---
title: 영구 채팅 데이터베이스 스키마
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 이 문서에서는 비즈니스용 Skype 서버의 영구 채팅 데이터베이스의 스마마를 문서화합니다.
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809878"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="2cd00-103">영구 채팅 데이터베이스 스키마</span><span class="sxs-lookup"><span data-stu-id="2cd00-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="2cd00-104">이 문서에서는 비즈니스용 Skype 서버의 영구 채팅 데이터베이스의 스마마를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="2cd00-105">영구 채팅 데이터베이스는 비즈니스용 Skype 서버 백 엔드 서버 역할 **PersistentChatStore(mgc** 데이터베이스에 해당) 및 **PersistentChatComplianceStore(mgccomp** 데이터베이스에 해당)에 해당하는 데이터베이스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="2cd00-106">이 스키마를 게시하는 목적은 사용자가 쿼리를 작성하고 채팅 사용, 활성 방, 최상위 게시자 등에 대한 유용한 보고서를 작성할 수 있는 몇 가지 통찰력을 얻을 수 있도록 지원하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2cd00-p102">Microsoft는 이 스키마를 개선시킬 수 있는 권한을 보유하며, 이 게시된 스키마의 이전 버전과의 호환성을 유지 관리하는 데 대해 어떠한 보장도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="2cd00-109">다음과 같은 모범 사례를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="2cd00-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="2cd00-110">열 목록이 커질 수 있기 때문에 SELECT \* //는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="2cd00-111">사용자가 생성한 스키마 수정은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="2cd00-112">쓰기 작업은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="2cd00-113">쿼리가 사용자의 요구 사항을 충족할 수 있는 수준으로 수행될 수 있는지 확인하기 위해 대표적인 크기의 데이터베이스에서 작성하는 모든 쿼리를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd00-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="2cd00-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2cd00-114">In this section</span></span>

- [<span data-ttu-id="2cd00-115">영구적 채팅 서버 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="2cd00-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="2cd00-116">비즈니스용 Skype 서버의 영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="2cd00-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="2cd00-117">영구적 채팅 서버 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="2cd00-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="2cd00-118">샘플 영구적 채팅 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="2cd00-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

