---
title: SBA(Survivable Branch Appliance) 연결
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
description: 모든 SBA(Survivable Branch Appliance)는 SBA용 백업 고급 등록자로 작동하는 프런트 엔드 풀과 연결됩니다. 프런트 엔드 풀이 비즈니스용 Skype 서버 2019로 마이그레이션되는 경우 풀이 업그레이드되는 동안 프런트 엔드 풀에서 SBA의 연결이 되어야 합니다. 풀이 비즈니스용 Skype 서버 2019로 마이그레이션된 후 SBA를 업그레이드된 프런트 엔드 풀과 다시 연결될 수 있습니다. 여기에는 토폴로지 작성기에서 레거시 토폴로지에서 SBA를 삭제한 다음 SBA를 비즈니스용 Skype 서버 2019 토폴로지로 추가합니다. 레거시 SBA에 있는 사용자는 토폴로지에서 SBA를 제거하기 전에 먼저 다른 프런트 엔드 풀로 이동해야 합니다. SBA를 비즈니스용 Skype 서버 2019 토폴로지로 추가하면 해당 사용자를 다시 SBA로 이동할 수 있습니다. 이러한 단계는 아래에 요약되어 있습니다.
ms.openlocfilehash: c431451503efd23039b4c358488bfc5bce03ba65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588050"
---
# <a name="connect-a-survivable-branch-appliance"></a>SBA(Survivable Branch Appliance) 연결

모든 SBA(Survivable Branch Appliance)는 SBA의 백업 등록자 역할을 하는 프런트 엔드 풀과 연결됩니다. 프런트 엔드 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 경우 풀이 업그레이드되는 동안 프런트 엔드 풀에서 SBA의 분해를 해야 합니다. 풀을 비즈니스용 Skype 서버 2019로 마이그레이션한 후 SBA를 업그레이드된 프런트 엔드 풀과 다시 연결합니다. 여기에는 토폴로지 작성기에서 레거시 토폴로지에서 SBA를 삭제한 다음 SBA를 비즈니스용 Skype 서버 2019 토폴로지로 추가합니다. 레거시 SBA에 있는 사용자는 토폴로지에서 SBA를 제거하기 전에 먼저 다른 프런트 엔드 풀로 이동해야 합니다. SBA가 비즈니스용 Skype 서버 2019 토폴로지로 추가된 후 해당 사용자를 SBA로 다시 이동할 수 있습니다. 이러한 단계는 아래에 요약되어 있습니다.
  
1. 레거시 SBA에 있는 분기 사용자를 다른 프런트 엔드 풀로 이동
    
2. 레거시 토폴로지에서 SBA를 제거하여 백업 등록자인 기존 프런트 엔드 풀의 연결을 끊습니다.
    
3. 비즈니스용 Skype 서버 2019 토폴로지에 SBA를 추가하고 이 새 프런트 엔드 풀을 백업 등록 기관으로 구성합니다. 
    
4. 분기 사용자를 2019년 비즈니스용 Skype 서버 새 SBA로 이동합니다.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>토폴로지에 레거시 SBA 분기 사이트 추가

1. **토폴로지 작성기** 를 엽니다.
    
2. 왼쪽 창에서 분기 사이트를 마우스 오른쪽 단추로 **클릭한** 다음 새 분기 **사이트를 클릭합니다.**
    
3. **새 분기 사이트 정의** 대화 상자에서 **이름** 을 클릭한 다음 분기 사이트의 이름을 입력합니다.
    
4. (선택 사항) **설명** 을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.
    
5. **다음** 을 클릭합니다.
    
6. (선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다. 
    
    1. **구/군/시** 를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.
    
    2. **시/도/지역** 을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.
    
    3. 국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.
    
7. **다음을** 클릭하고 이 사이트에서 Survivable Branch Appliance 또는 Server를 사용하는 경우 이 마법사가 닫히면 새 **Survivable Wizard** 열기 확인란의 선택을 취소해야 합니다. **마침** 을 클릭합니다.
    
8. 레거시 SBA를 비즈니스용 Skype 서버 2019 프런트 엔드 풀에 연결합니다.
    
    1. 만들어진 분기 사이트를 확장합니다. 
    
    2. 레거시 버전을 마우스 오른쪽 단추로 클릭한 다음 새로 **고치기 를 클릭합니다.**
    
    3. **Survivable Branch Appliance 를 클릭합니다.**
    
9. 표시되는 마법사의 지침을 따르십시오. 마법사 항목에 대한 자세한 내용은    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable Branch Appliance는 모니터링 저장소에만 연결될 수 있습니다. 
  
10. 이 사이트에서 SBA 또는 지속 가능 분기 서버를 사용하지 않는 경우에는 **이 마법사가 닫히면 새 지속 가능 마법사 열기** 확인란의 선택을 취소한 다음 **마침** 을 클릭합니다.
    
11. 토폴로지에 추가할 각 분기 사이트에 대해 이전 단계를 반복합니다.
