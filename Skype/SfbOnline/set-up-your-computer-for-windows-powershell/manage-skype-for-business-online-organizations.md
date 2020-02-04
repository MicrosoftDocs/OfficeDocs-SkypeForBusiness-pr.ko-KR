---
title: 비즈니스용 Skype Online 조 직 관리
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
description: Windows PowerShell 및 CsTenant 및 CsTenantLicensingConfiguration cmdlet을 사용 하 여 비즈니스용 Skype Online 테 넌 트에 대 한 정보를 가져옵니다.
ms.openlocfilehash: 3c4a8f72caca634b208de5cf4aa555b88518f4da
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706253"
---
# <a name="manage-skype-for-business-online-organizations"></a>비즈니스용 Skype Online 조 직 관리

**CsTenant** 및 **CsTenantLicensingConfiguration** cmdlet을 사용 하 여 비즈니스용 Skype Online 테 넌 트에 대 한 정보를 확인할 수 있습니다.
  
## <a name="manage-skype-for-business-online-tenants"></a>비즈니스용 Skype Online 테 넌 트 관리

비즈니스용 Skype Online 테 넌 트에 대 한 정보를 반환 하려면 [CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet에 추가 매개 변수 없이 호출 하세요.
  
```PowerShell
Get-CsTenant
```

테 넌 트 이름 및 ID만 반환 하려면이 명령을 사용 합니다.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

[Set-Csten앤틸리스 Publicprovider](https://go.microsoft.com/fwlink/p/?linkid=849602) 및 [set CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)와 같은 cmdlet을 실행 하는 경우 _TenantID_ 매개 변수의 값이 필요 합니다.
  
비즈니스용 Skype Online 관리 센터에서 지정 된 테 넌 트에 대 한 라이선스 정보를 사용할 수 있는지 여부에 대 한 정보를 찾으려면 [CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet을 사용 하세요.
  
## <a name="related-topics"></a>관련 주제
[Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md)

  
 
