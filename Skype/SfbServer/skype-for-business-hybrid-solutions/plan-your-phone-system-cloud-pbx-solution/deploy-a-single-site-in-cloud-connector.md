---
title: 클라우드 커넥터에 단일 사이트 배포
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
description: 클라우드 커넥터 Edition에 단일 PSTN 사이트를 배포 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: cc508d21f9e39c215ce3c07403ab75e791e2414a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779354"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>클라우드 커넥터에 단일 사이트 배포
 
클라우드 커넥터 Edition에 단일 PSTN 사이트를 배포 하는 방법에 대해 알아봅니다.
  
HA (고가용성) 지원 여부에 관계 없이 비즈니스용 Skype 클라우드 Connector Edition을 배포할 수 있습니다. HA를 사용 하도록 설정 하려는 경우에는 사이트 내에 두 개 이상의 기기를 배포 해야 합니다. 배포 후에 HA를 지원 하도록 기존 기기를 변환할 수도 있습니다.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>첫 번째 비즈니스용 Skype 클라우드 Connector Edition 기기 배포

사이트의 첫 번째 기기를 배포 하려면 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행 하 여 기기를 등록 합니다.
  
```powershell
Register-CcAppliance
```

지침에 따라 테 넌 트 관리자 계정 이름 및 암호를 제공 합니다. 클라우드 커넥터 온라인 관리용으로 만든 계정을 사용 합니다. 또한 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공 합니다. 
  
또한 릴리스 1.4.2 이전 버전에서는 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공 하는 지침을 따릅니다. 
  
릴리스 2.0 이상에서는 외부 인증서 암호, CceService 암호 및 CABackupFile 암호를 제공 하는 지침을 따릅니다.
  
설치를 시작 하려면 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행 합니다.
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>기존 사이트에 기기 추가

사이트에 추가 기기를 추가 하 여 HA를 지원 하도록 기존 클라우드 커넥터 사이트를 확장할 수 있습니다. 
  
1. [클라우드 커넥터 기기 준비](prepare-your-cloud-connector-appliance.md)에 설명 된 대로 클라우드 커넥터 기기를 준비 하는 단계를 수행 합니다. 일부 단계는 배포의 첫 번째 기기에만 필요 합니다. 사이트 디렉터리가 있는지와 HA 지원에 맞게 올바르게 구성 되어 있는지 확인 합니다.
    
2. 새로 추가한 호스트 서버 에서만 다음 cmdlet을 실행 하 여 Office 365 조직 구성에서 토폴로지 정보를 업데이트 합니다. 동시에 여러 기기를 추가 하려는 경우 새로 추가 된 각 호스트 서버에 대해 cmdlet을 하나씩 실행 합니다.
    
   ```powershell
   Register-CcAppliance
   ```

3. 각 호스트 서버에서 다음 cmdlet을 실행 하 여 기존 기기의 토폴로지를 업데이트 합니다. 기존 기기에 대해서만 cmdlet을 실행 합니다.
    
   ```powershell
   Publish-CcAppliance
   ```

4. 새로 추가 된 호스트 서버 에서만 다음 cmdlet을 실행 합니다. 기존 기기에서이 cmdlet을 실행 하지 마십시오. 동시에 여러 기기를 추가 하려는 경우 새로 추가 된 각 호스트 서버에 대해 cmdlet을 하나씩 실행 합니다.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> 사이트 디렉터리가 로컬 폴더 경로로 설정 된 경우에는이 폴더에 대 한 파일 공유를 정의 하 고 새 기기의 사이트 디렉터리에 대해 UNC 경로를 사용 해야 합니다. 첫 번째 기기 사이트 디렉터리를 로컬 경로로 그대로 두거나 같은 폴더에 공유에 대 한 UNC 경로를 사용 하도록 수정할 수 있습니다. 공유 사이트 디렉터리의 위치가 변경 되 면 이전에 설치한 모든 기기를 제거한 후 다시 설치 해야 합니다. > 중요: 기기에서 사이트 디렉터리 공유 및 암호화 된 CA 백업 파일에 액세스할 수 있도록 사이트 내에 배포 된 모든 기기에서 CceService 계정 및 CABackupFile 계정에 대 한 암호를 동일 하 게 설정 해야 합니다. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>기존 사이트에서 기기 제거

기존 사이트에서 기기를 제거 하려면 다음을 수행 합니다.
  
1. 사이트에서 제거 하려는 호스트 서버 에서만 다음 cmdlet을 실행 하 여 Office 365 조직 구성에서 토폴로지 정보를 업데이트 합니다.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. 기기의 모든 가상 컴퓨터를 제거 하려는 호스트 서버 에서만 다음 cmdlet을 실행 합니다.
    
   ```powershell
   Uninstall-CcAppliance
   ```


