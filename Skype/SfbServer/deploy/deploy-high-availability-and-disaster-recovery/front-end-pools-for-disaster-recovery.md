---
title: 비즈니스용 Skype 서버에서 재해 복구를 위해 페어링된 프런트 엔드 풀 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 페어링된 프런트 엔드 풀을 사용하여 재해 복구 보호를 제공할 수도 있지만 이렇게 할 필요는 없습니다.
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830608"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 재해 복구를 위해 페어링된 프런트 엔드 풀 배포
 
페어링된 프런트 엔드 풀을 사용하여 재해 복구 보호를 제공할 수도 있지만 이렇게 할 필요는 없습니다.
  
토폴로지 작성기에서 페어링된 프런트 엔드 풀의 재해 복구 토폴로지도 쉽게 배포할 수 있습니다. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>프런트 엔드 풀 쌍을 배포하려면

1. 풀이 아직 정의되지 않은 새 풀인 경우 토폴로지 작성기를 사용하여 풀을 만드면 됩니다.
    
2. 토폴로지 작성기에서 두 풀 중 하나를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 클릭합니다.**
    
3. 왼쪽 창에서 **탄성** 을 클릭하고 오른쪽 창에서 **연결된 백업 풀** 을 선택합니다.
    
4. **연결된 백업 풀** 아래 상자에서 이 풀과 쌍으로 지정할 풀을 선택합니다. 이미 다른 풀과 쌍으로 지정되어 있지 않은 기존 풀만 선택할 수 있습니다.
    
5. **자동 음성 장애 조치(failover) 및 장애 복구(failback)** 를 선택하고 **확인** 을 클릭합니다.
    
    이제 이 풀에 대한 세부 정보를 표시하면 연결된 풀이 오른쪽 창의 **탄성** 아래에 표시됩니다. 
    
6. 토폴로지 작성기에서 토폴로지 게시
    
7. 두 풀이 아직 배포되지 않은 경우 지금 배포하면 구성이 완료됩니다. 이 절차의 마지막 단계를 건너뛸 수 있습니다.
    
    그러나 쌍으로 된 관계를 정의하기 전에 풀이 이미 배포된 경우 다음 최종 단계를 완료해야 합니다.
    
8. 두 풀에 모두 포함되어 있는 모든 프런트 엔드 서버에서 다음을 실행합니다.
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    그러면 백업 페어링이 올바르게 작동하는 데 필요한 다른 서비스가 구성됩니다.
    
9. 부트스트래퍼가 두 풀의 모든 프런트 엔드 서버에 백업 페어링에 필요한 구성 요소의 설치를 마치면 이전에 두 풀의 이러한 프런트 엔드 서버에 적용한 기존 누적 업데이트를 다시 적용한 다음 다음 단계를 계속 진행하십시오.

10. 비즈니스용 Skype 서버 관리 셸 명령 프롬프트에서 다음을 실행합니다. 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. 다음 cmdlet을 사용하여 두 풀의 사용자 및 회의 데이터를 서로 동기화하도록 강제합니다.
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    데이터를 동기화하는 데는 시간이 걸릴 수 있습니다. 다음 cmdlet을 사용하여 상태를 확인할 수 있습니다. 두 방향의 상태가 모두 양방향 상태인지 확인
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> 음성에 대한 자동 장애 조치(failover) 및 장애 **조치(failback)** 옵션 및 토폴로지 작성기에서 연결된 시간 간격은 Lync Server에서 도입된 음성 탄력성 기능에만 적용됩니다. 해당 옵션을 선택해도 이 문서에서 설명하는 풀 장애 조치(failover)가 자동으로 수행되는 것은 아닙니다. 풀 장애 조치(failover) 및 장애 복구(failback)를 수행하려면 항상 관리자가 장애 조치(failover) 및 장애 복구(failback) cmdlet을 각각 수동으로 호출해야 합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 프런트 엔드 풀 재해 복구](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
