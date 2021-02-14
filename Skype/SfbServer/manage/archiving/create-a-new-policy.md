---
title: 비즈니스용 Skype 서버에서 새 보관 정책 만들기
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '요약: 비즈니스용 Skype 서버에 대한 새 보관 정책을 만드는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3e1f538aba26025f5868a09babd3b67df36f9a3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817648"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 새 보관 정책 만들기

**요약:** 비즈니스용 Skype 서버에 대한 새 보관 정책을 만드는 방법을 배워야 합니다.
  
제어판을 사용하거나 cmdlet을 사용하여 새 보관 정책을 Windows PowerShell 있습니다.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>제어판을 사용하여 새 보관 정책 만들기

제어판을 사용하여 새 보관 정책을 만들 수 있습니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
4. **다음** 을 클릭하고 다음 중 하나를 수행합니다. 
    
   - 사이트 수준 보관 정책을 만들려면 사이트 정책을 클릭한 다음 사이트 선택에서 정책을 적용할 사이트를 클릭합니다.
    
   - 사용자 수준의 보관 정책을 만들려면 **사용자 정책** 을 클릭합니다.
    
5. **새 보관 정책** 에서 다음을 수행합니다.
    
   - **이름** 에 새 정책의 이름을 지정합니다(예: externalContoso).
    
   - **설명** 에 정책에 대한 자세한 설명을 입력합니다(예: Contoso용 외부 사용자 보관 정책).
    
   - 내부 사용자와의 통신 내용의 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
   - 외부 사용자와의 통신 내용의 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
6. **커밋** 을 클릭합니다.
    
    > [!IMPORTANT]
    > 사용자 정책 설정은 관리자가 정책을 적용한 특정 사용자 및 사용자 그룹에만 적용됩니다. 자세한 내용은 비즈니스용 Skype 서버의 사용자에게 보관 정책 [적용을 참조하세요.](apply-a-policy-to-users.md) 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>보관 정책을 사용하여 새 보관 정책을 Windows PowerShell

**New-CsArchivingPolicy** cmdlet을 사용하여 새 보관 정책을 Windows PowerShell 수 있습니다. 자세한 내용은 [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>사이트 수준에서 새 보관 정책을 만들 수 있습니다.

이 명령은 Redmond 사이트에 대한 새로운 보관 정책을 만듭니다.
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>사용자 수준에서 새 보관 정책을 만들 수 있습니다.

사용자 수준에서 새 보관 정책을 만들 경우 정책을 만들 때 고유 ID를 지정하기만하면 됩니다.
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>내부 통신 세션의 보관을 사용할 수 있는 새 보관 정책을 만들 수 있습니다.

이전 명령에서는 필수 Identity 매개 변수를 제외하고 어떤 매개 변수도 지정되지 않았기 때문에 새로운 정책이 모든 속성에 대해 기본값을 사용합니다. 다른 속성 값을 사용하는 정책을 만들려면 적합한 매개 변수 및 매개 변수 값을 포함하기만 하면 됩니다. 예를 들어 다음 명령은 내부 인스턴트 메시징 세션의 보관을 허용하는 보관 정책을 만듭니다. 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>내부 및 외부 통신 세션 모두의 보관을 사용할 수 있는 새 보관 정책을 만들 수 있습니다.

여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령은 내부 및 외부 인스턴트 메시징 세션을 모두 보관하도록 새 정책을 구성합니다.
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
