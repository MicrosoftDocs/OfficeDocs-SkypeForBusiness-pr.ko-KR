---
title: 남은 사용자 이동
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
description: '제어판 또는 관리 셸을 사용하여 비즈니스용 Skype 서버 201 비즈니스용 Skype 서버9 배포로 비즈니스용 Skype 서버 있습니다. 2019년으로 원활하게 전환하려면 몇 가지 요구 사항을 비즈니스용 Skype 서버 합니다. 이 항목의 절차를 완료하기 위한 선행 구성에 대한 자세한 내용은 Configure clients for migration을 참조하십시오. 사용자 이동에 대한 자세한 단계는 Phase 4: Move test users to the pilot pool을 참조하세요.'
ms.openlocfilehash: 60742068bc684470d181593e94615da2a8d79ff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623110"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>나머지 사용자를 2019년 비즈니스용 Skype 서버 이동

제어판 또는 관리 셸을 사용하여 비즈니스용 Skype 서버 201 비즈니스용 Skype 서버9 배포로 비즈니스용 Skype 서버 있습니다. 2019년으로 원활하게 전환하려면 몇 가지 요구 사항을 비즈니스용 Skype 서버 합니다. 이 항목의 절차를 완료하기 위한 선행 구성에 대한 자세한 내용은 [Configure clients for migration을 참조하십시오.](configure-clients-for-migration.md) 사용자 이동에 대한 자세한 단계는 [Phase 4: Move test users to the pilot pool을 참조하세요.](phase-4-move-test-users-to-the-pilot-pool.md)
  
> [!IMPORTANT]
> Active Directory 사용자 및 컴퓨터 스냅인 또는 레거시 관리 도구를 사용하여 레거시 환경에서 2019년 8월로 사용자를 비즈니스용 Skype 서버 없습니다. 
  
사용자를 비즈니스용 Skype 서버 2019 풀로 이동하면 사용자의 데이터가 새 풀과 연결된 백 엔드 데이터베이스로 이동됩니다. 
  
> [!IMPORTANT]
> 여기에는 레거시 사용자가 만든 활성 모임이 포함됩니다. 예를 들어 레거시 사용자가 내  모임 회의를 구성한 경우 사용자가 이동된 후에도 새 비즈니스용 Skype 서버 2019 풀에서 해당 회의를 계속 사용할 수 있습니다. 이 모임에 액세스하기 위한 세부 정보도 동일한 **회의 URL 및 회의 ID** 가 됩니다. 유일한 차이점은 이제 회의가 레거시 풀이 아닌 비즈니스용 Skype 서버 2019 풀에서 호스트됩니다. 
  
> [!NOTE]
> 비즈니스용 Skype 서버 2019에서 사용자를 모을 경우 업그레이드된 클라이언트를 동시에 배포할 필요가 없습니다. 새로운 기능은 사용자가 새 클라이언트 소프트웨어로 업그레이드한 경우에만 사용할 수 있습니다. 
  
### <a name="post-migration-task"></a>마이그레이션 후 작업

1. 사용자를 이동한 후에는 사용자에게 지정된 회의 정책을 확인합니다. 
    
2. 비즈니스용 Skype 서버 2019에 있는 사용자가 구성한 모임이 레거시 설치에 있는 페더링된 사용자와 원활하게 작동하도록 마이그레이션된 사용자에게 할당된 회의 정책에서 익명 참가자를 허용해야 합니다.
    
3. 익명 참가자를 허용하는 회의 정책에는  비즈니스용 Skype 서버 2019 제어판에서 참가자가 익명 사용자를 초대할 수 있도록 허용이 선택되어 있으며 비즈니스용 Skype 서버 관리 셸의 **Get-CsConferencingPolicy** cmdlet 출력에서 **AllowAnonymousParticipantsInMeetings가** **True로** 설정되어 있습니다. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

