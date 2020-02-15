---
title: Sba (survivable 분기 기기 연결
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
description: 모든 SBA(Survivable Branch Appliance)는 SBA용 백업 고급 등록자로 작동하는 프런트 엔드 풀과 연결됩니다. 프런트 엔드 풀이 비즈니스용 Skype 서버 2019로 마이그레이션될 경우 프런트 엔드 풀에서 SBA를 분리 해야 함 풀이 업그레이드 되는 동안에는 풀이 비즈니스용 Skype 서버 2019로 마이그레이션된 후에도 SBA가 업그레이드 된 전면 E와 연결 될 수 있습니다. nd 풀 여기에는 토폴로지 작성기의 레거시 토폴로지에서 SBA를 삭제 한 다음 SBA를 비즈니스용 Skype 서버 2019 토폴로지에 추가 하는 작업이 포함 됩니다. 레거시 SBA에 있는 사용자를 먼저 다른 프런트 엔드 풀로 이동한 후 토폴로지에 있는 SBA를 제거 해야 합니다. SBA를 비즈니스용 Skype 서버 2019 토폴로지에 추가 하면 해당 사용자는 SBA로 다시 이동할 수 있습니다. 이러한 단계는 아래에 요약되어 있습니다.
ms.openlocfilehash: 7f51b9c29d6008ea3606184eb22741a489d056df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027789"
---
# <a name="connect-a-survivable-branch-appliance"></a>Sba (survivable 분기 기기 연결

모든 Sba (survivable Branch 기기 (SBA)는 SBA의 백업 등록자 역할을 하는 프런트 엔드 풀과 연결 됩니다. 프런트 엔드 풀이 비즈니스용 Skype 서버 2019로 마이그레이션될 경우에는 풀이 업그레이드 되는 동안 SBA를 프런트 엔드 풀에서 분리 해야 합니다. 풀이 비즈니스용 Skype 서버 2019로 마이그레이션된 후에는 SBA를 업그레이드 된 프런트 엔드 풀에 다시 연결할 수 있습니다. 여기에는 토폴로지 작성기의 레거시 토폴로지에서 SBA를 삭제 한 다음 SBA를 비즈니스용 Skype 서버 2019 토폴로지에 추가 하는 작업이 포함 됩니다. 레거시 SBA에 있는 사용자를 먼저 다른 프런트 엔드 풀로 이동한 후 토폴로지에 있는 SBA를 제거 해야 합니다. SBA를 비즈니스용 Skype 서버 2019 토폴로지에 추가 하 고 나면 해당 사용자는 SBA로 다시 이동할 수 있습니다. 이러한 단계는 아래에 요약되어 있습니다.
  
1. 레거시 SBA에 있는 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.
    
2. 기존 프런트 엔드 풀을 백업 등록자로 연결 해제 하려면 레거시 토폴로지에서 SBA를 제거 합니다.
    
3. 비즈니스용 Skype 서버 2019 토폴로지에 SBA를 추가 하 고이 새 프런트 엔드 풀을 백업 등록자로 구성 합니다. 
    
4. 분기 사용자를 새 비즈니스용 Skype 서버 2019 SBA로 이동 합니다.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>레거시 SBA 분기 사이트를 토폴로지에 추가

1. **토폴로지 작성기**를 엽니다.
    
2. 왼쪽 창에서 **분기 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **새 분기 사이트**를 클릭 합니다.
    
3. **새 분기 사이트 정의** 대화 상자에서 **이름**을 클릭한 다음 분기 사이트의 이름을 입력합니다.
    
4. (선택 사항) **설명**을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.
    
5. **다음**을 클릭합니다.
    
6. (선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다. 
    
    1. **구/군/시**를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.
    
    2. **시/도/지역**을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.
    
    3. 국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.
    
7. **다음**을 클릭 하 고이 사이트에서 Sba (survivable Branch 기기 또는 서버를 사용 하는 경우 **이 마법사를 닫을 때 새 sba (survivable 마법사 열기** 확인란의 선택을 취소 합니다. **마침**을 클릭합니다.
    
8. 레거시 SBA를 비즈니스용 Skype 서버 2019 프런트 엔드 풀에 연결 하려면 다음을 수행 합니다.
    
    1. 만들어진 분기 사이트를 확장합니다. 
    
    2. 레거시 버전을 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 합니다.
    
    3. **Sba (survivable Branch 기기**를 클릭 합니다.
    
9. 표시되는 마법사의 지침을 따르십시오. 마법사 항목에 대 한 자세한 내용은    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Sba (survivable 분기 어플라이언스는 모니터링 저장소에만 연결할 수 있습니다. 
  
10. 이 사이트에서 SBA 또는 지속 가능 분기 서버를 사용하지 않는 경우에는 **이 마법사가 닫히면 새 지속 가능 마법사 열기** 확인란의 선택을 취소한 다음 **마침**을 클릭합니다.
    
11. 토폴로지에 추가할 각 분기 사이트에 대해 이전 단계를 반복합니다.
    

