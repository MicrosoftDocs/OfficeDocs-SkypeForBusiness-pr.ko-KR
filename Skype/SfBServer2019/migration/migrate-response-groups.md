---
title: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 레거시 배포에서 비즈니스용 Skype Server 2019 풀로 에이전트 그룹, 큐, 워크플로, 오디오 파일, 응답 그룹 연락처 개체 복사 등이 포함 됩니다. 레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 호출이 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에서 처리 됩니다. 응답 그룹에 대 한 호출은 더 이상 레거시 풀에서 처리 되지 않습니다.
ms.openlocfilehash: 148fbe2ca547c3bd7e3d240e687b37c94d10270b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991113"
---
# <a name="migrate-response-groups"></a>응답 그룹 마이그레이션

사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 레거시 배포에서 비즈니스용 Skype Server 2019 풀로 에이전트 그룹, 큐, 워크플로, 오디오 파일, 응답 그룹 연락처 개체 복사 등이 포함 됩니다. 레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 호출이 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에서 처리 됩니다. 응답 그룹에 대 한 호출은 더 이상 레거시 풀에서 처리 되지 않습니다.
  
> [!NOTE]
> 모든 사용자를 비즈니스용 Skype Server 2019 풀로 이동 하기 전에 응답 그룹을 마이그레이션할 수 있지만, 모든 사용자를 먼저 이동 하는 것이 좋습니다. 특히 응답 그룹 에이전트를 사용 하는 사용자는 비즈니스용 Skype Server 2019 풀로 이동할 때까지 새로운 기능을 완전히 사용할 수 없습니다. 
  
응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램이 포함 된 비즈니스용 Skype 서버 2019 풀을 배포 해야 합니다. 엔터프라이즈 음성을 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다. **Get CsService-ApplicationServer** cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 설치 되어 있는지 확인할 수 있습니다. 
  
> [!NOTE]
> 레거시 응답 그룹을 마이그레이션하기 전에 비즈니스용 Skype Server 2019 풀에서 새로운 비즈니스용 Skype 서버 2019 응답 그룹을 만들 수 있습니다. 
  
레거시 풀의 응답 그룹을 비즈니스용 Skype 서버 2019로 마이그레이션하려면 **Move-CsRgsConfiguration** cmdlet을 실행 합니다. 
  
> [!IMPORTANT]
> 응답 그룹 마이그레이션 cmdlet은 전체 풀에 대 한 응답 그룹 구성을 이동 합니다. 마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다. 
  
응답 그룹을 마이그레이션한 후 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell cmdlet을 사용 하 여 모든 에이전트 그룹, 큐 및 워크플로가 성공적으로 이동 되었는지 확인 해야 합니다. 
  
응답 그룹을 마이그레이션하면 레거시 응답 그룹이 제거 되지 않습니다. 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 마이그레이션 후에 응답 그룹을 관리 하는 경우 레거시 응답 그룹과 비즈니스용 Skype 서버 2019 응답 그룹을 둘 다 볼 수 있습니다. 비즈니스용 Skype Server 2019 응답 그룹에만 업데이트를 적용 해야 합니다. 레거시 응답 그룹은 롤백 용도로만 유지 됩니다. 
  
> [!CAUTION]
> 마이그레이션이 완료 되 고 새 응답 그룹이 만들어졌으면 비즈니스용 Skype Server 제어판 및 비즈니스용 Skype 서버 관리 셸에서는 각 응답의 레거시 및 비즈니스용 Skype server 2019 버전이 표시 됩니다. 그룹과. Skype for Business Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 레거시 응답 그룹을 제거 하지 마세요. 제거 하는 경우 마이그레이션 중에 만든 해당 응답 그룹의 작동이 중지 됩니다. 레거시 풀을 해제할 때 레거시 응답 그룹이 제거 됩니다. 
  
> [!IMPORTANT]
> 풀을 해제할 때까지 이전 배포에서 데이터를 제거 하지 않는 것이 좋습니다. 또한 마이그레이션한 후 즉시 응답 그룹을 내보낼 것을 적극 권장 합니다. 레거시 응답 그룹을 제거 해야 하는 경우 백업에서 응답 그룹을 복원 하 여 비즈니스용 Skype Server 2019 응답 그룹을 다시 실행 하도록 할 수 있습니다. 
  
비즈니스용 Skype 서버 2019에는 **워크플로 유형**이라는 새 응답 그룹 기능이 도입 되었습니다. **워크플로 유형은** **관리** 또는 **비관리형**일 수 있습니다. 모든 응답 그룹은 **워크플로 유형이** **비관리형** 으로 설정 되 고 빈 관리자 목록이 있는 상태로 마이그레이션됩니다. 
  
**CsRgsConfiguration** cmdlet을 실행 하는 경우 롤백 목적으로 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 레거시 풀에 남아 있습니다. 그러나 레거시 풀로 롤백해야 하는 경우에는 요청 **이동 Applicationendpoint** cmdlet을 실행 하 여 연락처 개체를 레거시 풀로 다시 이동 해야 합니다. 
  
응답 그룹 구성을 마이그레이션하는 다음 절차에서는 레거시 풀과 비즈니스용 Skype Server 2019 풀 간에 일대일 관계를 사용 하 고 있다고 가정 합니다. 마이그레이션 및 배포 중에 풀을 통합 하거나 분할 하려는 경우 비즈니스용 Skype 서버 2019 풀에 매핑되는 레거시 풀을 계획 해야 합니다.
  
## <a name="to-migrate-response-group-configurations"></a>응답 그룹 구성을 마이그레이션하려면

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 관리자 권한이 있는 계정을 사용 하 여 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.
    
3. 런
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    예를 들면 다음과 같습니다.
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 응답 그룹 및 에이전트를 비즈니스용 Skype 서버 2019 풀로 마이그레이션한 후에는 에이전트가 로그인 하 고 로그 아웃 하는 데 사용 하는 URL이 비즈니스용 Skype Server 2019 URL 이며 **도구** 메뉴에서 사용할 수 있습니다. 상담원에 게 책갈피 등의 모든 참조를 새 URL로 업데이트 하도록 알립니다. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면

1. RTCUniversalReadOnlyAdmins 그룹의 구성원 이거나 적어도 Csviewis 관리자 역할의 구성원 인 계정으로 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2019 관리 도구 열기](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)를 참조 하세요. 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 왼쪽 탐색 창에서 **응답 그룹**을 클릭 합니다.
    
4. **워크플로** 탭에서 레거시 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다. 
    
5. **대기열** 탭을 클릭 하 고 레거시 환경의 모든 대기열이 목록에 포함 되어 있는지 확인 합니다. 
    
6. **그룹** 탭을 클릭 하 고 레거시 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면

1. RTCUniversalReadOnlyAdmins 그룹의 구성원 이거나 적어도 Csviewis 관리자 역할의 구성원 인 계정으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.
    
    다음 cmdlet에 대 한 자세한 내용을 보려면 다음을 실행 합니다.
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 런
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 레거시 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.
    
5. 런
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 레거시 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.
    
7. 런
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 레거시 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.
    

