---
title: 2013에서 기존 보관 정책을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '요약: 사용자 보관 정책에 대한 사용자 보관 정책을 변경하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 494ed5ab3bd9e7bf4b64926533d3866e515fe34a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416621"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>2013에서 기존 보관 정책을 비즈니스용 Skype 서버
 
**요약:** 사용자 보관 정책에 대한 사용자 보관 정책을 변경하는 비즈니스용 Skype 서버.
  
사용자 비즈니스용 Skype 서버 배포할 때 배포의 사용자에 대해 보관이 구현되는 방법을 결정하는 초기 보관 정책을 설정할 수 있습니다. 이 항목에서는 정책을 관리하고 수정하는 방법에 대해 설명합니다. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>제어판을 사용하여 보관 정책 변경

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
4. 정책 목록에서 다음 중 하나를 수행합니다. 
    
   - 전체 배포에 대한 정책을 변경하려면 정책 목록에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.
    
   - 단일 사이트에 대한 정책을 변경하려면 정책 목록에서 사이트 이름을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.
    
   - 단일 사용자 또는 사용자 그룹에 대한 정책을 변경하려면 정책 목록에서 사용자 또는 사용자 그룹 이름을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.
    
5. **보관 정책 편집** 페이지에서 다음을 수행합니다.
    
   - 정책에 내부 보관을 사용하거나 사용하지 않도록 설정하려면 **내부 통신 보관** 확인란을 선택하거나 선택 취소합니다.
    
   - 정책에 외부 보관을 사용하거나 사용하지 않도록 설정하려면 **외부 통신 보관** 확인란을 선택하거나 선택 취소합니다.
    
6. **커밋** 을 클릭합니다.
    
    > [!IMPORTANT]
    > 사용자 정책 설정은 관리자가 정책을 적용한 특정 사용자 및 사용자 그룹에만 적용됩니다. 자세한 내용은 [Apply an archiving policy to users in 비즈니스용 Skype 서버](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>보관 정책을 사용하여 Windows PowerShell

**Set-CsArchivingPolicy** cmdlet을 사용하여 보관 정책을 Windows PowerShell 수 있습니다.
  
### <a name="enable-archiving-policies"></a>보관 정책 사용

내부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveInternal 매개 변수의 값을 True($True). 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

외부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveExternal 매개 변수의 값을 True(다음 값)로 $True. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

내부 및 외부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveInternal 및 ArchiveExternal 매개 변수의 값을 True로 설정합니다. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>보관 정책 사용 안

보관을 모두 사용하지 않도록 설정하기 위해 ArchiveInternal 매개 변수와 ArchiveExternal 매개 변수의 값을 모두 False($False). 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
