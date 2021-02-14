---
title: 비즈니스용 Skype 서버에서 기존 보관 정책 변경
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '요약: 비즈니스용 Skype 서버에 대한 사용자 보관 정책을 변경하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817708"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 기존 보관 정책 변경
 
**요약:** 비즈니스용 Skype 서버에 대한 사용자 보관 정책을 변경하는 방법에 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버를 처음 배포할 때 배포의 사용자에 대해 보관이 구현되는 방법을 결정하는 초기 보관 정책을 설정할 수 있습니다. 이 항목에서는 정책을 관리하고 수정하는 방법에 대해 설명합니다. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>제어판을 사용하여 보관 정책 변경

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
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
    > 사용자 정책 설정은 관리자가 정책을 적용한 특정 사용자 및 사용자 그룹에만 적용됩니다. 자세한 내용은 비즈니스용 Skype 서버의 사용자에게 보관 정책 [적용을 참조하세요.](apply-a-policy-to-users.md) 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>보관 정책을 사용하여 Windows PowerShell

**Set-CsArchivingPolicy** cmdlet을 사용하여 보관 정책을 Windows PowerShell 수 있습니다.
  
### <a name="enable-archiving-policies"></a>보관 정책 사용

내부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveInternal 매개 변수의 값을 True($True) 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

외부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveExternal 매개 변수의 값을 True($True) 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

내부 및 외부 통신 세션의 보관을 사용하도록 설정하려면 ArchiveInternal 및 ArchiveExternal 매개 변수의 값을 True로 설정합니다. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>보관 정책 사용 안

보관을 모두 사용하지 않도록 설정하기 위해 ArchiveInternal 및 ArchiveExternal 매개 변수의 값을 False($False) 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
