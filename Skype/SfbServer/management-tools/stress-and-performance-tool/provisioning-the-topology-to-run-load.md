---
title: 스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로 비전
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 사용자가 스트레스 및 성능 도구를 성공적으로 실행할 수 있도록 비즈니스용 Skype 서버 2015 토폴로지를 변경 하거나 프로 비전 합니다.
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816167"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로 비전
 
사용자가 스트레스 및 성능 도구를 성공적으로 실행할 수 있도록 비즈니스용 Skype 서버 2015 토폴로지를 변경 하거나 프로 비전 합니다.
  
비즈니스용 Skype Server 2015 배포에 대 한 기존 설정 및 구성에 따라 환경에서 몇 가지 변경 작업을 수행 해야 할 수 있습니다. 다음은 이러한 변경의 목록입니다.
  
1. Windows PowerShell 실행 정책을 무제한으로 설정 합니다. 현재 설정 되어 있는지 확실 하지 않은 경우 비즈니스용 Skype Server Management Shell을 열고 다음 명령을 실행할 수 있습니다.
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   무제한 값이 반환 되지 않는 경우 다음을 실행 해야 합니다.
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. 비즈니스용 Skype 서버를 효과적으로 구성 하려면 다음이 필요 합니다.
    
    - 비즈니스용 Skype 서버 2015 토폴로지 (컴퓨터 이름, 서비스 인스턴스, 사이트 이름, 정책 등)에 대해 잘 알고 있어야 합니다.
    
    - 응답 그룹 헌트 그룹과 같은 그룹에 만든 일부 사용자 (예: SIP Uri)를 할당 합니다.
    
3. 명령줄에서 스크립트를 실행 하려면 다음을 사용할 수 있습니다.
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 일반적으로이 패키지에서 스크립트를 실행 하면 결과 추적은 스크립트가 실행 된 위치와 같은 경로에 있는 파일에 저장 됩니다. \<Scriptname\>$h $ m $ s .txt와 같은 이름 지정 형식으로도 지정할 수도 있습니다. 따라서 12:15 PM에서 ArchivingPolicy를 실행 하면 ArchivingPolicy121500 라는 로그 파일이 표시 됩니다.
    
5. 서버 구성에 대해 이러한 예제를 제공 했지만 부하 테스트 실행을 완료 한 후에는 구성을 수정 하 고 복원 하거나 롤백해야 합니다.
    

