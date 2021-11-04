---
title: 2015년 8월의 영구 채팅 서버에 대한 고가용성 비즈니스용 Skype 서버 복구 관리
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '요약: 2015년 8월에 영구 채팅 서버 고가용성 및 재해 복구를 관리하는 방법을 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 3b45f38f1a530e91b75693196c5e64e206b10121
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774768"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>2015년 8월의 영구 채팅 서버에 대한 고가용성 비즈니스용 Skype 서버 복구 관리
 
**요약:** 2015년 8월에 영구 채팅 서버 고가용성 및 재해 복구를 관리하는 방법을 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
  
이 항목에서는 영구 채팅 서버 장애 조치(fail over) 및 장애 조치(fail back)를 설명합니다. 이 항목을 읽기 전에 [Plan for high availability and disaster recovery for Persistent Chat Server in 비즈니스용 Skype 서버 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) 및 Configure high availability and disaster recovery for [Persistent Chat Server in 비즈니스용 Skype 서버 2015을](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)읽어야 합니다.

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 
  
## <a name="fail-over-persistent-chat-server"></a>영구 채팅 서버 장애 조치(fail over)

영구 채팅 서버에 대한 장애 조치(failover)는 주로 수동 프로세스로 설계되어 있습니다.
  
장애 조치(failover) 절차는 보조 데이터 센터가 운영되고 있지만 다음을 포함하여 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 완전히 사용할 수 없다고 가정합니다.
  
- 영구 채팅 서버 기본 데이터베이스 및 영구 채팅 서버 미러 데이터베이스가 다운되었습니다.
    
- 비즈니스용 Skype 서버 프런트 엔드 서버가 다운됩니다.
    
이 절차는 다음과 같은 두 기본 단계를 기반으로 합니다.
  
- 기본 영구 채팅 데이터베이스(mgc)를 복구합니다.
    
- 새 주 데이터베이스에 대해 미러링을 설정합니다.
    
영구 채팅 준수 데이터베이스(mgccomp)는 실패하지 않습니다. 이 데이터베이스의 콘텐츠는 일시적인 항목이며 준수 어댑터가 데이터를 처리하면 삭제됩니다. 데이터 손실을 방지하기 위해 어댑터 출력을 올바르게 관리하는 것은 영구 채팅 관리자의 책임입니다.
  
영구 채팅 서버를 장애 조치(fail over)하는 경우:
  
1. 영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거합니다.
    
   - SQL Server Management Studio 사용하여 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결합니다.
    
   - 마스터 데이터베이스에 대한 쿼리 창을 엽니다.
    
   - 다음 명령을 사용하여 로그 전달을 삭제합니다.
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. 복사되지 않은 백업 파일을 백업 공유에서 백업 서버의 복사 대상 폴더로 복사합니다.
    
3. 시퀀스에서 적용되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 적용합니다. 자세한 내용은 방법: 트랜잭션 로그 백업 [적용(Transact-SQL)을 참조합니다.](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))
    
4. 백업 mgc 데이터베이스를 온라인 상태로 설정합니다. 1b단계에서 연 쿼리 창을 사용하여 다음을 수행합니다.
    
   - mgc 데이터베이스에 대한 연결이 있는 경우 모두 종료합니다.
    
   - **exec sp_who2** mgc 데이터베이스에 대한 연결을 식별하는 데 사용됩니다.
    
   - **kill \<spid\>** 를 사용하여 이러한 연결을 종료합니다.
    
   - 데이터베이스를 온라인 상태로 설정합니다.
    
   - **복구를 통해 데이터베이스 mgc를 복원합니다.**
    
5. 비즈니스용 Skype 서버 관리 셸에서 **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** 명령을 사용하여 mgc 백업 데이터베이스로 장애 조치(failover)합니다. 영구 채팅 풀의 정식 도메인 이름을 영구 채팅 풀로 대체해야 atl-cs-001.litwareinc.com.
    
    이제 mgc 백업 데이터베이스가 주 데이터베이스로 사용됩니다.
    
6. 비즈니스용 Skype 서버 관리 셸에서 **Install-CsMirrorDatabase** cmdlet을 사용하여 현재 기본 데이터베이스 역할을 하는 백업 데이터베이스에 대한 고가용성 미러를 설정할 수 있습니다. 백업 데이터베이스 인스턴스를 주 데이터베이스로, 백업 미러 데이터베이스 인스턴스를 미러 인스턴스로 사용합니다. 이 미러는 설치 중에 주 데이터베이스에 대해 처음 구성한 미러와는 다릅니다.
    
7. 영구 채팅 서버 활성 서버를 설정하십시오. 관리 비즈니스용 Skype 서버 **Set-CsPersistentChatActiveServer** cmdlet을 사용하여 활성 서버 목록을 설정할 수 있습니다.
    
    > [!IMPORTANT]
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 배치하거나 데이터베이스에 대한 연결 대기 시간이 낮고 대역폭이 높은 데이터 센터에 배치해야 합니다. 
  
    이때 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로의 장애 조치(failover)가 성공적으로 완료됩니다.
    
## <a name="fail-back-persistent-chat-server"></a>영구 채팅 서버 장애 조치(fail back)

이 절차에서는 영구 채팅 서버 오류로부터 복구하고 기본 데이터 센터에서 작업을 다시 설정하는 데 필요한 단계를 간략하게 설명합니다.
  
영구 채팅 서버 오류가 발생하면 기본 데이터 센터가 전체 중단되고 기본 및 미러 데이터베이스를 사용할 수 없게 됩니다. 기본 데이터 센터는 백업 서버로 장애 조치(failover)됩니다.
  
다음 절차에서는 기본 데이터 센터가 백업되고 서버를 다시 구축한 후에 일반 작업을 복원합니다. 이 절차에서는 기본 데이터 센터가 총 정전으로부터 복구되고, 토폴로지 작성기에서 mgc 데이터베이스와 mgccomp 데이터베이스를 다시 구축하고 다시 설치했다고 가정합니다.
  
또한 이 절차에서는 장애 조치(failover) 기간 동안 새 미러 및 백업 서버가 배포되지 않고 이전에 영구 채팅 서버 장애 조치(Failover)에 정의된 백업 서버와 해당 미러 서버만 배포된 것으로 가정합니다.
  
이러한 단계는 구성을 재해 이전의 상태로 복구하여 기본 서버를 백업 서버로 장애 조치(failover)하도록 디자인되었습니다.
  
1. 비즈니스용 Skype 서버 관리 셸에서 **Set-CsPersistentChatActiveServer** cmdlet을 사용하여 영구 채팅 서버 활성 서버 목록의 모든 서버를 비즈니스용 Skype 서버 합니다. 이렇게 하여 장애 조치(failback) 중에 모든 영구 채팅 서버가 mgc 데이터베이스 및 mgccomp 데이터베이스에 연결할 수 없습니다.
    
    > [!IMPORTANT]
    > 보조 SQL Server 영구 채팅 서버 백 엔드 서버의 보안 에이전트가 권한 있는 계정으로 실행되고 있습니다. 특히 이 계정은 다음과 같은 권한을 포함해야 합니다. 
  
   - 백업을 배치 중인 네트워크 공유에 대한 읽기 액세스 권한
    
   - 백업을 복사 중인 특정 로컬 디렉터리에 대한 쓰기 액세스 권한
    
2. 백업 mgc 데이터베이스에서 미러링 해제:
    
   - 이 SQL Server Management Studio 사용하여 백업 mgc 인스턴스에 연결합니다.
    
   - mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업** 을 가리킨 후 **미러** 를 클릭합니다.
    
   - **미러링 제거** 를 클릭합니다.
    
   - **확인** 을 클릭합니다.
    
   - mgccomp 데이터베이스에서도 같은 단계를 수행합니다.
    
3. 새 기본 데이터베이스로 복원할 수 있도록 mgc 데이터베이스를 백업합니다.
    
   - 이 SQL Server Management Studio 사용하여 백업 mgc 인스턴스에 연결합니다.
    
   - mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업** 을 가리킨 후 **백업** 을 클릭합니다. **데이터베이스 백업** 대화 상자가 나타납니다.
    
   - **백업 유형** 에서 **전체** 를 선택합니다.
    
   - **백업 구성 요소** 에 대해 **데이터베이스** 를 클릭합니다.
    
   - **이름** 에 제안된 기본 백업 집합 이름을 사용하거나 백업 집합에 대해 다른 이름을 입력합니다.
    
   -  *\<Optional\>***설명에** 백업 세트에 대한 설명을 입력합니다.
    
   - 대상 목록에서 기본 백업 위치를 제거합니다.
    
   - 로그 전달을 위해 설정한 공유 위치에 대한 경로를 사용해서 목록에 파일을 추가합니다. 이 경로는 기본 데이터베이스 및 백업 데이터베이스 모두 사용할 수 있습니다.
    
   - **확인** 을 클릭하여 대화 상자를 닫고 백업 프로세스를 시작합니다.
    
4. 이전 단계에서 만든 백업 데이터베이스를 사용하여 기본 데이터베이스를 복원합니다.
    
   - 이 SQL Server Management Studio 기본 mgc 인스턴스에 연결합니다.
    
   - mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업**, **복원** 을 차례로 클릭한 후 **데이터베이스** 를 클릭합니다. **데이터베이스 복원** 대화 상자가 나타납니다.
    
   - **장치에서** 를 선택합니다.
    
   - 찾아보기 단추를 클릭하여 **백업 지정** 대화 상자를 엽니다. **백업 미디어** 에서 **파일** 을 선택합니다. **추가** 를 클릭하고 3단계에서 만든 백업 파일을 선택한 후 **확인** 을 클릭합니다.
    
   - **복원할 백업 집합 선택** 에서 백업을 선택합니다.
    
   - **페이지 선택** 창에서 **옵션** 을 클릭합니다.
    
   - **복원 옵션** 에서 **기존 데이터베이스 덮어쓰기** 를 선택합니다.
    
   - **복구 상태** 에서 **데이터베이스를 사용할 수 있는 상태로 유지합니다.** 를 선택합니다.
    
   - **확인** 을 클릭하여 복원 프로세스를 시작합니다.
    
5. 기본 SQL Server 로그 전달을 구성합니다. Configure high [availability and disaster recovery for Persistent Chat Server in 비즈니스용 Skype 서버 2015의](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) 절차에 따라 기본 mgc 데이터베이스에 대한 로그 전달을 설정할 수 있습니다.
    
6. 영구 채팅 서버 활성 서버를 설정하십시오. 관리 비즈니스용 Skype 서버 **Set-CsPersistentChatActiveServer** cmdlet을 사용하여 활성 서버 목록을 설정할 수 있습니다.
    
    > [!IMPORTANT]
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 배치하거나 데이터베이스에 대한 연결 대기 시간이 낮고 대역폭이 높은 데이터 센터에 배치해야 합니다. 
  
풀을 정상 상태로 복원하기 위해 다음 Windows PowerShell 실행합니다.
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

자세한 내용은 [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
