---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019에 대해 권장 되거나 지원 되는 마이그레이션 절차는 나란히 마이그레이션입니다. 이 항목에서는 나란히 마이그레이션을 사용 해야 하는 이유와 공존 테스트에 대 한 정보를 포함 합니다.
ms.openlocfilehash: 179ad56dcf4c31abe8b94fb7131dd27dc68bfd96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196952"
---
# <a name="migration-process"></a>마이그레이션 프로세스

비즈니스용 Skype 서버 2019에 대해 권장 되거나 지원 되는 마이그레이션 절차는 나란히 마이그레이션입니다. 이 항목에서는 나란히 마이그레이션을 사용 해야 하는 이유와 공존 테스트에 대 한 정보를 포함 합니다.
  
## <a name="side-by-side-migration"></a>나란히 마이그레이션

거의 모든 마이그레이션에는 side-by-side 마이그레이션 경로를 사용 해야 합니다. 나란히 마이그레이션하는 경우 이전 버전을 실행 하는 해당 서버와 함께 비즈니스용 Skype 서버 2019와 새 서버를 배포한 다음 새 서버로 작업을 전송 합니다. 이전 버전으로 롤백하는 데 필요한 경우 원래 서버로만 작업을 다시 전환할 수 있습니다. 이 상황에서는 업그레이드 된 클라이언트를 사용 하 여 예약 된 새 모임이 작동 하지 않으며 클라이언트도 다운 그레이드 해야 한다는 점에 유의 하세요.
  
## <a name="coexistence-testing"></a>공존 테스트

이전 버전과 병행 하 여 비즈니스용 Skype 서버 2019을 배포한 후에는 배포는 비즈니스용 Skype Server 2019 및 이전 버전의 공존 테스트 상태를 나타냅니다. 이 상태에서는 서비스를 시작 하 고 각 사이트를 관리할 수 있으며 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지를 테스트 하는 것이 중요 합니다. 모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해 하 고 각 배포가 제대로 작동 하 고 작동 하는지 확인 하는 것이 중요 합니다. 일반적으로 공존 테스트 단계는 비즈니스용 Skype 서버 2019의 파일럿 테스트 전반에 걸쳐 있습니다. 레거시 사용자는 일정 기간 동안 비즈니스용 Skype 서버 2019으로 이동 하 여 응용 프로그램 호환성과 기능 및 기능이 제대로 작동 하는지 확인 합니다. 파일럿 테스트 후에는 사용자 및 응용 프로그램이 비즈니스용 Skype Server 2019의 프로덕션 버전으로 이동 하 고 이전 버전의 레거시 풀 및 응용 프로그램은 사용 중지 됩니다.
  
