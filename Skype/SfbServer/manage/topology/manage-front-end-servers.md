---
title: 비즈니스용 Skype 서버에서 프런트 엔드 서버 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '요약: 비즈니스용 Skype 서버에서 프런트 엔드 서버를 추가, 제거, 패치 또는 업데이트 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187104"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 프런트 엔드 서버 관리
 
이 문서에서는 프런트 엔드 서버를 추가 또는 제거 하는 방법과 프런트 엔드 서버에 업그레이드 또는 패치를 적용 하는 방법에 대해 설명 합니다.

## <a name="add-or-remove-front-end-servers"></a>프런트 엔드 서버 추가 또는 제거
  
풀에 프런트 엔드 서버를 추가 하거나 풀에서 프런트 엔드 서버를 제거 하는 경우에는 풀을 다시 시작 해야 합니다. 
  
> [!IMPORTANT]
> 토폴로지에 있는 풀에 서버를 추가 하거나 제거 하 고 업데이트 된 토폴로지를 게시 하면 풀의 모든 서버가 동시에 다시 시작 됩니다. 서버가 풀을 다시 시작 하는 동안에는 해당 풀에 연결 된 사용자에 대 한 서비스를 중단 하는 동안 오프 라인 상태가 됩니다. 사용자에 대 한 서비스 중단을 방지 하려면 업무 외 시간에 풀에 새 서버를 사용 하 여 토폴로지를 게시 하도록 계획 합니다. 
  
프런트 엔드 서버를 추가 하거나 제거 하는 경우 다음 절차를 사용할 수 있습니다.
  
> [!NOTE]
> 풀에 새 서버를 추가 하는 경우 새 풀 서버를 풀의 기존 서버와 동일한 누적 업데이트 수준으로 업데이트 합니다. 
  
### <a name="to-add-or-remove-front-end-servers"></a>프런트 엔드 서버를 추가 하거나 제거 하려면

1. 프런트 엔드 서버를 제거 하는 경우 먼저 해당 서버에 대 한 새 연결을 중지 합니다. 이렇게 하려면 다음 cmdlet을 사용 하면 됩니다.
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. 토폴로지 작성기를 열고 필요한 서버를 추가 또는 제거 합니다. 
    
3. 토폴로지를 게시 합니다.
    
    > [!IMPORTANT]
    > 토폴로지에 있는 풀에 서버를 추가 하거나 제거 하 고 업데이트 된 토폴로지를 게시 하면 풀의 모든 서버가 동시에 다시 시작 됩니다. 서버가 풀을 다시 시작 하는 동안에는 해당 풀에 연결 된 사용자에 대 한 서비스를 중단 하는 동안 오프 라인 상태가 됩니다. 사용자에 대 한 서비스 중단을 방지 하려면 업무 외 시간에 풀에 새 서버를 사용 하 여 토폴로지를 게시 하도록 계획 합니다. 
  
  > [!NOTE]
> 또한 풀에 서버를 추가 하거나 제거할 때 추가 또는 제거 된 각 컴퓨터에서 비즈니스용 Skype 서버 배포 마법사를 실행 해야 합니다. 자세한 내용은 [토폴로지에 있는 서버에 비즈니스용 Skype 서버 설치](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) 를 참조 하세요.
  
4. 프런트 엔드 풀의 서버 수를 다음 방법 중 하나로 변경한 경우 다음 cmdlet을 입력 하 여 풀을 다시 설정 합니다. CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2에 모두
    
     - 모두 2
    
     - 3 ~ any
    
     - 모두 3
    
5. 다음 cmdlet을 입력 하 여 풀을 다시 시작 합니다.
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>프런트 엔드 서버 패치 또는 업데이트

프런트 엔드 풀에 서버를 패치 하는 경우 한 번에 하나의 서버를 수행 합니다. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>풀의 프런트 엔드 서버에 업그레이드를 적용 하려면

1. 다음 cmdlet을 입력 합니다.
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     이 cmdlet에 누락 된 복제본이 표시 되는 경우 패치를 적용 하기 전에 다음 cmdlet을 실행 하 여 풀을 복구 합니다.
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 패치를 적용할 첫 번째 서버에서 다음 cmdlet을 실행 합니다.
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    이 cmdlet은 모든 서비스를 풀의 다른 프런트 엔드 서버로 이동 하 고이 서버를 오프 라인 상태로 전환 합니다.
    
3. 이 서버에 업그레이드 또는 패치를 적용 합니다.
    
4. 업그레이드 된 서버에서 다음 cmdlet을 실행 합니다.
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    서버가 서비스에 반환 됩니다.
    
5. 업그레이드 해야 하는 각 서버에 대해 2-4 단계를 반복 합니다.
    
