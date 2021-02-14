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
description: 비즈니스 Windows PowerShell 및 Get-CsTenant Get-CsTenantLicensingConfiguration cmdlet을 사용하여 비즈니스용 Skype Online 테넌트에 대한 정보를 얻을 수 있습니다.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085694"
---
# <a name="manage-skype-for-business-online-organizations"></a>비즈니스용 Skype Online 조직 관리
> [!NOTE]
> 최신 [Teams PowerShell 공개](https://www.powershellgallery.com/packages/MicrosoftTeams/) 미리 보기 릴리스는 비즈니스용 Skype Online Connector와 통합되어 Teams PowerShell 관리를 위한 단일 모듈을 제공합니다.

Get-CsTenant 및 **Get-CsTenantLicensingConfiguration** cmdlet을 사용하여 비즈니스용 Skype Online 테넌트에 대한 정보를 찾을 수 있습니다. 
  
## <a name="manage-skype-for-business-online-tenants"></a>비즈니스용 Skype Online 테넌트 관리

비즈니스용 Skype Online 테넌트에 대한 정보를 반환하기 위해 추가 매개 변수 없이 [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet을 호출합니다.
  
```PowerShell
Get-CsTenant
```

테넌트 이름 및 ID만 반환하기 위해 이 명령을 사용 합니다.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

[Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) 및 [Set-CsTenantFederationConfiguration과](https://technet.microsoft.com/library/jj994080.aspx)같은 cmdlet을 실행하는 경우 _TenantID_ 매개 변수의 값이 필요합니다.
  
비즈니스용 Skype Online 관리 센터에서 지정된 테넌트에 대한 라이선스 정보를 사용할 수 있는지 여부에 대한 정보를 확인하려면 [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet을 사용하세요.
  
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 관리를 위한 컴퓨터를 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
