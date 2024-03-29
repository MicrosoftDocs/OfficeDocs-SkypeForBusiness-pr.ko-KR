---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 2019년 2019에 대해 권장 비즈니스용 Skype 서버 지원되는 마이그레이션 절차는 나란히 마이그레이션입니다. 이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유에 대해 설명하며, 동시 사용 테스트에 대한 정보도 제공합니다.
ms.openlocfilehash: 4ca0e8d1362c05e87c4ec347115f7e45457c55d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613397"
---
# <a name="migration-process"></a>마이그레이션 프로세스

2019년 2019에 대해 권장 비즈니스용 Skype 서버 지원되는 마이그레이션 절차는 나란히 마이그레이션입니다. 이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유에 대해 설명하며, 동시 사용 테스트에 대한 정보도 제공합니다.
  
## <a name="side-by-side-migration"></a>병렬 마이그레이션

거의 모든 마이그레이션에서는 병렬 마이그레이션 경로를 사용해야 합니다. 함께 마이그레이션에서는 비즈니스용 Skype 서버 2019가 있는 새 서버를 이전 버전을 실행 중인 해당 서버와 함께 배포한 다음 작업을 새 서버로 전송합니다. 이전 버전으로 롤백해야 하는 경우 작업을 원래 서버로 다시 이동하기만하면 됩니다. 이 경우 업그레이드된 클라이언트로 예약된 모든 새 모임이 작동하지 않으며 클라이언트도 다운그레이드해야 합니다.
  
## <a name="coexistence-testing"></a>동시 사용 테스트

이전 버전과 비즈니스용 Skype 서버 2019를 배포한 후 배포는 비즈니스용 Skype 서버 2019 및 이전 버전의 동시 사용 테스트 상태를 나타났습니다. 이 상태에서는 테스트를 통해 서비스가 시작되었고, 각 사이트를 관리할 수 있으며, 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지 확인해야 합니다. 모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해하고 각 배포가 올바르게 기능 및 작동하는지 확인해야 합니다. 일반적으로 공존 테스트 단계는 2019년 8월의 파일럿 테스트 비즈니스용 Skype 서버 있습니다. 레거시 사용자는 응용 프로그램 호환성과 비즈니스용 Skype 서버 기능이 제대로 작동하도록 2019년 2019년으로 이동됩니다. 파일럿 테스트를 수행하면 사용자 및 응용 프로그램이 비즈니스용 Skype 서버 2019의 프로덕션 버전으로 이동되고 이전 버전의 레거시 풀 및 응용 프로그램이 사용 중지됩니다.
  
