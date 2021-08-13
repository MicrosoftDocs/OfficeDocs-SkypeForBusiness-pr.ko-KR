---
title: 여러 사이트 및 풀 마이그레이션
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
description: 비즈니스용 Skype 서버 2019에서는 다중 사이트 및 다중 풀 배포가 지원됩니다. 여러 풀을 2019년 비즈니스용 Skype 서버 마이그레이션하는 프로세스에서는 다음과 같은 사항을 고려해야 합니다.
ms.openlocfilehash: 445c519fd9a470002258ff50c14ebac7328979acc667c60a77b15a503ec3f3fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303442"
---
# <a name="migrating-multiple-sites-and-pools"></a>여러 사이트 및 풀 마이그레이션

비즈니스용 Skype 서버 2019에서는 다중 사이트 및 다중 풀 배포가 지원됩니다. 여러 풀을 2019년 비즈니스용 Skype 서버 마이그레이션하는 프로세스에서는 다음과 같은 사항을 고려해야 합니다. 
  
1. 비즈니스용 Skype 서버 2019 파일럿 풀을 배포한 후 비즈니스용 Skype 서버 2019 풀로 이동할 파일럿 사용자의 하위 집합과 사용자의 기능 유효성을 검사하기 위한 방법을 정의해야 합니다. 예를 들어 사용자를 파일럿 풀로 이동한 후 사용자의 회의 정책이 2019년 8월로 비즈니스용 Skype 서버 합니다. 
    
2. 파일럿 풀에 에지 서버를 배포한 후 외부 사용자가 2019 풀과 통신할 수 비즈니스용 Skype 서버 합니다.

3. 영구 채팅, SQL 미러링 및 XMPP 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않고 비즈니스용 Skype 서버 2019 기능으로 더 이상 사용할 수 없지만 이전에 레거시 환경에 배포된 경우 동시 사용 환경에서 계속 사용할 수 있습니다. 이러한 기능을 계속 사용하려는 경우 특정 사용자가 레거시 풀에 남아 있는 공존 환경을 계속 사용하려는 경우를 계획해야 합니다.
    
4. 페더링 경로의 에지 서버를 파일럿 비즈니스용 Skype 서버 2019 에지 서버로 전환한 후 페더러가 비즈니스용 Skype 서버 2019 풀과 통신할 수 있는지 유효성을 검사해야 합니다.
    
5. 모든 사용자 및 비사용자 연락처 개체를 이동한 후 레거시 풀이 비어있는지 유효성을 검사해야 합니다.
    
6. 레거시 풀이 비어 있는지 확인한 후 풀을 비활성화할 수 있습니다. 
    
    레거시 풀 및 서버를 비활성화하는 방법에 대한 자세한 내용은 [Phase 8: Decommission legacy pools를 참조합니다.](phase-8-decommission-legacy-pools.md)
    

