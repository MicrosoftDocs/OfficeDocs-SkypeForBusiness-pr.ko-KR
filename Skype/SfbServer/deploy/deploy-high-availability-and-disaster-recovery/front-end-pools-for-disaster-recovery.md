---
title: 비즈니스용 Skype 서버에서 재해 복구용으로 쌍을 이루는 프런트 엔드 풀 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 페어링 된 프런트 엔드 풀을 사용 하 여 재해 복구 보호를 제공 하기로 결정할 수 있지만, 반드시 그럴 필요는 없습니다.
ms.openlocfilehash: 550c336569b604ae20199b419dc104af0609c775
ms.sourcegitcommit: e43a66a7f769f855dc45c1bb7f83636d0390949b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "39254397"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 재해 복구용으로 쌍을 이루는 프런트 엔드 풀 배포
 
페어링 된 프런트 엔드 풀을 사용 하 여 재해 복구 보호를 제공 하기로 결정할 수 있지만, 반드시 그럴 필요는 없습니다.
  
토폴로지 작성기를 사용 하 여 페어링 된 프런트 엔드 풀의 장애 복구 토폴로지를 쉽게 배포할 수 있습니다. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>프런트 엔드 풀 쌍을 배포 하려면

1. 풀이 신규이 고 아직 정의 되지 않은 경우 토폴로지 작성기를 사용 하 여 풀을 만듭니다.
    
2. 토폴로지 작성기에서 두 풀 중 하나를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    
3. 왼쪽 창에서 **복구 력을** 클릭 한 다음 오른쪽 창에서 **연결 된 백업 풀** 을 선택 합니다.
    
4. **연결 된 백업 풀**아래 상자에서이 풀과 페어링 할 풀을 선택 합니다. 다른 풀과 아직 페어링되지 않은 기존 풀만 선택할 수 있습니다.
    
5. **자동 장애 조치 및 음성 장애 복구**를 선택한 다음 **확인**을 클릭 합니다.
    
    이 풀에 대 한 세부 정보를 볼 때 이제 오른쪽 창의 **복원 력**아래에 연결 된 풀이 표시 됩니다. 
    
6. 토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다.
    
7. 두 풀이 아직 배포 되지 않은 경우 지금 배포 하면 구성이 완료 됩니다. 이 절차의 마지막 단계를 건너뛸 수 있습니다.
    
    그러나 짝이 되는 관계를 정의 하기 전에 풀이 이미 배포 된 경우 다음의 마지막 단계를 완료 해야 합니다.
    
8. 두 풀의 모든 프런트 엔드 서버에서 다음을 실행 합니다.
    
   ```
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    이렇게 하면 백업 페어링에 필요한 다른 서비스가 제대로 작동 합니다.
    
9. 부트스트래퍼가 두 풀의 모든 프런트 엔드 서버에 있는 백업 연결에 필요한 구성 요소를 설치 하는 것을 마치면, 두 풀의 프런트 엔드 서버에 이전에 적용 한 기존 누적 업데이트를 다시 적용 한 후 계속 합니다. 다음 단계로 이동 합니다.

10. 비즈니스용 Skype 서버 관리 셸 명령 프롬프트에서 다음을 실행 합니다. 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. 다음 cmdlet을 사용 하 여 두 풀의 사용자 및 컨퍼런스 데이터를 서로 동기화 합니다.
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    데이터를 동기화 하는 데 시간이 걸릴 수 있습니다. 다음 cmdlet을 사용 하 여 상태를 확인할 수 있습니다. 두 방향의 상태가 모두 안정 된 상태 인지 확인 합니다.
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> **자동 장애 조치 및 음성 복구** 옵션 및 토폴로지 작성기의 관련 시간 간격은 Lync Server에 도입 된 음성 복원 기능에만 적용 됩니다. 이 옵션을 선택 하면이 문서에서 설명 하는 풀 장애 조치 (failover)가 자동으로 수행 된다는 의미는 아닙니다. 풀 장애 조치 및 장애 복구를 위해 관리자는 항상 장애 조치 및 장애 복구 cmdlet을 수동으로 호출 해야 합니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 프론트 엔드 풀 재해 복구](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
