---
title: 풀에서 프런트 엔드 서버 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다. 풀에 컴퓨터가 하나만 있는 경우에도 프런트 엔드 풀로 정의 해야 합니다.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752320"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>풀에서 프런트 엔드 서버 제거

프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다. 풀에 컴퓨터가 하나만 있는 경우에도 프런트 엔드 풀로 정의 해야 합니다.
  
이 항목에서는 기존 프런트 엔드 풀에서 개별 프런트 엔드 서버를 제거 하는 프로세스를 안내 합니다. 프런트 엔드 서버가 풀의 마지막 서버 이거나 풀을 완전히 제거 하는 경우에는 [Remove 프런트 엔드 풀 또는 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)를 참조 하세요. 프런트 엔드 풀을 제거 하기 전에 개별 프런트 엔드 서버를 제거할 필요가 없습니다. 풀을 제거 하면 각 프런트 엔드 서버가 제거 됩니다.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>풀에서 프런트 엔드 서버를 제거하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.
    
2. 레거시 설치 노드로 이동 합니다.
    
3. **Enterprise Edition 프런트 엔드 풀**을 확장 하 고, 제거할 프런트 엔드 서버를 사용 하 여 프런트 엔드 풀을 확장 하 고, 제거할 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    

