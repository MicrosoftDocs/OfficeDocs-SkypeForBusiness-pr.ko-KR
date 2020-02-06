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
description: 클라우드 커넥터 에디션 배포를 업그레이드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d2f9d2a2720f67a2110ba97b7d100e5673a0015c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814146"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>클라우드 커넥터의 새 버전으로 업그레이드
 
클라우드 커넥터 에디션 배포를 업그레이드 하는 방법에 대해 알아봅니다.
  
온라인 관리 테 넌 트 계정을 설정 하 고 자동 업데이트를 사용 하는 경우 자동 업데이트 시간 창에 따라 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 기존 배포가 자동으로 최신 버전으로 업그레이드 됩니다. 구성. 수동 업그레이드를 수행할 수도 있습니다. 
  
Cloud Connector Edition 버전 1.4.1 이상에서는 기본적으로 자동 업데이트를 수행 합니다. 최신 버전 (2.1)으로 수동으로 업그레이드 하려는 경우이 항목의 뒷부분에 나오는 [단일 사이트를 새 버전으로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 를 참조 하세요.
  
자동 업데이트를 사용 하려면 클라우드 커넥터 서비스가 실행 중 이어야 합니다. 다음 단계에서는 자동 업데이트에 대 한 프로세스를 설명 합니다.
  
- 자동 업데이트 프로세스는 자동 업데이트를 위해 구성한 일정에 따라 실행 됩니다.
    
- 운영 체제 업데이트 작업
    
  - 모든 클라우드 커넥터 Vm에 대 한 운영 체제 업데이트를 확인 하 고 다운로드 합니다. 
    
  - 모든 클라우드 커넥터 Vm을 하나씩 설치 하 고 업데이트 한 후 다시 시작 합니다.
    
  - 클라우드 커넥터 Vm을 다시 시작한 후에 다른 다시 시작이 필요한 지 확인 합니다.
    
  - 클라우드 커넥터 Vm이 성공적으로 패치 된 후 클라우드 커넥터 호스트 컴퓨터에 대 한 프로세스를 반복 합니다.
    
  - 클라우드 커넥터 호스트 컴퓨터를 성공적으로 부팅 한 후에는 처리 중인 운영 체제 업데이트 작업이 완료 됩니다.
    
- 클라우드 커넥터 업데이트 작업
    
  - 다운로드 사이트에서 버전 파일을 다운로드 하 여 확인 합니다.
    
  - 새 버전의 .msi 파일을 다운로드 합니다. 
    
  - 이전 msi 파일을 제거 합니다. 새 msi 파일을 설치 합니다.
    
  - 새 버전의 비즈니스용 Skype 비트를 다운로드 하세요.
    
  - 등록-CcAppliance를 호출 하 여 기기를 등록 합니다.
    
  - 새 클라우드 커넥터 버전을 설치 합니다.
    
  - 이전 기기를 방전 하 고 새 기기로 네트워크 연결을 전환 합니다.
    
> [!NOTE]
>  클라우드 커넥터가 새 빌드로 업데이트 되 면 클라우드 커넥터 cmdlet이 업데이트 되지 않았을 수 있습니다. 예를 들어 자동 업데이트가 발생 하는 동안 PowerShell 창이 열려 있는 경우이 문제가 발생할 수 있습니다. 업데이트 된 cmdlet을 로드 하려면 다음 단계 중 하나를 수행 합니다. 클라우드 커넥터 기기에서 PowerShell을 > 다음 PowerShell을 다시 엽니다. > 또는 가져오기-모듈 CloudConnector-Force를 실행할 수 있습니다.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>단일 사이트를 새 버전으로 업그레이드
<a name="BKMK_Upgrade"> </a>

업그레이드 하려는 사이트에 하나의 기기만 있는 경우 다음을 수행 합니다.
  
1. **제어판 \> 프로그램 \> 의 프로그램 및 기능**에서 기존 클라우드 커넥터 버전을 제거 합니다.
    
2. 에서 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)새 버전의 cloudconnector의 msi를 설치 합니다.
    
3. 설치 하려는 버전에 대 한 CloudConnector .ini 파일이 있고 환경에 필요한 모든 값을 업데이트 했는지 확인 합니다. 이전 릴리스에서는 .ini 파일을 사용할 수 없습니다. 클라우드 커넥터를 업그레이드 하는 경우 [클라우드 커넥터 기기 준비](prepare-your-cloud-connector-appliance.md) 항목을 참조 하 고 다음을 사용 하 여 SiteName 및 EnableReferSupport가 cloudconnector .ini 파일에서 올바른 값으로 설정 되어 있는지 확인 하세요.
    
4. PowerShell 콘솔을 관리자로 시작 하 고 다음 cmdlet을 실행 하 여 현재 기기를 등록 합니다.
    
   ```powershell
   Register-CcAppliance
   ```

5. 다음 cmdlet을 실행 하 여 최신 버전을 다운로드 합니다.
    
   ```powershell
   Start-CcDownload
   ```

6. 다음 cmdlet을 실행 하 여 설치를 시작 합니다. 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. 다음 cmdlet을 실행 하 여 새 배포를 활성화 하 고 이전 버전을 해제 합니다.
    
   ```powershell
   Switch-CcVersion
   ```

사이트에 둘 이상의 기기가 있는 경우 앞의 단계를 따라 각 기기를 하나씩 업그레이드 하세요.
  
도메인 관리자, 가상 컴퓨터 관리자, 안전 모드 관리자 및 테 넌 트 관리자 자격 증명을 업데이트 하려는 경우 _Updateallcredentials_ 매개 변수를 사용 하 여 cmdlet을 실행 하 여 모든 자격 증명을 다시 설정할 수 있습니다.
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

그런 다음 새 버전으로 업그레이드 하기 시작 하면 새 자격 증명을 입력 하도록 승격 됩니다. 
  
테 넌 트 관리자 자격 증명만을 다시 설정 하려는 경우 다음 cmdlet을 실행 합니다.
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>여러 사이트를 새 버전으로 업그레이드
<a name="BKMK_Upgrade"> </a>

배포의 각 사이트에 대해 한 번에 한 사이트를 업그레이드 하 여 단일 사이트를 업그레이드 하는 단계를 따릅니다. 각 사이트를 업그레이드 한 후 [클라우드 커넥터 배포를 확인 하 고 유효성을 검사](validate-your-cloud-connector-deployment.md) 합니다.
  

