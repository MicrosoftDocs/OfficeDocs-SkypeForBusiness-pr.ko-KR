---
title: 도메인에서 복제 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: '1 단계: 스키마 준비에서 수행한 도메인 준비의 복제를 확인 하려면 비즈니스용 Skype Server Management Shell Lync Server 관리 셸에서 cmdlet을 실행 해야 합니다. Windows PowerShell cmdlet을 실행 하려면 준비한 도메인의 구성원 인 컴퓨터 (도메인 관리자 그룹의 구성원)에 로그온 합니다. 이렇게 하려면 다음을 수행합니다.'
ms.openlocfilehash: 7a9b8e90ce3c7c65f5f4b3d160ca7379b3bf8910
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705420"
---
# <a name="verify-replication-in-the-domain"></a>도메인에서 복제 확인
 
**1 단계: 스키마 준비**에서 수행한 도메인 준비의 복제를 확인 하려면 비즈니스용 Skype Server Management Shell Lync Server 관리 셸에서 cmdlet을 실행 해야 합니다. Windows PowerShell cmdlet을 실행 하려면 준비한 도메인의 구성원 인 컴퓨터 (도메인 관리자 그룹의 구성원)에 로그온 합니다. 이렇게 하려면 다음을 수행합니다.
  
1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.
    
2. Windows PowerShell에서 다음을 입력 합니다.
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    예를 들면 다음과 같습니다.
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > GlobalSettingsDomainController 매개 변수를 통해 전역 설정이 저장되어 있는 위치를 나타낼 수 있습니다. 설정이 시스템 컨테이너에 저장 된 경우 (구성 컨테이너에 전역 설정이 마이그레이션되지 않은 업그레이드 배포의 경우), Active Directory 도메인 서비스 포리스트의 루트에 도메인 컨트롤러를 정의 합니다. 전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다. 이 매개 변수를 지정 하지 않으면 cmdlet이 구성 컨테이너에 저장 된 것으로 간주 하 고 Active Directory의 모든 도메인 컨트롤러를 참조 합니다. 
  
    Domain 매개 변수를 지정하지 않으면 값이 로컬 도메인으로 설정됩니다. 이 cmdlet은 도메인 준비가 성공적이면 **LC_DOMAIN_SETTINGS_STATE_READY** 값을 반환합니다.
    

