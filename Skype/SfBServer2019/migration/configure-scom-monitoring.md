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
description: Microsoft 비즈니스용 Skype 서버 2019로 마이그레이션한 후 비즈니스용 Skype 서버 Operations Manager와 함께 작동하도록 비즈니스용 Skype 서버 몇 가지 작업을 System Center 합니다.
ms.openlocfilehash: 477fbd3c405328ffac4aa70a722120d375e95b295bf5a23d19882248d1ece54e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279616"
---
# <a name="configure-scom-monitoring"></a>SCOM 모니터링 구성

비즈니스용 Skype 서버 2019로 마이그레이션한 후 비즈니스용 Skype 서버 Operations Manager와 함께 작동하도록 비즈니스용 Skype 서버 몇 가지 작업을 System Center 합니다.
  
- 중앙 검색 논리를 관리하기 위해 선택된 서버에 업데이트를 적용합니다.
    
- 중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.
    
- 후보 중앙 System Center 노드를 다시 설정하도록 기본 작업 관리자 관리 서버를 구성합니다.
    
이러한 각 작업의 수행 지침은 아래에 제공되어 있습니다.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>중앙 검색 논리를 관리하기 위해 선택된 서버에 업데이트를 적용합니다.

1. System Center Operations Manager 에이전트 파일을 설치하고 후보 검색 노드로 구성할 서버를 선택합니다. 
    
2. 이 서버에 업데이트를 적용합니다. Apply [updates 항목을 참조하세요.](apply-updates.md)
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.

1. 중앙 검색 논리를 관리하기로 선택된 서버에서 명령 Windows PowerShell 를 니다. 
    
2. 명령줄에 다음을 입력합니다.
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > 레지스트리를 편집할 때마다 레지스트리 키가 이미 있으면 명령이 실패했다는 오류가 발생할 수 있습니다. 이 문제가 발생할 경우 오류를 무시해도 됩니다. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>후보 중앙 System Center 검색 감시자 노드를 다시 설정하도록 기본 운영 관리자 관리 서버를 구성합니다.

1. System Center Operations Manager 콘솔이 설치된 컴퓨터에서 **관리 팩 개체** 를 확장한 후 **개체 검색** 을 선택합니다.
    
2. 범위 **변경 클릭**
    
3. **관리 팩 개체 범위 지정** 페이지에서 **LS 검색 후보** 를 선택합니다.
    
4. **LS 검색 후보 유효 값** 을 이전 절차에서 선택한 후보 서버의 이름으로 바꿉니다. 
    
변경 내용을 마무리하려면 System Center Operations Manager 루트 관리 서버에서 상태 서비스를 다시 시작합니다.
  

