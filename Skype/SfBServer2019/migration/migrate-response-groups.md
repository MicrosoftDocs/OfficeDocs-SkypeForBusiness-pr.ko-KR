---
title: 응답 그룹 마이그레이션
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
description: 사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 에이전트 그룹, 큐, 워크플로, 오디오 파일 복사, 레거시 배포에서 비즈니스용 Skype 서버 2019 풀로 응답 그룹 연락처 개체 이동이 포함됩니다. 레거시 응답 그룹을 마이그레이션한 후 응답 그룹에 대한 통화는 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에 의해 처리됩니다. 응답 그룹에 대한 호출은 더 이상 레거시 풀에서 처리되지 않습니다.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752680"
---
# <a name="migrate-response-groups"></a>응답 그룹 마이그레이션

사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 에이전트 그룹, 큐, 워크플로, 오디오 파일 복사, 레거시 배포에서 비즈니스용 Skype 서버 2019 풀로 응답 그룹 연락처 개체 이동이 포함됩니다. 레거시 응답 그룹을 마이그레이션한 후 응답 그룹에 대한 통화는 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에 의해 처리됩니다. 응답 그룹에 대한 호출은 더 이상 레거시 풀에서 처리되지 않습니다.
  
> [!NOTE]
> 모든 사용자를 비즈니스용 Skype 서버 2019 풀로 이동하기 전에 응답 그룹을 마이그레이션할 수 있습니다. 그러나 모든 사용자를 먼저 이동하는 것이 좋습니다. 특히 응답 그룹 에이전트인 사용자는 비즈니스용 Skype 서버 2019 풀로 이동하기 전까지는 새로운 기능의 전체 기능을 사용할 수 없습니다. 
  
응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램을 포함하는 비즈니스용 Skype 서버 2019 풀을 배포해야 합니다. 응답 그룹 응용 프로그램은 배포할 때 기본적으로 설치되고 Enterprise Voice. **Get-CsService -ApplicationServer** cmdlet을 실행하여 응답 그룹 응용 프로그램이 설치되도록 할 수 있습니다. 
  
> [!NOTE]
> 레거시 응답 그룹을 마이그레이션하기 전에 비즈니스용 Skype 서버 2019 풀에서 새 비즈니스용 Skype 서버 2019 응답 그룹을 만들 수 있습니다. 
  
응답 그룹을 레거시 풀에서 비즈니스용 Skype 서버 2019로 마이그레이션하려면 **Move-CsRgsConfiguration** cmdlet을 실행합니다. 
  
> [!IMPORTANT]
> 응답 그룹 마이그레이션 cmdlet은 전체 풀에 대한 응답 그룹 구성을 이동합니다. 마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다. 
  
응답 그룹을 마이그레이션한 후 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 모든 에이전트 그룹, 큐 및 워크플로가 성공적으로 이동된지 확인해야 합니다. 
  
응답 그룹을 마이그레이션할 때 레거시 응답 그룹은 제거되지 않습니다. 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 마이그레이션 후 응답 그룹을 관리하는 경우 레거시 응답 그룹과 비즈니스용 Skype 서버 2019 응답 그룹을 모두 볼 수 있습니다. 비즈니스용 Skype 서버 2019 응답 그룹에만 업데이트를 적용해야 합니다. 레거시 응답 그룹은 롤백 목적으로만 보존됩니다. 
  
> [!CAUTION]
> 마이그레이션이 완료되고 새 응답 그룹이 만들어진 후 비즈니스용 Skype 서버 제어판과 비즈니스용 Skype 서버 관리 셸에는 각 응답 그룹의 레거시 및 비즈니스용 Skype 서버 2019 버전이 표시됩니다. 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 레거시 응답 그룹을 제거하지 않습니다. 하나를 제거하면 마이그레이션 중에 만들어진 해당 응답 그룹이 작동하지 않습니다. 레거시 풀을 해제하면 레거시 응답 그룹이 제거됩니다. 
  
> [!IMPORTANT]
> 풀을 해제하기 전까지는 이전 배포에서 어떠한 데이터도 제거하지 않는 것이 좋습니다. 또한 마이그레이션 직후 응답 그룹을 내보내는 것이 좋습니다. 레거시 응답 그룹을 제거해야 하는 경우 백업에서 응답 그룹을 복원하여 비즈니스용 Skype 서버 2019 응답 그룹을 다시 실행하도록 할 수 있습니다. 
  
비즈니스용 Skype 서버 2019에는 워크플로 유형이라는 새로운 응답 **그룹 기능이 도입됩니다.** **워크플로 유형** 은 **관리됨** 또는 **관리되지 않음** 일 수 있습니다. 모든 응답 그룹은 **워크플로 유형** 이 **관리되지 않음** 상태로 마이그레이션되고 관리자 목록은 비어 있습니다. 
  
**Move-CsRgsConfiguration** cmdlet을 실행하면 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 롤백 목적으로 레거시 풀에 보존됩니다. 하지만 레거시 풀로 롤백해야 하는 경우에는 **Move-CsApplicationEndpoint** cmdlet을 실행해서 연락처 개체를 다시 레거시 풀로 이동해야 합니다. 
  
다음 응답 그룹 구성 마이그레이션 절차에서는 레거시 풀과 비즈니스용 Skype 서버 2019 풀 간에 일대일 관계가 있는 것으로 가정합니다. 마이그레이션 및 배포 중에 풀을 통합하거나 분할하려는 경우 비즈니스용 Skype 서버 2019 풀에 매핑되는 레거시 풀을 계획해야 합니다.
  
## <a name="to-migrate-response-group-configurations"></a>응답 그룹 구성을 마이그레이션하려면

1. RTCUniversalServerAdmins 그룹의 구성원이거나 이와 동등한 관리자 권한 및 사용 권한을 가진 계정을 사용하여 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** **Microsoft 비즈니스용 Skype 서버 2019,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 실행:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    예를 들면 다음과 같습니다.
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 응답 그룹 및 에이전트를 비즈니스용 Skype 서버 2019 풀로 마이그레이션한 후 에이전트가 로그인 및 로그인하는 데 사용하는 URL은 비즈니스용 Skype  서버 2019 URL로 도구 메뉴에서 사용할 수 있습니다. 에이전트가 책갈피와 같은 모든 참조를 새 URL로 업데이트하도록 알립니다. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 응답 그룹 마이그레이션을 확인하려는 경우

1. RTCUniversalReadOnlyAdmins 그룹의 구성원이거나 최소한 CsViewOnlyAdministrator 역할의 구성원인 계정을 사용하여 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 [Skype 서버 2019 관리 도구 열기를 참조하세요.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx) 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 왼쪽 탐색 창에서 **응답 그룹** 을 클릭합니다.
    
4. 워크플로 **탭에서** 레거시 환경의 모든 워크플로가 목록에 포함되어 있는지 확인해야 합니다. 
    
5. 큐 **탭을** 클릭하고 레거시 환경의 모든 큐가 목록에 포함되어 있는지 확인해야 합니다. 
    
6. 그룹 **탭을** 클릭하고 레거시 환경의 모든 에이전트 그룹이 목록에 포함되어 있는지 확인해야 합니다. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 응답 그룹 마이그레이션을 확인하려는 경우

1. RTCUniversalReadOnlyAdmins 그룹의 구성원이거나 최소한 CsViewOnlyAdministrator 역할의 구성원인 계정을 사용하여 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** **Microsoft 비즈니스용 Skype 서버 2019,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
    다음 cmdlet에 대한 자세한 내용을 보려면 다음을 실행합니다.
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 실행:
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 레거시 환경의 모든 에이전트 그룹이 목록에 포함되어 있는지 확인해야 합니다.
    
5. 실행:
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 레거시 환경의 모든 큐가 목록에 포함되어 있는지 확인
    
7. 실행:
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 레거시 환경의 모든 워크플로가 목록에 포함되어 있는지 확인
    

