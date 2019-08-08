---
title: 나머지 사용자 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '비즈니스용 Skype server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자를 새로운 비즈니스용 Skype Server 2019 배포로 이동할 수 있습니다. 비즈니스용 Skype 서버 2019의 원활한 전환을 위해 몇 가지 요구 사항을 충족 해야 합니다. 이 항목의 절차를 완료 하기 위한 필수 구성 요소에 대 한 자세한 내용은 마이그레이션할 클라이언트 구성을 참조 하세요. 사용자 이동에 대 한 자세한 내용은 4 단계: 파일럿 풀로 테스트 사용자 이동을 참조 하세요.'
ms.openlocfilehash: 8c12ca52e162c4317dabc59d5de9b74082730882
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244785"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>나머지 사용자를 비즈니스용 Skype 서버 2019로 이동

비즈니스용 Skype server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자를 새로운 비즈니스용 Skype Server 2019 배포로 이동할 수 있습니다. 비즈니스용 Skype 서버 2019의 원활한 전환을 위해 몇 가지 요구 사항을 충족 해야 합니다. 이 항목의 절차를 완료 하기 위한 필수 구성 요소에 대 한 자세한 내용은 [마이그레이션할 클라이언트 구성을](configure-clients-for-migration.md)참조 하세요. 사용자 이동에 대 한 자세한 내용은 [4 단계: 파일럿 풀로 테스트 사용자 이동을](phase-4-move-test-users-to-the-pilot-pool.md)참조 하세요.
  
> [!IMPORTANT]
> Active Directory 사용자 및 컴퓨터 스냅인 또는 레거시 관리 도구를 사용 하 여 레거시 환경에서 비즈니스용 Skype Server 2019 사용자를 이동할 수 없습니다. 
  
비즈니스용 Skype Server 2019 풀로 사용자를 이동 하면 사용자의 데이터가 새 풀과 연결 된 백 엔드 데이터베이스로 이동 합니다. 
  
> [!IMPORTANT]
> 여기에는 레거시 사용자가 만든 활성 모임이 포함 됩니다. 예를 들어 레거시 사용자가 **내 모임** 회의를 구성한 경우 해당 회의는 사용자가 이동한 후 새로운 비즈니스용 Skype 서버 2019 풀에서 계속 사용할 수 있습니다. 해당 모임에 액세스 하는 데 대 한 세부 정보는 계속 해 서 동일한 **회의 URL 및 전화 회의 ID**가 됩니다. 유일한 차이점은 현재 회의가 레거시 풀이 아닌 비즈니스용 Skype 서버 2019 풀에서 호스트 된다는 점입니다. 
  
> [!NOTE]
> 비즈니스용 Skype 서버 2019에 있는 사용자는 업그레이드 된 클라이언트를 동시에 배포할 필요가 없습니다. 새로운 기능은 사용자가 새 클라이언트 소프트웨어로 업그레이드 한 경우에만 사용할 수 있게 됩니다. 
  
### <a name="post-migration-task"></a>마이그레이션 이후 작업

1. 사용자를 이동한 후에는 자신에 게 할당 된 회의 정책을 확인 합니다. 
    
2. 비즈니스용 Skype 서버 2019에 있는 사용자가 구성한 모임이 레거시 설치에 속한 페더레이션 사용자와 원활 하 게 작동 하도록 하기 위해, 마이그레이션된 사용자에 게 할당 된 회의 정책은 익명 참가자를 허용 해야 합니다.
    
3. 익명 참가자가 비즈니스용 Skype Server 2019 제어판에서 **익명 사용자를 초대할 수** 있도록 허용 하는 회의 정책에는 **AllowAnonymousParticipantsInMeetings** 가 **True** 로 설정 되어 있습니다. 비즈니스용 Skype 서버 관리 셸에서 **CsConferencingPolicy** cmdlet의 출력. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

