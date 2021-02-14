---
title: 기존 클라우드 커넥터 배포의 구성 수정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 이 항목의 단계에 따라 기존 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1 이상 배포의 구성을 수정합니다.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359114"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>기존 클라우드 커넥터 배포의 구성 수정

> [!Important]
> Cloud Connector Edition은 2021년 7월 31일 비즈니스용 Skype Online과 함께 사용 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

이 항목의 단계에 따라 기존 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1 이상 배포의 구성을 수정합니다. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>단일 사이트의 구성 수정
<a name="BKMK_SIngleSite"> </a>

사이트에 어플라이언스가 하나뿐인 경우 어플라이언스가 배포된 후 구성 설정을 변경하려는 경우 CloudConnector.ini 파일을 수정하고 배포를 다시 시작할 수 있습니다.
  
1. 다음 cmdlet을 실행하여 호스트 서버에서 모든 기존 가상 컴퓨터를 제거합니다. 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 다음 cmdlet을 실행하여 어플라이언스 등록을 해지합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Appliance 디렉터리에서 CloudConnector.ini 파일을 업데이트합니다.
    
4. 다음 cmdlet을 실행하여 구성을 업데이트합니다. (이 단계는 버전 2에만 적용되고 이전 버전에서는 다음 단계로 건너뜁습니다.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 다음 cmdlet을 실행하여 어플라이언스를 다시 등록합니다.
    
   ```powershell
   Register-CcAppliance
   ```

6. 다음 cmdlet을 실행하여 비즈니스용 Skype 클라우드 커넥터 Edition을 설치합니다.
    
   ```powershell
   Install-CcAppliance
   ```

사이트에 어플라이언스가 두 개 이상 있는 경우 다음 단계를 수행하여 CloudConnector.ini 파일을 수정한 다음 어플라이언스를 하나씩 다시 배포해야 합니다.
  
1. 다음 cmdlet을 실행하여 현재 어플라이언스에 있는 모든 기존 가상 컴퓨터를 제거합니다. 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 다음 cmdlet을 실행하여 어플라이언스 등록을 해지합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Appliance 디렉터리에서 CloudConnector.ini 파일을 업데이트합니다.
    
4. 다음 cmdlet을 실행하여 구성을 업데이트합니다. (이 단계는 버전 2에만 적용되고 이전 버전에서는 다음 단계로 건너뜁습니다.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 다음 cmdlet을 실행하여 어플라이언스를 다시 등록합니다.
    
   ```powershell
   Register-CcAppliance
   ```

6. 사이트의 다른 모든 어플라이언스에서 다음 cmdlet을 실행하여 최신 구성을 선택하십시오.
    
   ```powershell
   Publish-CcAppliance
   ```

7. 다음 cmdlet을 실행하여 현재 어플라이언스에서 클라우드 커넥터를 다시Eploy합니다.
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>여러 사이트의 구성 수정
<a name="BKMK_MultipleSites"> </a>

배포에서 여러 사이트에 대한 구성을 수정하려면 단일 사이트에 대한 단계를 수행하여 한 사이트에서 한 사이트씩 업데이트합니다.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>자동 업데이트를 사용하도록 Microsoft 365 또는 Office 365 조직의 구성 수정
<a name="BKMK_MultipleSites"> </a>

운영 체제 자동 업데이트 및 비트 자동 업데이트를 사용하려면 온라인 관리를 위해 비즈니스용 Skype 테넌트 관리자 계정을 사용하고 다음과 같이 테넌트 원격 PowerShell을 사용해야 합니다.
  
운영 체제 자동 업데이트 또는 비트 자동 업데이트를 사용하지 않도록 설정한 경우 호스트 및 가상 컴퓨터는 중요한 Windows 업데이트를 놓칠 수 있으며 클라우드 커넥터가 새 버전으로 자동으로 업그레이드되지 않습니다. 자동 업데이트를 사용하도록 설정하는 것이 좋습니다.
  
1. 사이트의 EnableAutoUpdate 속성을 true(기본값)로 설정해야 합니다. EnableAutoUpdate가 true로 설정되어 있는지 확인하려면 다음 cmdlet을 실행합니다.
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 테넌트에 대한 자동 업데이트 시간 창을 만드십시오.
    
    시간 창은 일, 주 및 월간일 수 있습니다. 모든 시간 창에 시작 시간 및 기간이 필요합니다.
    
   - 일별 기간의 경우 시작 시간 및 기간만 필요합니다. 
    
   - 주간 시간 창의 경우 하루 또는 여러 일일 수 있는 주 중 일 수가 필요합니다.
    
   - 월별 기간의 경우 두 가지 유형이 있을 수 있습니다. 첫 번째 형식은 하루가 될 수 있는 월의 날짜를 지정하는 것입니다. 두 번째 유형은 단일 항목 또는 여러 항목이 될 수 있는 주와 함께 주를 지정하는 것입니다.
    
   - 각 테넌트에는 20시간의 기간이 정의될 수 있습니다. 운영 체제 업데이트 및 비트 업데이트의 기본 기간으로 새 테넌트에 대한 기본 시간 창이 만들어집니다. 다음 cmdlet을 실행하여 일, 주 또는 월별 시간 창을 설정할 수 있습니다.
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - 사이트에 업데이트 시간 창을 할당합니다. 
    
     비트 업데이트 시간 및 OS 업데이트 시간 창은 별도로 구성됩니다. 둘 다 한 번 또는 여러 번 창을 할당할 수 있습니다. 각 기간을 다른 사이트 및 용도(비트 업데이트 및 OS 업데이트)에 할당할 수 있습니다. 다음 cmdlet을 실행하여 사이트의 시간 창을 설정할 수 있습니다. 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>전용 테넌트 관리자 자격 증명 업데이트
<a name="BKMK_MultipleSites"> </a>

클라우드 커넥터에 대한 Microsoft 365 또는 Office 365 조직의 관리 변경 사항은 필요한 권한이 있는 계정에서 변경됩니다. 2.0 이전의 클라우드 커넥터 버전에서 해당 계정은 전용 전역 테넌트 관리자 계정입니다. 클라우드 커넥터 버전 2.0 이상에서 해당 계정은 비즈니스용 Skype 관리자 권한이 있는 Microsoft 365 또는 Office 365 계정일 수 있습니다.
  
Microsoft 365 또는 Office 365에서 관리자 계정 자격 증명이 변경되는 경우 배포한 각 클라우드 커넥터 어플라이언스에서 다음 관리자 PowerShell 명령을 실행하여 클라우드 커넥터에서 로컬로 캐시된 자격 증명을 업데이트해야 합니다.
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>호스트 서버의 암호 업데이트
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 이 섹션은 클라우드 커넥터 버전 2.0 이상에 적용할 수 있습니다. 
  
모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml". 호스트 서버의 암호가 변경되는 경우 로컬에 저장된 자격 증명을 업데이트해야 합니다.
  
클라우드 커넥터 어플라이언스에서 로컬로 저장된 자격 증명을 업데이트하기 위해 [Get-CcCredential](get-cccredential.md) 및 [Set-CcCredential](set-cccredential.md) cmdlet을 사용하여 다음 단계를 수행합니다.
  
1. 다음 명령을 실행하여 나중에 필요한 암호를 검색합니다. 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. 호스트 서버에서 계정의 암호를 변경합니다.
    
3. 호스트 서버를 다시 시작합니다.
    
4. 다음 파일을 삭제합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".
    
5. 관리자 권한으로 PowerShell 콘솔을 시작한 다음 "Register-CcAppliance -Local"을 실행하여 설명에 따라 암호를 다시 입력합니다. 클라우드 커넥터 배포 전에 입력한 암호와 동일한 암호를 입력해야 합니다.
    
기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다. 1단계에서 반환된 DomainAdmin, VMAdmin 및 CceService 암호가 다른 경우 다음 단계를 수행해야 합니다.
  
1. 다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.
    
1. 이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.
    
2. 새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 DomainAdmin 암호의 암호를 입력합니다.
    
2. 다음과 Set-CcCredential -AccountType VmAdmin을 실행합니다.
    
1. 이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.
    
2. 새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 VmAdmin 암호의 암호를 입력합니다. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>CceService 계정의 암호 업데이트
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 이 섹션은 클라우드 커넥터 버전 2.0.1 이상에 적용할 수 있습니다. 
  
클라우드 커넥터 서비스가 클라우드 커넥터 관리 서비스를 실행합니다. CceService 계정은 Cloud Connector Edition 배포 중에 만들어지며 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" 및 "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
모든 어플라이언스가 사이트 디렉터리 공유에 액세스할 수 있도록 CceService 계정의 암호는 사이트 내에 배포된 모든 어플라이언스에서 동일해야 합니다. 다음 사항에 유의해야 합니다.
  
- 기본적으로 CceService 계정은 "암호가 만료되지 않습니다."로 구성됩니다. 암호를 업데이트할 때 이 구성을 유지하는 것이 좋습니다.
    
- 사용량이 많은 기간에는 암호를 업데이트해야 합니다. 비트 또는 Windows 업데이트의 경우 자동 업데이트 기간을 밖으로 업데이트해야 합니다. 암호를 업데이트할 때 어플라이언스를 드레인했다가 다시 시작해야 합니다. 이 경우 시간이 오래 걸리게 됩니다. 어플라이언스를 다시 시작하면 자동 업데이트 작업이 중단됩니다. 
    
- CceService 계정 암호를 변경하는 경우 모든 자격 증명을 지정하고 로컬에 저장된 파일에서 업데이트해야 합니다. 
    
동일한 PSTN 사이트에 속하는 각 어플라이언스에 대해 다음을 지정해야 합니다. 
  
1. 다음 명령을 실행하여 나중에 사용할 계정 이름 및 암호를 검색합니다.
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. Enter-CcUpdate cmdlet을 실행하여 어플라이언스를 드레인하고 수동 유지 관리 모드로 전환합니다.
    
3. 호스트 서버에서 CceService 계정의 암호를 업데이트합니다.
    
4. 호스트 서버를 다시 시작합니다.
    
5. Restore-CcCredentials cmdlet을 실행하여 설명 다음에 암호를 다시 입력합니다. 
    
    CceService 계정을 제외하고 클라우드 커넥터 배포 전에 입력한 암호를 입력해야 합니다. CceService 계정의 경우 새 암호를 입력합니다. CceService 계정의 새 암호가 PSTN 사이트의 모든 어플라이언스에 대해 동일해야 합니다.
    
6. 기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다. 1단계에서 반환된 DomainAdmin, VMAdmin 및 CceService 암호가 다른 경우 다음 단계를 수행해야 합니다.
    
7. 다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.
    
   - 이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.
    
   - 새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 DomainAdmin 암호의 암호를 입력합니다.
    
8. 다음과 Set-CcCredential -AccountType VmAdmin을 실행합니다.
    
   - 이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.
    
   - 새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 VmAdmin 암호의 암호를 입력합니다. 
    
9. 이 Exit-CcUpdate cmdlet을 실행하여 수동 유지 관리 모드에서 어플라이언스를 이동합니다.
    
10. 동일한 PSTN 사이트의 모든 어플라이언스에서 이러한 단계를 완료한 후 사이트 루트 디렉터리에서 다음 파일을 삭제합니다.
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>새 SIP 도메인 추가
<a name="BKMK_UpdatePassword"> </a>

기존 클라우드 커넥터 배포에 새 SIP 도메인(또는 여러 SIP 도메인)을 추가하려면 다음을 실행합니다.
  
1. Microsoft 365 또는 Office 365에서 도메인을 업데이트하는 단계를 완료하고 DNS 레코드를 추가할 수 있는지 확인 합니다. Microsoft 365 또는 Office 365에서 도메인을 설정하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)도메인 추가를 참조하세요.
    
2. 클라우드 커넥터 구성 파일을 새 SIP 도메인 또는 도메인으로 업데이트합니다.
    
3. 클라우드 커넥터 구성에 정의된 각 SIP 도메인에 대해 sip.domain에 대한 추가 SAN 이름을 사용하여 새 에지 외부 인증서를 요청합니다. 
    
4. 새 에지 외부 인증서의 경로를 다음과 같이 설정하십시오.
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    지침에 따라 단일 사이트의 구성을 [수정하거나](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 여러 사이트의 [구성을 수정합니다.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>기본 SIP 도메인 수정
<a name="BKMK_UpdatePassword"> </a>

클라우드 커넥터 배포에서 기본 SIP 도메인을 변경해야 하는 경우 다음을 실행합니다.
  
1. Microsoft 365 또는 Office 365에서 도메인을 업데이트하는 단계를 완료하고 DNS 레코드를 추가할 수 있는지 확인 합니다. Microsoft 365 또는 Office 365에서 도메인을 설정하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)도메인 추가를 참조하세요.
    
2. 클라우드 커넥터 구성 파일을 새 SIP 도메인으로 업데이트합니다.
    
3. 클라우드 커넥터 구성에 정의된 각 SIP 도메인에 대해 sip.domain에 대한 추가 SAN 이름을 사용하여 새 에지 외부 인증서를 요청합니다. 
    
4. 새 에지 외부 인증서의 경로를 다음과 같이 설정하십시오.
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 사이트의 각 어플라이언스에 대한 테넌트 등록을 제거합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행하여 각 사이트에 대한 사이트 등록을 제거합니다.
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 각 어플라이언스를 제거합니다.
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 각 어플라이언스를 등록합니다.
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 각 어플라이언스를 하나씩 설치합니다.
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>외부 에지 인증서를 새 인증서로 바꾸기
<a name="BKMK_UpdatePassword"> </a>

클라우드 커넥터 어플라이언스에서 외부 에지 인증서를 교체해야 하는 경우 새 에지 인증서를 얻어 개인 키 및 전체 인증서 체인이 포함된 PFX 파일을 준비한 다음 각 어플라이언스에서 다음을 실행해야 합니다.
  
1. 이 cmdlet을 사용하여 어플라이언스를 유지 관리 Enter-CcUpdate 합니다.
    
2. 다음 명령을 실행합니다. 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    새 인증서의 암호가 이전 인증서와 같을 경우 가져오기에 성공합니다. 암호가 다른 경우 암호가 잘못했다는 오류가 표시되고 -Local 매개 변수를 사용하여 Register-CcAppliance cmdlet을 실행한 다음 2단계를 반복하여 암호를 다시 설정해야 합니다. 
    
4. Exit -CcUpdate cmdlet을 사용하여 어플라이언스를 유지 관리 모드에서 퇴장합니다.
    

