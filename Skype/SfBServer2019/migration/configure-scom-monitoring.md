---
title: SCOM 모니터링 구성
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
description: Microsoft 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 System Center Operations Manager에서 작동 하도록 비즈니스용 Skype 서버 2019을 구성 하기 위한 몇 가지 작업을 완료 해야 합니다.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754048"
---
# <a name="configure-scom-monitoring"></a>SCOM 모니터링 구성

비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 몇 가지 작업을 완료 하 여 비즈니스용 Skype 서버 2019에서 System Center Operations Manager와 함께 작동 하도록 구성 해야 합니다.
  
- 중앙 검색 논리를 관리 하도록 선택한 서버에 업데이트를 적용 합니다.
    
- 중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.
    
- 기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 노드를 재정의 합니다.
    
이러한 각 작업의 수행 지침은 아래에 제공되어 있습니다.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>중앙 검색 논리를 관리 하도록 선택한 서버에 업데이트를 적용 합니다.

1. System Center Operations Manager 에이전트 파일을 설치하고 후보 검색 노드로 구성할 서버를 선택합니다. 
    
2. 이 서버에 업데이트를 적용 합니다. [Apply updates](apply-updates.md)항목을 참조 하십시오.
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.

1. 중앙 검색 논리를 관리 하도록 선택한 서버에서 Windows PowerShell 명령 창을 엽니다. 
    
2. 명령줄에 다음을 입력합니다.
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > 레지스트리를 편집할 때마다 레지스트리 키가 이미 있으면 명령이 실패했다는 오류가 발생할 수 있습니다. 이 문제가 발생할 경우 오류를 무시해도 됩니다. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 감시자 노드를 재정의 합니다.

1. System Center Operations Manager 콘솔이 설치된 컴퓨터에서 **관리 팩 개체**를 확장한 후 **개체 검색**을 선택합니다.
    
2. **범위 변경을** 클릭
    
3. **관리 팩 개체 범위 지정** 페이지에서 **LS 검색 후보**를 선택합니다.
    
4. **LS 검색 후보 유효 값**을 이전 절차에서 선택한 후보 서버의 이름으로 바꿉니다. 
    
변경 내용을 마무리 하려면 System Center Operations Manager 루트 관리 서버에서 상태 서비스를 다시 시작 합니다.
  

