---
title: 스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로비전
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 비즈니스용 Skype 서버 및 성능 도구를 성공적으로 실행할 수 있도록 2015년 토폴로지 변경 또는 프로비전을 제공합니다.
---

# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로비전
 
비즈니스용 Skype 서버 및 성능 도구를 성공적으로 실행할 수 있도록 2015년 토폴로지 변경 또는 프로비전을 제공합니다.
  
비즈니스용 Skype 서버 2015 배포에 대한 기존 설정 및 구성에 따라 환경을 일부 변경해야 할 수 있습니다. 다음은 이러한 변경 내용의 목록입니다.
  
1. Windows PowerShell 실행 정책을 무제한으로 설정 현재로 설정된 설정이 확실하지 않은 경우 비즈니스용 Skype 서버 관리 셸을 열고 다음 명령을 실행할 수 있습니다.
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Unrestricted 값이 반환되지 않는 경우 다음에 이 값을 실행해야 합니다.
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. 이러한 비즈니스용 Skype 서버 구성하려면 다음을 해야 합니다.
    
    - 컴퓨터 이름, 비즈니스용 Skype 서버, 사이트 이름 및 정책과 같은 2015 토폴로지에 익숙해지야 합니다.
    
    - 응답 그룹 헌트 그룹(예: SIP UR) 등 그룹에 만들어진 일부 사용자를 할당합니다.
    
3. 명령줄에서 스크립트를 실행하기 위해 다음을 사용할 수 있습니다.
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 일반적으로 이 패키지에서 스크립트를 실행한 후 결과 추적은 스크립트가 실행된 동일한 경로의 파일에 저장됩니다. 이름 형식도 있습니다$h \<scriptname\>$m$s.txt. 따라서 오후 12시 15분에 로그 파일을 ArchivingPolicy.ps1 로그 파일을 ArchivingPolicy121500.txt.
    
5. 서버 구성에 대한 이러한 예제를 제공한 경우 부하 테스트를 완료한 후 구성을 수정하고 복원 또는 롤백하는 것이 모두 사용자에 따라 다릅니다.
    

