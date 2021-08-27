---
title: 서버의 프런트 엔드 서버 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '요약: 서버에서 프런트 엔드 서버를 추가, 제거, 패치 또는 업데이트하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 4a58eb7ab54102d1287a61a9f736b9d0c1a87108
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578792"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>서버의 프런트 엔드 서버 비즈니스용 Skype 서버
 
이 문서에서는 프런트 엔드 서버를 추가 또는 제거하는 방법과 프런트 엔드 서버에 업그레이드 또는 패치를 적용하는 방법에 대해 설명합니다.

  > [!NOTE]
> 비즈니스용 Skype 서버 2019에서는 프런트 엔드 서버가 Enterprise Edition 프런트 엔드 풀을 지원하지 않습니다. 이 시나리오에서는 토폴로지가 게시될 수 없습니다.

## <a name="add-or-remove-front-end-servers"></a>프런트 엔드 서버 추가 또는 제거
  
풀에 프런트 엔드 서버를 추가하거나 풀에서 프런트 엔드 서버를 제거할 때 풀을 다시 시작해야 합니다. 
  
> [!IMPORTANT]
> 토폴로지의 풀에 서버를 추가하거나 제거한 다음 업데이트된 토폴로지 게시하면 풀의 모든 서버가 동시에 다시 시작됩니다. 서버가 풀을 다시 시작하는 동안에는 풀이 오프라인 상태이면 해당 풀에 연결된 사용자의 서비스가 중단됩니다. 사용자에게 서비스가 중단되지 않도록 업무 시간 동안 풀에 새 서버와 함께 토폴로지 게시를 계획합니다. 
  
프런트 엔드 서버를 추가하거나 제거할 때 다음 절차를 사용할 수 있습니다.
  
> [!NOTE]
> 풀에 새 서버를 추가하는 경우 새 풀 서버를 풀의 기존 서버와 동일한 누적 업데이트 수준으로 업데이트합니다. 
  
### <a name="to-add-or-remove-front-end-servers"></a>프런트 엔드 서버를 추가하거나 제거하려면

1. 프런트 엔드 서버를 제거하는 경우 먼저 해당 서버에 대한 새 연결을 중지합니다. 이렇게 하여 다음 cmdlet을 사용할 수 있습니다.
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. 토폴로지 작성기를 열고 필요한 서버를 추가하거나 제거합니다. 
    
3. 토폴로지를 게시합니다.
    
    > [!IMPORTANT]
    > 토폴로지의 풀에 서버를 추가하거나 제거한 다음 업데이트된 토폴로지 게시하면 풀의 모든 서버가 동시에 다시 시작됩니다. 서버가 풀을 다시 시작하는 동안에는 풀이 오프라인 상태이면 해당 풀에 연결된 사용자의 서비스가 중단됩니다. 사용자에게 서비스가 중단되지 않도록 업무 시간 동안 풀에 새 서버와 함께 토폴로지 게시를 계획합니다. 
  
  > [!NOTE]
> 또한 풀에 서버를 추가하거나 제거할 때 추가되거나 제거된 각 컴퓨터에서 비즈니스용 Skype 서버 배포 마법사를 실행해야 합니다. 자세한 내용은 토폴로지의 서버에 비즈니스용 Skype 서버 설치를 [참조하세요.](../../deploy/install/install-skype-for-business-server.md)
  
4. 프런트 엔드 풀의 서버 수를 변경한 경우 다음 cmdlet을 입력하여 풀을 다시 설정하십시오. Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 ~ 모든
    
     - 2개까지
    
     - 3 ~ 모든
    
     - 3개까지
    
5. 다음 cmdlet을 입력하여 풀 다시 시작
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>프런트 엔드 서버 패치 또는 업데이트

프런트 엔드 풀의 서버를 패치할 때 한 서버에 한 번씩 패치를 적용합니다. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>풀의 프런트 엔드 서버에 업그레이드를 적용하려면

1. 다음 cmdlet을 입력합니다.
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     이 cmdlet에 누락된 복제본이 표시될 경우 패치를 적용하기 전에 다음 cmdlet을 실행하여 풀을 복구합니다.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 패치할 첫 번째 서버에서 다음 cmdlet을 실행합니다.
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    이 cmdlet은 모든 서비스를 풀의 다른 프런트 엔드 서버로 이동하고 이 서버를 오프라인으로 전환합니다.
    
3. 이 서버에 업그레이드 또는 패치를 적용합니다.
    
4. 업그레이드된 서버에서 다음 cmdlet을 실행합니다.
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    서버가 서비스로 반환됩니다.
    
5. 업그레이드해야 하는 각 서버에 대해 2-4단계를 반복합니다.
