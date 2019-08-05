---
title: SCOM 모니터링 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft 비즈니스용 Skype Server 2019으로 마이그레이션한 후 System Center Operations Manager와 함께 작동 하도록 비즈니스용 Skype Server 2019를 구성 하는 몇 가지 작업을 완료 해야 합니다.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190026"
---
# <a name="configure-scom-monitoring"></a>SCOM 모니터링 구성

비즈니스용 Skype Server 2019으로 마이그레이션한 후 System Center Operations Manager와 함께 작동 하도록 비즈니스용 Skype Server 2019를 구성 하는 몇 가지 작업을 완료 해야 합니다.
  
- 중앙 검색 논리를 관리 하기 위해 선택한 서버에 업데이트를 적용 합니다.
    
- 중앙 검색 후보 서버 레지스트리 키를 업데이트 합니다.
    
- 기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 노드를 재정의 합니다.
    
각 작업을 수행 하기 위한 지침은 아래에서 제공 합니다.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>중앙 검색 논리를 관리 하기 위해 선택한 서버에 업데이트를 적용 합니다.

1. System Center Operations Manager 에이전트 파일이 설치 되어 있고 후보 검색 노드로 구성 된 서버를 선택할 수 있습니다. 
    
2. 이 서버에 업데이트를 적용 합니다. [업데이트 적용](apply-updates.md)항목을 참조 하세요.
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>중앙 검색 후보 서버 레지스트리 키를 업데이트 합니다.

1. 중앙 검색 논리를 관리 하도록 선택한 서버에서 Windows PowerShell 명령 창을 엽니다. 
    
2. 명령줄에 다음을 입력 합니다.
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > 레지스트리를 편집할 때마다 레지스트리 키가 이미 있는 경우 명령에 실패 하는 오류가 발생할 수 있습니다. 이 문제가 발생 하는 경우 오류를 무시 해도 됩니다. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>후보 중앙 검색 감시자 노드를 재정의 하도록 기본 System Center Operations Manager 관리 서버를 구성 합니다.

1. System Center Operations Manager 콘솔이 설치 된 컴퓨터에서 **관리 팩 개체** 를 확장 한 다음 **개체**검색을 선택 합니다.
    
2. **범위 변경을** 클릭 합니다.
    
3. **범위 관리 팩 개체** 페이지에서 **LS 검색 후보**를 선택 합니다.
    
4. **LS 검색 후보 유효 값** 을 이전 절차에서 선택한 후보 서버의 이름으로 재정의 합니다. 
    
변경 내용을 마무리 하려면 System Center Operations Manager 루트 관리 서버에서 상태 서비스를 다시 시작 합니다.
  

