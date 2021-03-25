---
title: 비즈니스용 Skype Online 조직 관리
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 비즈니스용 Windows PowerShell Get-CsTenant 및 Get-CsTenantLicensingConfiguration cmdlet을 사용하여 비즈니스용 Skype 온라인 테넌트에 대한 정보를 얻습니다.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113184"
---
# <a name="manage-skype-for-business-online-organizations"></a>비즈니스용 Skype Online 조직 관리
> [!NOTE]
> 최신 [Teams PowerShell 공개](https://www.powershellgallery.com/packages/MicrosoftTeams/) 미리 보기 릴리스는 비즈니스용 Skype Online 커넥터와 통합되어 Teams PowerShell 관리를 위한 단일 모듈을 제공합니다.

**Get-CsTenant** 및 **Get-CsTenantLicensingConfiguration** cmdlet을 사용하여 비즈니스용 Skype Online 테넌트에 대한 정보를 찾을 수 있습니다.
  
## <a name="manage-skype-for-business-online-tenants"></a>비즈니스용 Skype Online 테넌트 관리

비즈니스용 Skype Online 테넌트에 대한 정보를 반환하기 위해 추가 매개 변수 없이 [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet을 호출합니다.
  
```PowerShell
Get-CsTenant
```

테넌트 이름 및 ID만 반환하는 경우 이 명령을 사용 합니다.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) 및 [Set-CsTenantFederationConfiguration과](/powershell/module/skype/Set-CsTenantFederationConfiguration)같은 cmdlet을 실행하는 경우 _TenantID_ 매개 변수의 값이 필요합니다.
  
비즈니스용 Skype Online 관리 센터에서 지정된 테넌트에 대한 라이선스 정보를 사용할 수 있는지 여부에 대한 정보를 찾으하려면 [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet을 사용하세요.
  
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
