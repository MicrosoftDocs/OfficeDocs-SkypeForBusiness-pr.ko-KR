---
title: 클라우드 커넥터에서 단일 사이트 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Cloud Connector Edition에서 단일 PSTN 사이트 배포에 대해 자세히 알아보습니다.
ms.openlocfilehash: 52c10b8c5e386f72415ce5a379b68b0b469f825f5cf52be9b225f28dcf8232b6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298128"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>클라우드 커넥터에서 단일 사이트 배포
 
> [!Important]
> Cloud Connector Edition은 온라인과 함께 2021년 7월 31일 비즈니스용 Skype 있습니다. 조직에서 사용자 Teams 직접 라우팅을 사용하여 Teams 방법을 [확인합니다.](/MicrosoftTeams/direct-routing-landing-page)

Cloud Connector Edition에서 단일 PSTN 사이트 배포에 대해 자세히 알아보습니다.
  
HA(고가용성) 비즈니스용 Skype 클라우드 커넥터 버전 없는 경우 배포할 수 있습니다. HA를 사용하도록 설정하려면 사이트 내에 두 개 이상의 어플라이언스를 배포해야 합니다. 기존 어플라이언스가 배포된 후 HA를 지원하기 위해 변환할 수도 있습니다.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>첫 번째 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스 배포

사이트에 첫 번째 어플라이언스를 배포하기 위해 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행하여 어플라이언스를 등록합니다.
  
```powershell
Register-CcAppliance
```

지침에 따라 테넌트 관리자 계정 이름과 암호를 제공합니다. 클라우드 커넥터 온라인 관리를 위해 만든 계정을 사용하세요. 또한 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공합니다. 
  
1.4.2 이전 버전에서는 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공합니다. 
  
릴리스 2.0 이상에서도 지침에 따라 외부 인증서 암호, CceService 암호 및 CABackupFile 암호를 제공합니다.
  
설치를 시작하기 위해 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행합니다.
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>기존 사이트에 어플라이언스 추가

사이트에 어플라이언스를 추가하여 기존 클라우드 커넥터 사이트를 확장하여 HA를 지원할 수 있습니다. 
  
1. Prepare your Cloud Connector appliance에 설명된 바와 같이 단계에 따라 클라우드 커넥터 [어플라이언스를 준비합니다.](prepare-your-cloud-connector-appliance.md) 일부 단계는 배포의 첫 번째 어플라이언스에만 필요합니다. 사이트 디렉터리가 있으며 HA 지원에 맞게 올바르게 구성되어 있는지 확인합니다.
    
2. 새로 추가한 호스트 서버에서만 다음 cmdlet을 실행하여 조직 구성 또는 Microsoft 365 토폴로지 Office 365 업데이트합니다. 여러 어플라이언스를 동시에 추가하려는 경우 새로 추가된 각 호스트 서버에서 하나씩 cmdlet을 실행합니다.
    
   ```powershell
   Register-CcAppliance
   ```

3. 각 호스트 서버에서 다음 cmdlet을 실행하여 기존 어플라이언스에서 토폴로지 업데이트 기존 어플라이언스에서만 cmdlet을 실행합니다.
    
   ```powershell
   Publish-CcAppliance
   ```

4. 새로 추가된 호스트 서버에서만 다음 cmdlet을 실행합니다. 기존 어플라이언스에서 이 cmdlet을 실행하지 마십시오. 여러 어플라이언스를 동시에 추가하려는 경우 새로 추가된 각 호스트 서버에서 cmdlet을 하나씩 실행합니다.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> 사이트 디렉터리가 로컬 폴더 경로로 설정된 경우 이 폴더에 대한 파일 공유를 정의하고 새 어플라이언스의 사이트 디렉터리에 대해 UNC 경로를 사용해야 합니다. 로컬 경로가 있는 첫 번째 어플라이언스 사이트 디렉터리를 그대로 두거나 공유의 UNC 경로를 동일한 폴더로 사용하기 위해 이를 수정할 수 있습니다. 공유 사이트 디렉터리의 위치가 변경되면 이전에 설치된 모든 어플라이언스를 제거한 다음 다시 설치해야 합니다. > 중요: 어플라이언스가 사이트 디렉터리 공유 및 사이트 디렉터리의 암호화된 CA 백업 파일에 액세스할 수 있도록 CceService 계정과 CABackupFile 계정의 암호는 사이트 내에 배포된 모든 어플라이언스에서 동일해야 합니다. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>기존 사이트에서 어플라이언스 제거

기존 사이트에서 어플라이언스를 제거하려면
  
1. 사이트에서 제거할 호스트 서버에서만 다음 cmdlet을 실행하여 조직 구성 또는 Microsoft 365 Office 365 토폴로지 정보를 업데이트합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. 다음 cmdlet은 어플라이언스의 모든 가상 컴퓨터를 제거할 호스트 서버에서만 실행합니다.
    
   ```powershell
   Uninstall-CcAppliance
   ```