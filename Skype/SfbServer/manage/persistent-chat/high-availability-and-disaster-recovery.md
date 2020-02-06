---
title: 영구 채팅 서버를 위한 고가용성 및 재해 복구 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버의 고가용성 및 재해 복구를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: ea81f72dfa65fd350b7c8b8c3aaf61bee6999b34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817229"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>영구 채팅 서버를 위한 고가용성 및 재해 복구 관리
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버의 고가용성 및 재해 복구를 관리 하는 방법에 대해 알아봅니다.
  
이 항목에서는 영구 채팅 서버 장애 조치 및 실패 복구 방법에 대해 설명 합니다. 이 항목을 읽기 전에 비즈니스용 skype server [2015의 영구 채팅 서버에 대 한 고가용성 및 재해 복구 계획](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) 을 읽고 비즈니스용 [skype Server 2015의 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)해야 합니다.

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 
  
## <a name="fail-over-persistent-chat-server"></a>영구 채팅 서버 장애 조치

영구 채팅 서버에 대 한 장애 조치는 주로 수동 프로세스를 위해 설계 되었습니다.
  
장애 조치 절차는 보조 데이터 센터가 실행 중이 고, 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 다음을 포함 하 여 완전히 사용할 수 없다는 가정을 기반으로 합니다.
  
- 영구 채팅 서버 기본 데이터베이스와 영구 채팅 서버 미러 데이터베이스는 작동 하지 않습니다.
    
- 비즈니스용 Skype Server 프런트 엔드 서버가 중단 되었습니다.
    
절차는 두 가지 기본 단계를 기반으로 합니다.
  
- Mgc (기본 영구 채팅 데이터베이스)를 복구 합니다.
    
- 새 기본 데이터베이스에 대 한 미러링을 설정 합니다.
    
영구 채팅 준수 데이터베이스 (mgccomp)는 장애 조치 되지 않습니다. 이 데이터베이스의 콘텐츠는 임시 이며 준수 어댑터가 데이터를 처리 하므로 제거 됩니다. 데이터 손실을 방지 하기 위해 어댑터 출력을 올바르게 관리 하는 것은 관리자의 책임입니다.
  
영구 채팅 서버를 장애 조치할 때:
  
1. 영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거 합니다.
    
   - SQL Server Management Studio를 사용 하 여 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결 합니다.
    
   - 쿼리 창을 마스터 데이터베이스에 엽니다.
    
   - 다음 명령을 사용 하 여 로그 전달을 삭제 합니다.
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. 백업 공유의 uncopied 백업 파일을 백업 서버의 복사 대상 폴더에 복사 합니다.
    
3. 적용 되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 차례로 적용할 수 있습니다. 자세한 내용은 [방법: 트랜잭션 로그 백업 적용 (transact-sql)](https://go.microsoft.com/fwlink/p/?linkid=247428)을 참조 하세요.
    
4. 백업 mgc 데이터베이스를 온라인 상태로 전환 합니다. 1b 단계에서 열리는 쿼리 창을 사용 하 여 다음을 수행 합니다.
    
   - Mgc 데이터베이스에 대 한 모든 연결 (있는 경우)을 종료 합니다.
    
   - **exec** 는 mgc 데이터베이스 연결을 식별 하는 sp_who2.
    
   - ** \<spid\> 를 중단** 하 여 이러한 연결을 종료 합니다.
    
   - 데이터베이스를 온라인 상태로 만듭니다.
    
   - **복구로 데이터베이스 mgc를 복원**합니다.
    
5. 비즈니스용 Skype Server Management Shell에서 명령 **집합-CsPersistentChatState "서비스: atl-cs-001.litwareinc.com"-PoolState FailedOver** 를 사용 하 여 mgc 백업 데이터베이스로 장애 조치 합니다. Atl-cs-001.litwareinc.com에 대 한 영구 채팅 풀의 정규화 된 도메인 이름을 대체 하세요.
    
    Mgc 백업 데이터베이스는 이제 기본 데이터베이스로 작동 합니다.
    
6. 비즈니스용 Skype Server Management Shell에서 **CsMirrorDatabase** cmdlet을 사용 하 여 이제 기본 데이터베이스로 작동 하는 백업 데이터베이스에 대 한 고가용성 미러를 설정 합니다. 백업 데이터베이스 인스턴스를 기본 데이터베이스로 사용 하 고, 미러 인스턴스로 백업 미러 데이터베이스 인스턴스를 사용 합니다. 이는 처음에 설치 하는 동안 기본 데이터베이스에 대해 구성 된 것과는 다른 미러와 동일 합니다.
    
7. 영구 채팅 서버 활성 서버를 설정 합니다. 비즈니스용 Skype 서버 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.
    
    > [!IMPORTANT]
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다. 
  
    이 시점에서 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로 장애 조치 (failover)가 성공적으로 완료 됩니다.
    
## <a name="fail-back-persistent-chat-server"></a>영구 채팅 서버 장애 복구

이 절차에서는 영구 채팅 서버 오류에서 복구 하 고 기본 데이터 센터에서 작업을 다시 설정 하는 데 필요한 단계에 대해 설명 합니다.
  
영구 채팅 서버 장애가 발생 한 경우 기본 데이터 센터에서 중단 되 고 기본 및 미러 데이터베이스를 사용할 수 없게 됩니다. 주 데이터 센터가 백업 서버로 장애 조치 됩니다.
  
다음 절차는 기본 데이터 센터를 백업한 후에 정상 작업을 복원 하 고 서버를 다시 작성 했습니다. 이 절차에서는 기본 데이터 센터가 총 중단 으로부터 복구 되었고, mgc 데이터베이스와 mgccomp 데이터베이스가 토폴로지 작성기를 사용 하 여 다시 작성 되 고 다시 설치 되었다고 가정 합니다.
  
또한이 절차에서는 장애 조치 기간 동안 새 미러 및 백업 서버가 배포 되지 않은 것으로 가정 하 고 이전에는 영구 채팅 서버에서 장애 조치에 정의 된 것 처럼 백업 서버와 미러 서버만 배포 합니다.
  
이러한 단계는 재해가 발생 하기 이전에 구성을 복구 하도록 설계 되었으며, 결과적으로 주 서버에서 백업 서버로 장애 조치를 수행 합니다.
  
1. 비즈니스용 Skype 서버 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 영구 채팅 서버 활성 서버 목록에서 모든 서버를 지웁니다. 이렇게 하면 장애 복구 하는 동안 mgc 데이터베이스 및 mgccomp 데이터베이스에 연결 하는 모든 영구 채팅 서버가 중지 됩니다.
    
    > [!IMPORTANT]
    > 보조 영구 채팅 서버 백 엔드 서버의 SQL Server 에이전트는 특권 계정으로 실행 되어야 합니다. 특히, 계정에는 다음이 포함 되어야 합니다. 
  
   - 백업이 저장 되는 네트워크 공유에 대 한 읽기 액세스입니다.
    
   - 백업을 복사할 특정 로컬 디렉터리에 대 한 쓰기 액세스입니다.
    
2. Backup mgc 데이터베이스에서 미러링을 사용 하지 않도록 설정 합니다.
    
   - SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.
    
   - Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **미러**를 클릭 합니다.
    
   - **미러링 제거**를 클릭 합니다.
    
   - **확인**을 클릭합니다.
    
   - Mgccomp 데이터베이스에 대해 동일한 단계를 수행 합니다.
    
3. 새 기본 데이터베이스로 복원할 수 있도록 mgc 데이터베이스를 백업 합니다.
    
   - SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.
    
   - Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **백업을**클릭 합니다. **데이터베이스 백업** 대화 상자가 나타납니다.
    
   - **백업 유형에**서 Full ( **전체**)을 선택 합니다.
    
   - **백업 구성 요소**를 보려면 **데이터베이스**를 클릭 합니다.
    
   - **이름**에 제시 된 기본 백업 집합 이름을 그대로 사용 하거나 백업 집합에 다른 이름을 입력 합니다.
    
   -  * \<선택\> 사항*  **설명**에 백업 집합에 대 한 설명을 입력 합니다.
    
   - 대상 목록에서 기본 백업 위치를 제거 합니다.
    
   - 로그 전달을 위해 설정한 공유 위치의 경로를 사용 하 여 목록에 파일을 추가 합니다. 이 경로는 기본 데이터베이스와 백업 데이터베이스에서 사용할 수 있습니다.
    
   - **확인** 을 클릭 하 여 대화 상자를 닫고 백업 프로세스를 시작 합니다.
    
4. 이전 단계에서 만든 백업 데이터베이스를 사용 하 여 기본 데이터베이스를 복원 합니다.
    
   - SQL Server Management Studio를 사용 하 여 기본 mgc 인스턴스에 연결 합니다.
    
   - Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**, **복원을**차례로 가리킨 다음 **데이터베이스**를 클릭 합니다. **데이터베이스 복원** 대화 상자가 나타납니다.
    
   - **장치에서를**선택 합니다.
    
   - 찾아보기 단추를 클릭 하 여 **백업 지정** 대화 상자를 엽니다. **백업 미디어**에서 **파일**을 선택 합니다. **추가**를 클릭 하 고 3 단계에서 만든 백업 파일을 선택한 다음 **확인**을 클릭 합니다.
    
   - **복원할 백업 세트 선택**에서 백업을 선택 합니다.
    
   - **페이지 선택** 창에서 **옵션** 을 클릭 합니다.
    
   - **복원 옵션**에서 **기존 데이터베이스 덮어쓰기를**선택 합니다.
    
   - **복구 상태**에서 **데이터베이스를 사용할 준비가 된 상태로 둡니다**.를 선택 합니다.
    
   - **확인** 을 클릭 하 여 복원 프로세스를 시작 합니다.
    
5. 기본 데이터베이스에 대 한 SQL Server 로그 전달을 구성 합니다. [비즈니스용 Skype server 2015의 영구 채팅 서버에 대해 고가용성 및 재해 복구 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) 절차를 따라 기본 mgc 데이터베이스에 대 한 로그 전달을 설정 합니다.
    
6. 영구 채팅 서버 활성 서버를 설정 합니다. 비즈니스용 Skype 서버 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.
    
    > [!IMPORTANT]
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다. 
  
풀을 정상 상태로 복원 하려면 다음 Windows PowerShell 명령을 실행 합니다.
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

자세한 내용은 [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  

