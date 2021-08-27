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
ms.localizationpriority: medium
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 이 문서에서는 영구 채팅 데이터베이스의 비즈니스용 Skype 서버.
ms.openlocfilehash: 673cca8acf2ecad76c578ba05d8d22a20a253a9c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610585"
---
# <a name="persistent-chat-database-schema"></a>영구 채팅 데이터베이스 스키마
 
이 문서에서는 영구 채팅 데이터베이스의 비즈니스용 Skype 서버.
  
영구 채팅 데이터베이스는 비즈니스용 Skype 서버 백 엔드 서버 역할 **PersistentChatStore(mgc** 데이터베이스에 해당) 및 **PersistentChatComplianceStore(mgccomp** 데이터베이스에 해당)에 해당하는 데이터베이스를 참조합니다. 이 스키마를 게시하는 목적은 사용자가 쿼리를 작성하고 채팅 사용, 활성 방, 최상위 게시자 등에 대한 유용한 보고서를 작성할 수 있는 몇 가지 통찰력을 얻을 수 있도록 지원하기 위한 것입니다.
  
> [!IMPORTANT]
> Microsoft는 이 스키마를 개선시킬 수 있는 권한을 보유하며, 이 게시된 스키마의 이전 버전과의 호환성을 유지 관리하는 데 대해 어떠한 보장도 하지 않습니다. 
  
다음과 같은 모범 사례를 따르십시오.
  
- 열 목록이 커질 수 있기 때문에 SELECT \* //는 지원되지 않습니다.
    
- 사용자가 생성한 스키마 수정은 지원되지 않습니다.
    
- 쓰기 작업은 지원되지 않습니다.
    
- 쿼리가 사용자의 요구 사항을 충족할 수 있는 수준으로 수행될 수 있는지 확인하기 위해 대표적인 크기의 데이터베이스에서 작성하는 모든 쿼리를 테스트합니다.
    
## <a name="in-this-section"></a>이 섹션의 내용

- [영구적 채팅 서버 테이블 목록](list-of-persistent-chat-server-tables.md)
    
- [영구 채팅 서버 준수 테이블의 비즈니스용 Skype 서버](list-of-persistent-chat-server-compliance-tables.md)
    
- [영구적 채팅 서버 테이블 세부 정보](persistent-chat-server-table-details.md)
    
- [샘플 영구적 채팅 데이터베이스 쿼리](sample-persistent-chat-database-queries.md)
    

