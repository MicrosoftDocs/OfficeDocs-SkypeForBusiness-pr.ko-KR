---
title: 도메인에서 복제 확인
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: '1단계: Lync Server 관리 셸에서 수행한 도메인 준비 복제를 확인하려면 비즈니스용 Skype 서버 관리 셸에서 cmdlet을 실행해야 합니다. Windows PowerShell cmdlet를 실행하려면 준비한 도메인의 구성원인 컴퓨터에 Domain Admins 그룹의 구성원으로 로그온합니다. 다음을 수행합니다.'
ms.openlocfilehash: e3c4a1d234427c43a9b0de298591b08f8a8194df
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591822"
---
# <a name="verify-replication-in-the-domain"></a>도메인에서 복제 확인
 
**1단계:** Lync Server 관리 셸에서 수행한 도메인 준비 복제를 확인하려면 비즈니스용 Skype 서버 관리 셸에서 cmdlet을 실행해야 합니다. Windows PowerShell cmdlet를 실행하려면 준비한 도메인의 구성원인 컴퓨터에 Domain Admins 그룹의 구성원으로 로그온합니다. 다음을 수행합니다.
  
1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype 를 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 다음 Windows PowerShell 입력합니다.
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    예를 들면 다음과 같습니다.
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > GlobalSettingsDomainController 매개 변수를 통해 전역 설정이 저장되어 있는 위치를 나타낼 수 있습니다. 설정이 시스템 컨테이너에 저장되어 있는 경우(전역 설정이 구성 컨테이너로 마이그레이션되지 않은 업그레이드 배포의 경우 일반적) Active Directory 도메인 서비스 포리스트의 루트에서 도메인 컨트롤러를 정의합니다. 전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다. 이 매개 변수를 지정하지 않으면 이 cmdlet은 설정이 구성 컨테이너에 저장되고 Active Directory의 도메인 컨트롤러를 참조하는 것으로 가정합니다. 
  
    Domain 매개 변수를 지정하지 않으면 값이 로컬 도메인으로 설정됩니다. 이 cmdlet는 도메인 준비가 성공적이면 **LC_DOMAIN_SETTINGS_STATE_READY** 값을 반환합니다.
    

