---
title: 온라인 비즈니스용 Skype 관리
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Windows PowerShell 및 Get-CsTenant Get-CsTenantLicensingConfiguration cmdlet을 사용하여 비즈니스용 Skype 테넌트에 대한 정보를 얻을 수 있습니다.
ms.openlocfilehash: e45f1bdd2c14aea34e07183dde86031a8c503476
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623090"
---
# <a name="manage-skype-for-business-online-organizations"></a>온라인 비즈니스용 Skype 관리

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> 최신 Teams PowerShell 공개 미리 보기 릴리스는 비즈니스용 Skype 온라인 커넥터와 통합되어 단일 모듈을 제공하여 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) Teams 제공합니다.

Get-CsTenant 비즈니스용 Skype **Get-CsTenantLicensingConfiguration** cmdlet을 사용하여 온라인 테넌트에 대한 정보를 찾을 수 있습니다. 
  
## <a name="manage-skype-for-business-online-tenants"></a>온라인 비즈니스용 Skype 관리

온라인 테넌트에 대한 정보를 비즈니스용 Skype 추가 매개 변수 없이 [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet을 호출합니다.
  
```PowerShell
Get-CsTenant
```

테넌트 이름 및 ID만 반환하는 경우 이 명령을 사용 합니다.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) 및 [Set-CsTenantFederationConfiguration과](/powershell/module/skype/Set-CsTenantFederationConfiguration)같은 cmdlet을 실행하는 경우 _TenantID_ 매개 변수의 값이 필요합니다.
  
지정된 테넌트에 대한 라이선스 정보를 비즈니스용 Skype 온라인 관리 센터에서 사용할 수 있는지 여부를 확인하려면 [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet을 사용하세요.
  
## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
