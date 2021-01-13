---
title: 비즈니스용 Skype 서버 통계 관리자 업그레이드
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자를 업그레이드하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821768"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>비즈니스용 Skype 서버 통계 관리자 업그레이드
 
**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 통계 관리자를 업그레이드하는 방법을 배워 읽습니다.
  
이 항목에서는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구인 비즈니스용 Skype 서버 통계 관리자의 기존 설치를 업그레이드하는 방법에 대해 설명합니다. 몇 초마다 수백 대의 서버로 성능 데이터를 폴링하고 통계 관리자 웹 사이트에서 결과를 즉시 확인할 수 있습니다. 
  
통계 관리자 및 릴리스 2.0의 새로운 기능에 대한 자세한 내용은 비즈니스용 [Skype](plan.md) 서버의 통계 관리자 계획 및 비즈니스용 Skype 서버용 통계 관리자 배포를 [참조하세요.](deploy.md)
  
업그레이드 방법에는 두 가지가 있습니다.
  
- **자동화된 업그레이드.** 이 메서드는 자동화된 스크립트를 사용합니다. 가장 쉬운 방법일 수 있으며 모든 업그레이드 시나리오에 적용할 수 있습니다.
    
- **수동 업그레이드.** 이 방법은 자동화된 업그레이드가 실패하는 비정상적인 경우 백업 계획으로 제공됩니다.
    
## <a name="prerequisites"></a>필수 구성 요소

업그레이드하기 전에 다음 정보를 제공해야 합니다.
  
- 활성 수신기 인증서 지문
    
- 수신기 서비스 암호(수신기 및 모든 에이전트 설치 시 입력)
    
- 웹 사이트에 대한 SSL 인증서 구성
    
## <a name="automated-upgrade"></a>자동화된 업그레이드

스크립트는 현재 인증서 정보 및 수신기 암호를 수집하고 이전 버전의 제품을 제거한 다음 제품의 새 버전을 설치합니다. 서버에 설치된 Redis 인스턴스는 터치되지 않습니다. 따라서 캐시에 저장된 데이터는 업그레이드 프로세스를 통해 유지됩니다.
  
1. 새 버전의 에이전트, 수신기 및 웹 사이트의 MSI 파일과 Update-StatsMan.ps1 스크립트를 수신기 컴퓨터의 단일 폴더에 배치합니다.
    
2. 관리 PowerShell 창을 열 수 있습니다. 수신기 구성 요소를 업그레이드합니다.
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> 통계 관리자 서비스 암호는 설치 관리자에 전달될 때 명령줄에 명확한 텍스트로 표시됩니다. 필요한 경우 모니터를 보호해야 합니다. 
  
1. 스크립트를 실행하는 경우 이전 버전의 제품을 제거하라는 메시지가 표시해야 합니다. 예로 대답합니다.
    
2. 수신기 서비스가 실행 중인 경우 계속하기 전에 응용 프로그램을 닫을지 묻는 메시지가 표시될 것입니다. 응용 프로그램을 닫을 수 있도록 허용합니다(Statistics Manager Listener Service가 중지됨).
    
3. 설치 프로세스를 계속합니다. 서비스 암호 및 인증서 지문이 미리 채워진 것입니다. 그렇지 않은 경우 저장한 값을 계속하기 전에 추가합니다.
    
4. 관리 PowerShell 창을 여십시오. 웹 사이트 구성 요소를 업그레이드합니다.
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. 스크립트를 실행하는 경우 이전 버전의 제품을 제거하라는 메시지가 표시해야 합니다. 예로 대답합니다.
    
6. 에이전트 서비스가 실행 중인 경우 계속하기 전에 응용 프로그램을 닫하라는 메시지가 표시될 것입니다. 응용 프로그램을 닫을 수 있도록 허용합니다(StatsMan 에이전트 서비스가 중지됨).
    
7. 설치 프로세스를 계속합니다. 서비스 암호 및 인증서 지문이 미리 채워진 것입니다. 그렇지 않은 경우 저장한 값을 계속하기 전에 추가합니다.
    
8. 관리 PowerShell 창을 열 수 있습니다. 에이전트 구성 요소를 업그레이드합니다.
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. 스크립트를 실행하는 경우 이전 버전의 제품을 제거하라는 메시지가 표시해야 합니다. 예로 대답합니다.
    
10. 설치 프로세스를 계속합니다. 웹 사이트 포트가 미리 채워진 것입니다. 그렇지 않은 경우 저장한 값을 계속하기 전에 추가합니다.
    
11. 브라우저를 사용하여 웹 사이트가 예상대로 작동하고 있는지 확인하세요.
    
> [!NOTE]
> 에이전트 업그레이드는 -NoPrompt 스위치와 함께 사용할 수 있습니다. 이렇게 하면 제거/설치 프로세스가 자동으로 실행되므로 PSExec 같은 도구가 많은 서버에서 원격으로 업그레이드를 실행할 수 있습니다. 
  
### <a name="manual-upgrade"></a>수동 업그레이드

어떤 이유로 자동 업그레이드가 실패하면 항상 다음과 같이 수동 업그레이드를 수행할 수 있습니다.
  
1. 수신기 컴퓨터에서 프로그램 및 기능 제어판을 통해 수신기, 웹 사이트 및 에이전트(이 서버에 설치된 경우)를 제거합니다. 
    
    > [!NOTE]
    >  그런 다음 업그레이드 프로세스를 통해 캐시의 데이터가 유지 관리될 수 있도록 Redis를 설치한 후 유지 관리합니다.
  
2. 메시지가 표시될 때 위에 저장한 값을 포함하여 새 버전의 구성 요소를 설치합니다. 구성 요소 설치에 대한 자세한 내용은 통계 관리자 [배포를 참조하십시오.](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>자세한 내용
<a name="BKMK_Fixed"> </a>

자세한 내용은 다음 항목을 참조하세요.
  
- [비즈니스용 Skype 서버 통계 관리자에 대한 계획](plan.md)
    
- [비즈니스용 Skype 서버 통계 관리자 배포](deploy.md)
    
- [비즈니스용 Skype 서버 통계 관리자 문제 해결](troubleshoot.md)
