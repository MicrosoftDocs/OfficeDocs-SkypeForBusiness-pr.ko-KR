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
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 이 문서는 비즈니스용 Skype 서버의 영구 채팅 데이터베이스 스키마를 설명 합니다.
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196658"
---
# <a name="persistent-chat-database-schema"></a>영구 채팅 데이터베이스 스키마
 
이 문서는 비즈니스용 Skype 서버의 영구 채팅 데이터베이스 스키마를 설명 합니다.
  
영구 채팅 데이터베이스는 비즈니스용 Skype Server 백 엔드 서버 역할 **PersistentChatStore** (mgc 데이터베이스에 해당) 및 **PersistentChatComplianceStore** (다음에 해당)에 해당 하는 데이터베이스를 참조 합니다. mgccomp 데이터베이스). 이 스키마를 게시 하는 목적은 쿼리를 작성 하 고 채팅 사용, 활성 회의실, 인기 포스터 등의 유용한 보고를 작성 하는 데 필요한 정보를 얻을 수 있도록 하는 것입니다.
  
> [!IMPORTANT]
> 이 스키마를 발전시키는 권한을 예약 합니다. Microsoft는이 게시 된 스키마와의 완전 한 이전 호환성을 유지 하기 위해 어떠한 보증도 하지 않습니다. 
  
다음 모범 사례를 따르세요.
  
- SELECT\* //는 열 목록이 커질 수 있으므로 지원 되지 않습니다.
    
- 사용자가 생성 한 스키마 수정은 지원 되지 않습니다.
    
- 쓰기 작업은 지원 되지 않습니다.
    
- Representatively 크기의 데이터베이스에서 작성 하는 모든 쿼리를 테스트 하 여 쿼리가 필요에 맞게 수준에서 수행 될 수 있는지 확인 합니다.
    
## <a name="in-this-section"></a>이 섹션의

- [영구 채팅 서버 테이블 목록](list-of-persistent-chat-server-tables.md)
    
- [비즈니스용 Skype 서버의 영구 채팅 서버 준수 테이블 목록](list-of-persistent-chat-server-compliance-tables.md)
    
- [영구 채팅 서버 테이블 세부 정보](persistent-chat-server-table-details.md)
    
- [샘플 영구 채팅 데이터베이스 쿼리](sample-persistent-chat-database-queries.md)
    

