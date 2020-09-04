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
description: 기존 비즈니스용 Skype 클라우드 Connector Edition 1.4.1 이상 배포의 구성을 수정 하려면이 항목의 단계를 수행 합니다.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359114"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>기존 클라우드 커넥터 배포의 구성 수정

> [!Important]
> 클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다. 조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.

기존 비즈니스용 Skype 클라우드 Connector Edition 1.4.1 이상 배포의 구성을 수정 하려면이 항목의 단계를 수행 합니다. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>단일 사이트의 구성 수정
<a name="BKMK_SIngleSite"> </a>

사이트에 기기가 하나뿐인 경우 기기를 배포한 후 구성 설정을 변경 하려는 경우에는 CloudConnector.ini 파일을 수정 하 고 배포를 다시 시작할 수 있습니다.
  
1. 다음 cmdlet를 실행 하 여 호스트 서버에서 기존 가상 컴퓨터를 모두 제거 합니다. 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 다음 cmdlet를 실행 하 여 기기 등록을 취소 합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 기기 디렉터리에서 CloudConnector.ini 파일을 업데이트 합니다.
    
4. 다음 cmdlet을 실행 하 여 구성을 업데이트 합니다. (이 단계는 버전 2, 이전 버전의 경우에만 적용 되며, 다음 단계로 건너뜁니다.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 다음 cmdlet를 실행 하 여 기기를 다시 등록 합니다.
    
   ```powershell
   Register-CcAppliance
   ```

6. 다음 cmdlet를 실행 하 여 비즈니스용 Skype 클라우드 Connector Edition을 설치 합니다.
    
   ```powershell
   Install-CcAppliance
   ```

사이트에 둘 이상의 기기가 있는 경우 다음 단계를 수행 하 고 CloudConnector.ini 파일을 수정한 다음 기기를 하나씩 다시 배포 해야 합니다.
  
1. 다음 cmdlet를 실행 하 여 현재 기기에 있는 기존 가상 컴퓨터를 모두 제거 합니다. 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 다음 cmdlet를 실행 하 여 기기 등록을 취소 합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 기기 디렉터리에서 CloudConnector.ini 파일을 업데이트 합니다.
    
4. 다음 cmdlet을 실행 하 여 구성을 업데이트 합니다. (이 단계는 버전 2, 이전 버전의 경우에만 적용 되며, 다음 단계로 건너뜁니다.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 다음 cmdlet를 실행 하 여 기기를 다시 등록 합니다.
    
   ```powershell
   Register-CcAppliance
   ```

6. 사이트의 다른 모든 기기에서 다음 cmdlet을 실행 하 여 최신 구성을 선택 합니다.
    
   ```powershell
   Publish-CcAppliance
   ```

7. 다음 cmdlet를 실행 하 여 현재 기기에 클라우드 커넥터를 다시 배포 합니다.
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>여러 사이트의 구성 수정
<a name="BKMK_MultipleSites"> </a>

배포의 여러 사이트에 대 한 구성을 수정 하려면 단일 사이트에 대 한 단계를 수행 하 고 한 번에 한 사이트를 업데이트 합니다.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>자동 업데이트를 사용 하도록 Microsoft 365 또는 Office 365 조직의 구성 수정
<a name="BKMK_MultipleSites"> </a>

운영 체제 자동 업데이트 및 Bits 자동 업데이트를 사용 하도록 설정 하려면 온라인 관리에 비즈니스용 Skype 테 넌 트 관리자 계정을 사용 하 고 다음과 같이 테 넌 트 원격 PowerShell을 사용 해야 합니다.
  
운영 체제 자동 업데이트 또는 Bits 자동 업데이트를 사용 하지 않도록 설정한 경우 호스트 및 가상 컴퓨터에서 중요 한 Windows 업데이트를 놓칠 수 있으며 클라우드 커넥터가 새 버전으로 자동으로 업그레이드 되지 않습니다. 자동 업데이트를 사용 하는 것이 좋습니다.
  
1. 사이트의 EnableAutoUpdate 업데이트 속성을 true (기본값)로 설정 해야 합니다. 다음 cmdlet을 실행 하 여 EnableAutoUpdate 업데이트가 true로 설정 되어 있는지 확인 합니다.
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 테 넌 트에 대 한 자동 업데이트 시간 창을 만듭니다.
    
    기간은 매일, 매주 및 매월 일 수 있습니다. 모든 기간에 시작 시간과 기간이 필요 합니다.
    
   - 일 단위 기간에는 시작 시간 및 시간만 필요 합니다. 
    
   - 주간 기간에 대해 요일이 1 일 또는 여러 일인 작업일이 필요 합니다.
    
   - 월별 시간대에는 두 가지 유형이 있을 수 있습니다. 첫 번째 형식은 일을 지정 하는 것 이며 1 일이 될 수 있습니다. 두 번째 유형은 월의 주와 요일을 지정 하 고, 둘 다 단일 항목 또는 여러 항목 일 수 있습니다.
    
   - 각 테 넌 트에는 20 개의 windows 시간을 정의할 수 있습니다. 새 테 넌 트에 대 한 기본 시간대가 운영 체제 업데이트 및 Bits 업데이트를 위한 기본 시간 창으로 만들어집니다. 다음 cmdlet을 실행 하 여 일별, 주별 또는 월별 시간 기간을 설정 합니다.
    
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

   - 사이트에 업데이트 시간 창을 할당 합니다. 
    
     Bits 업데이트 시간 및 OS 업데이트 시간 창은 별도로 구성 됩니다. 두 사용자 모두에 게는 한 번 또는 여러 시간 창에 할당할 수 있습니다. 각 시간 창은 서로 다른 사이트에 할당 될 수 있으며 각 시간대에는 다른 용도가 있습니다 (Bits 업데이트 및 OS 업데이트). 다음 cmdlet를 실행 하 여 사이트에 대 한 시간 창을 설정 합니다. 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>전용 테 넌 트 관리자 자격 증명 업데이트
<a name="BKMK_MultipleSites"> </a>

클라우드 커넥터에 대 한 Microsoft 365 또는 Office 365 조 직의 관리 변경 내용은 필요한 권한을 가진 계정에서 만든 것입니다. 2.0 이전 클라우드 커넥터 버전에서 해당 계정은 전용 전역 테 넌 트 관리자 계정입니다. 클라우드 커넥터 버전 2.0 이상에서는 해당 계정이 비즈니스용 Skype 관리자 권한을 가진 Microsoft 365 또는 Office 365 계정일 수 있습니다.
  
Microsoft 365 또는 Office 365에서 관리자 계정 자격 증명이 변경 되는 경우 배포 된 각 클라우드 커넥터 기기에 대해 다음 관리자 PowerShell 명령을 실행 하 여 클라우드 커넥터에서 로컬로 캐싱된 자격 증명도 업데이트 해야 합니다.
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>호스트 서버에 대 한 암호 업데이트
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 이 섹션은 클라우드 커넥터 버전 2.0 이상에 적용할 수 있습니다. 
  
모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials." 파일에 저장 됩니다 \<CurrentUser\> . xml "입니다. 호스트 서버의 암호가 변경 되 면 로컬로 저장 된 자격 증명을 업데이트 해야 합니다.
  
클라우드 커넥터 기기에서 로컬로 저장 된 자격 증명을 업데이트 하려면 [Get-cccredential](get-cccredential.md) 및 [-cccredential](set-cccredential.md) cmdlet을 사용 하 고 다음 단계를 수행 합니다.
  
1. 나중에 필요한 암호를 검색 하려면 다음 명령을 실행 합니다. 
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. 호스트 서버에서 계정의 암호를 변경 합니다.
    
3. 호스트 서버를 다시 시작 합니다.
    
4. "%SystemDrive%\Programdata\Cloudconnector\credentials." 파일을 \<CurrentUser\> 삭제 합니다. xml "입니다.
    
5. PowerShell 콘솔을 관리자 권한으로 시작한 다음 "레지스터-CcAppliance-Local"을 실행 하 여 설명에 해당 하는 암호를 다시 입력 합니다. 클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 해야 합니다.
    
기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다. 1 단계에서 반환 된 DomainAdmin, VMAdmin 및 CceService 암호가 서로 다르면 다음 단계를 수행 해야 합니다.
  
1. Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.
    
1. 이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
2. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 DomainAdmin 암호의 암호를 입력 합니다.
    
2. 다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.
    
1. 이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
2. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 VmAdmin 암호의 암호를 입력 합니다. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>CceService 계정의 암호를 업데이트 합니다.
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 이 섹션은 클라우드 커넥터 버전 2.0.1 이상에 적용할 수 있습니다. 
  
클라우드 커넥터 서비스가 클라우드 커넥터 관리 서비스를 실행 합니다. CceService 계정은 클라우드 커넥터 에디션 배포 중에 만들어지고 "%SystemDrive%\Programdata\Cloudconnector\credentials. 파일에 저장 \<CurrentUser\> 됩니다. xml "및"% \Programdata\Cloudconnector\credentials..CceService.xml "
  
모든 기기가 사이트 디렉터리 공유에 액세스할 수 있도록 하려면 CceService 계정의 암호가 사이트 내에 배포 된 모든 기기에서 동일 해야 합니다. 다음 사항에 유의해야 합니다.
  
- 기본적으로 CceService 계정은 "암호 사용 기간 제한 없음"으로 구성 됩니다. 암호를 업데이트할 때이 구성을 유지 하는 것이 좋습니다.
    
- Bits 또는 Windows 업데이트에 대해 사용량이 많지 않은 기간 동안 및 자동 업데이트 시간 창 외부에서 암호를 업데이트 해야 합니다. 암호를 업데이트할 때 기기를 다시 시작 하 고 약간의 시간을 소요 해야 합니다. 기기를 다시 시작 하면 자동 업데이트 작업이 중단 됩니다. 
    
- CceService 계정 암호를 변경 하는 경우 모든 자격 증명을 지정 하 고 로컬로 저장 된 파일에 업데이트 해야 합니다. 
    
동일한 PSTN 사이트에 속하는 각 기기에 대해 다음을 지정 해야 합니다. 
  
1. 나중에 사용할 계정 이름 및 암호를 검색 하려면 다음 명령을 실행 합니다.
    
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

2. Enter-CcUpdate cmdlet을 실행 하 여 기기를 드레이닝 하 고 수동 유지 관리 모드로 이동 합니다.
    
3. 호스트 서버에서 CceService 계정의 암호를 업데이트 합니다.
    
4. 호스트 서버를 다시 시작 합니다.
    
5. 복원-CcCredentials cmdlet을 실행 하 여 설명 다음에 암호를 다시 입력 합니다. 
    
    CceService 계정을 제외 하 고 클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 해야 합니다. CceService 계정에 대해 새 암호를 입력 합니다. CceService 계정의 새 암호가 PSTN 사이트의 모든 기기에서 동일 해야 합니다.
    
6. 기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다. 1 단계에서 반환 된 DomainAdmin, VMAdmin 및 CceService 암호가 서로 다르면 다음 단계를 수행 해야 합니다.
    
7. Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.
    
   - 이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
   - 새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 DomainAdmin 암호의 암호를 입력 합니다.
    
8. 다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.
    
   - 이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
   - 새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 VmAdmin 암호의 암호를 입력 합니다. 
    
9. 수동 유지 관리 모드에서 기기를 이동 하려면 엑시트-CcUpdate cmdlet을 실행 합니다.
    
10. 동일한 PSTN 사이트의 모든 기기에서 이러한 단계를 완료 한 후에는 사이트 루트 디렉터리에서 다음 파일을 삭제 합니다.
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>새 SIP 도메인 추가
<a name="BKMK_UpdatePassword"> </a>

새 SIP 도메인 (또는 여러 SIP 도메인)을 기존 클라우드 커넥터 배포에 추가 하려면 다음을 수행 합니다.
  
1. Microsoft 365 또는 Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다. Microsoft 365 또는 Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [microsoft 365 또는 office 365에 도메인 추가](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조 하세요.
    
2. 새 SIP 도메인 또는 도메인을 사용 하 여 클라우드 커넥터 구성 파일을 업데이트 합니다.
    
3. 클라우드 커넥터 구성에 정의 된 각 SIP 도메인에 대해 추가 SAN 이름을 사용 하 여 새에 지 외부 인증서를 요청 합니다. 
    
4. 새에 지 외부 인증서의 경로를 다음과 같이 설정 합니다.
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    지침에 따라 [단일 사이트의 구성을 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 하거나 [여러 사이트의 구성을 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)합니다.
    
## <a name="modify-the-primary-sip-domain"></a>기본 SIP 도메인 수정
<a name="BKMK_UpdatePassword"> </a>

클라우드 커넥터 배포에서 기본 SIP 도메인을 변경 해야 하는 경우 다음을 수행 합니다.
  
1. Microsoft 365 또는 Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다. Microsoft 365 또는 Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [microsoft 365 또는 office 365에 도메인 추가](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조 하세요.
    
2. 새 SIP 도메인을 사용 하 여 클라우드 커넥터 구성 파일을 업데이트 합니다.
    
3. 클라우드 커넥터 구성에 정의 된 각 SIP 도메인에 대해 추가 SAN 이름을 사용 하 여 새에 지 외부 인증서를 요청 합니다. 
    
4. 새에 지 외부 인증서의 경로를 다음과 같이 설정 합니다.
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 사이트의 각 기기에 대 한 테 넌 트 등록을 제거 합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행 하 여 각 사이트에 대 한 사이트 등록을 제거 합니다.
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 제거 합니다.
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 등록 합니다.
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 하나씩 설치 합니다.
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>외부에 지 인증서를 새 인증서로 바꾸기
<a name="BKMK_UpdatePassword"> </a>

클라우드 커넥터 기기에서 외부에 지 인증서를 교체 해야 하는 경우에는 새에 지 인증서를 획득 하 고, 개인 키 및 전체 인증서 체인이 포함 된 PFX 파일을 준비 하 고, 각 기기에서 다음을 수행 해야 합니다.
  
1. Enter-CcUpdate cmdlet을 사용 하 여 기기를 유지 관리 모드로 전환 합니다.
    
2. 다음 명령을 실행합니다. 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    새 인증서의 암호가 이전 암호와 동일 하면 가져오기가 정상적으로 수행 됩니다. 암호가 다르면 암호가 잘못 되었다는 오류가 표시 되며,-Local 매개 변수를 사용 하 여 Register-CcAppliance cmdlet을 실행 하 고 2 단계를 반복 하 여 암호를 다시 설정 해야 합니다. 
    
4. Exit-CcUpdate cmdlet을 사용 하 여 기기를 유지 관리 모드에서 제외 합니다.
    

