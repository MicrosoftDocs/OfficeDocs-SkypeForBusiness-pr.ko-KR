---
title: Survivable Branch 기기 연결
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 모든 Survivable Branch 기기 (SBA)는 SBA에 대 한 백업 등록 기관 역할을 하는 프런트 엔드 풀과 연결 되어 있습니다. 프런트 엔드 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 경우 풀을 업그레이드 하는 동안 프런트 엔드 풀에서 연결을 해제 해야 하며,이 경우, 해당 풀이 비즈니스용 Skype Server 2019로 마이그레이션된 후에는 SBA를 업그레이드 된 전면 E와 다시 연결할 수 있습니다. nd 풀. 이 작업에는 토폴로지 작성기의 레거시 토폴로지에서의 SBA를 삭제 한 다음 비즈니스용 Skype 서버 2019 토폴로지에 추가 됩니다. 레거시 SBA에 있는 사용자는 먼저 다른 프런트 엔드 풀로 이동한 후에 야 토폴로지에서 SBA를 제거할 수 있습니다. SBA를 비즈니스용 Skype 서버 2019 토폴로지에 추가 하면 해당 사용자는 다시 SBA로 이동할 수 있습니다. 이러한 단계는 다음과 같이 요약할 수 있습니다.
ms.openlocfilehash: 7cb933018d24dafb978464338f01f97b25e15539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187332"
---
# <a name="connect-a-survivable-branch-appliance"></a>Survivable Branch 기기 연결

모든 Survivable Branch 기기 (SBA)는 SBA에 대 한 백업 등록 기관 역할을 하는 프런트 엔드 풀과 연결 되어 있습니다. 프런트 엔드 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하면 풀이 업그레이드 되는 동안 SBA를 프런트 엔드 풀에서 분리 해야 합니다. 풀이 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 SBA를 업그레이드 된 프런트 엔드 풀에 다시 연결할 수 있습니다. 이 작업에는 토폴로지 작성기의 레거시 토폴로지에서의 SBA를 삭제 한 다음 비즈니스용 Skype 서버 2019 토폴로지에 추가 됩니다. 레거시 SBA에 있는 사용자는 먼저 다른 프런트 엔드 풀로 이동한 후에 야 토폴로지에서 SBA를 제거할 수 있습니다. SBA가 비즈니스용 Skype 서버 2019 토폴로지에 추가 된 후에는 해당 사용자를 다시 SBA로 이동할 수 있습니다. 이러한 단계는 다음과 같이 요약할 수 있습니다.
  
1. 레거시 SBA에 속한 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.
    
2. 기존 프런트 엔드 풀을 백업 등록 기관으로 연결 해제 하려면 레거시 토폴로지에서 SBA를 제거 합니다.
    
3. 비즈니스용 Skype 서버 2019 토폴로지에 새 프런트 엔드 풀을 추가 하 고 백업 등록 기관으로 구성 합니다. 
    
4. 분기 사용자를 새 비즈니스용 Skype Server 2019 SBA로 이동 합니다.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>토폴로지에 레거시 SBA 분기 사이트 추가

1. **토폴로지 작성기**를 엽니다.
    
2. 왼쪽 창에서 **분기 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **새 분기 사이트**를 클릭 합니다.
    
3. **새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 분기 사이트의 이름을 입력 합니다.
    
4. ) **설명을**클릭 한 다음 분기 사이트에 대 한 의미 있는 설명을 입력 합니다.
    
5. **다음**을 클릭 합니다.
    
6. ) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 하나를 수행 합니다. 
    
    1. **도시**를 클릭 한 다음 지점 사이트가 있는 도시의 이름을 입력 합니다.
    
    2. **상태/지역을**클릭 한 다음 분기 사이트가 있는 상태 또는 지역의 이름을 입력 합니다.
    
    3. **국가 코드**를 클릭 한 다음 분기 사이트가 있는 국가/지역에 대 한 두 자리 통화 코드를 입력 합니다.
    
7. **다음**을 클릭 한 다음이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하는 경우 **마법사를 닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 해야 합니다. **마침을**클릭 합니다.
    
8. 레거시 SBA를 비즈니스용 Skype 서버 2019 프런트 엔드 풀에 연결 하려면 다음을 수행 합니다.
    
    1. 생성 된 분기 사이트를 확장 합니다. 
    
    2. 이전 버전을 마우스 오른쪽 단추로 클릭 한 다음 **새로 만들기**를 클릭 합니다.
    
    3. **Survivable Branch 기기**를 클릭 합니다.
    
9. 열리는 마법사의 지침을 따릅니다. 마법사 항목에 대 한 자세한 내용은 다음을 참고 하세요.    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable Branch 기기는 모니터링 저장소에만 연결할 수 있습니다. 
  
10. 이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하 고 있지 않은 경우 마법사를 **닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 하 고 **마침을**클릭 합니다.
    
11. 토폴로지에 추가 하려는 각 분기 사이트에 대해 앞의 단계를 반복 합니다.
    

