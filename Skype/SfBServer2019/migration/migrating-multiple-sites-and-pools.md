---
title: 여러 사이트 및 풀 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019는 다중 사이트 및 다중 풀 배포를 지원 합니다. 여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스에는 다음 고려 사항이 필요 합니다.
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813446"
---
# <a name="migrating-multiple-sites-and-pools"></a>여러 사이트 및 풀 마이그레이션

비즈니스용 Skype 서버 2019는 다중 사이트 및 다중 풀 배포를 지원 합니다. 여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스에는 다음 고려 사항이 필요 합니다. 
  
1. 비즈니스용 Skype Server 2019 파일럿 풀을 배포한 후에는 비즈니스용 Skype Server 2019 풀로 이동할 파일럿 사용자의 하위 집합을 정의 하 고 사용자의 기능을 확인 하기 위한 방법론으로 지정 해야 합니다. 예를 들어 파일럿 풀로 사용자를 이동한 후에는 사용자의 컨퍼런스 정책이 비즈니스용 Skype 서버 2019로 이동 했는지 확인 합니다. 
    
2. 파일럿 풀에 Edge 서버를 배포한 후에는 외부 사용자가 비즈니스용 Skype 서버 2019 풀과 통신할 수 있는지 확인 해야 합니다.

3. 영구 채팅, SQL 미러링 및 XMPP 기능은 비즈니스용 Skype 서버 2019에서 사용 되지 않으며, 더 이상 비즈니스용 Skype Server 2019 기능으로 사용할 수 없지만, 이전에 배포 된 경우에는 공존 환경에서 계속 가능 합니다. 레거시 환경. 이러한 기능을 계속 사용 하려면 특정 사용자가 레거시 풀에 유지 되는 공존 환경에서 계속 진행할 계획을 세워야 합니다.
    
4. 페더레이션된 경로의 Edge 서버를 파일럿 비즈니스용 Skype 서버 2019 Edge 서버로 전환 하 고 나면 페더레이션 사용자가 비즈니스용 Skype Server 2019 풀과 통신할 수 있는지 확인 해야 합니다.
    
5. 모든 사용자 및 사용자가 아닌 연락처 개체를 이동한 후에는 레거시 풀이 비어 있는지 확인 해야 합니다.
    
6. 레거시 풀이 비어 있는지 확인 한 후에 풀을 비활성화할 수 있습니다. 
    
    레거시 풀 및 서버를 비활성화 하는 방법에 대 한 자세한 내용은 [8 단계: 레거시 풀 서비스](phase-8-decommission-legacy-pools.md)해제를 참조 하세요.
    

