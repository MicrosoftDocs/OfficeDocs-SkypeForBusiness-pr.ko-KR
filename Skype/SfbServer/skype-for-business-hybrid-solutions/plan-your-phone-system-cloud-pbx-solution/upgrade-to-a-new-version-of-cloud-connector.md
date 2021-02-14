---
title: 클라우드 커넥터의 새 버전으로 업그레이드
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Cloud Connector Edition 배포를 업그레이드하는 방법을 설명합니다.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359294"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>클라우드 커넥터의 새 버전으로 업그레이드

> [!Important]
> Cloud Connector Edition은 2021년 7월 31일 비즈니스용 Skype Online과 함께 사용 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Cloud Connector Edition 배포를 업그레이드하는 방법을 설명합니다.
  
온라인 관리 테넌트 계정을 설정하고 자동 업데이트를 사용하도록 설정한 경우 자동 업데이트 시간 창 구성에 따라 비즈니스용 Skype 클라우드 커넥터 버전의 기존 배포가 자동으로 최신 버전으로 업그레이드됩니다. 수동 업그레이드를 수행할 수 있습니다. 
  
Cloud Connector Edition 버전 1.4.1 이상은 기본적으로 자동 업데이트를 실행합니다. 최신 버전(2.1)으로 수동으로 업그레이드하려면 이 [](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 항목의 부분에 있는 새 버전으로 단일 사이트 업그레이드를 참조하세요.
  
자동 업데이트를 사용하려면 클라우드 커넥터 서비스가 실행되고 있습니다. 다음 단계에서는 자동 업데이트 프로세스에 대해 설명합니다.
  
- 자동 업데이트 프로세스는 자동 업데이트에 대해 구성한 일정에 따라 실행됩니다.
    
- 운영 체제 업데이트 작업
    
  - 모든 클라우드 커넥터 VM에 대한 운영 체제 업데이트를 확인하고 다운로드합니다. 
    
  - 모든 클라우드 커넥터 VM을 하나씩 설치하고 업데이트하고 다시 시작합니다.
    
  - 클라우드 커넥터 VM을 다시 시작한 후 다른 다시 시작이 필요한지 확인해 봐야 합니다.
    
  - 클라우드 커넥터 VM이 성공적으로 패치된 후 클라우드 커넥터 호스트 컴퓨터의 프로세스를 반복합니다.
    
  - 클라우드 커넥터 호스트 시스템이 성공적으로 부팅된 후 미해결 운영 체제 업데이트 작업이 완료됩니다.
    
- 클라우드 커넥터 업데이트 작업
    
  - 다운로드 사이트에서 버전 파일을 다운로드하고 검사합니다.
    
  - 새 버전 .msi 파일을 다운로드합니다. 
    
  - 이전 msi 파일을 제거합니다. 새 msi 파일을 설치합니다.
    
  - 새 버전의 비즈니스용 Skype 비트를 다운로드합니다.
    
  - Register-CcAppliance를 호출하여 어플라이언스를 등록합니다.
    
  - 새 클라우드 커넥터 버전을 설치합니다.
    
  - 이전 어플라이언스를 드레인하고 네트워크 연결을 새 어플라이언스로 전환합니다.
    
> [!NOTE]
>  클라우드 커넥터가 새 빌드로 업데이트되는 경우 클라우드 커넥터 cmdlet이 업데이트되지 않을 수 있습니다. 예를 들어 자동 업데이트가 수행되는 동안 PowerShell 창이 열려 있는 경우 이 문제가 발생할 수 있습니다. 업데이트된 cmdlet을 로드하기 위해 클라우드 커넥터 어플라이언스에서 PowerShell을 닫은 후 > PowerShell을 다시 연 다음 > 다음 단계 중 하나를 수행하여 Import-Module CloudConnector -Force를 실행할 수 있습니다.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>단일 사이트를 새 버전으로 업그레이드
<a name="BKMK_Upgrade"> </a>

사이트에 업그레이드할 어플라이언스가 하나뿐인 경우 다음을 합니다.
  
1. 제어판 프로그램 프로그램 및 기능에서 기존 클라우드 커넥터 **\> 버전을 \> 제거합니다.**
    
2. 에서 새 버전의 CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 설치합니다.
    
3. 설치하는 버전의 CloudConnector.ini 파일이 있으며 환경에 필요한 모든 값을 업데이트해야 합니다. 이전 릴리스의 .ini 파일은 사용할 수 없습니다. 클라우드 커넥터를 업그레이드하는 경우 클라우드 커넥터 [](prepare-your-cloud-connector-appliance.md) 어플라이언스 준비 항목을 참조하고 SiteName 및 EnableReferSupport가 CloudConnector.ini 올바른 값으로 설정되어 있는지 확인하십시오.
    
4. 관리자 권한으로 PowerShell 콘솔을 시작하고 다음 cmdlet을 실행하여 현재 어플라이언스를 등록합니다.
    
   ```powershell
   Register-CcAppliance
   ```

5. 다음 cmdlet을 실행하여 최신 버전을 다운로드합니다.
    
   ```powershell
   Start-CcDownload
   ```

6. 다음 cmdlet을 실행하여 설치를 시작하십시오. 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. 다음 cmdlet을 실행하여 새 배포를 활성화하고 이전 버전을 해제합니다.
    
   ```powershell
   Switch-CcVersion
   ```

사이트에 어플라이언스가 두 개 이상 있는 경우 위의 단계에 따라 각 어플라이언스를 하나씩 업그레이드하세요.
  
도메인 관리자, 가상 컴퓨터 관리자, 안전 모드 관리자 및 테넌트 관리자 자격 증명을 업데이트하려면  _UpdateAllCredentials_ 매개 변수를 사용하여 cmdlet을 실행하여 모든 자격 증명을 다시 설정할 수 있습니다.
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

그런 다음 새 버전으로 업그레이드를 시작하면 새 자격 증명을 입력할 수 있도록 승격됩니다. 
  
테넌트 관리자 자격 증명만 다시 설정하려는 경우 다음 cmdlet을 실행합니다.
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>여러 사이트를 새 버전으로 업그레이드
<a name="BKMK_Upgrade"> </a>

배포의 각 사이트에 대해 한 번씩 한 사이트를 업그레이드하여 단일 사이트를 업그레이드하는 단계를 수행합니다. 각 사이트를 업그레이드한 후 [클라우드](validate-your-cloud-connector-deployment.md) 커넥터 배포를 확인하고 유효성을 검사합니다.
  

