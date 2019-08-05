---
title: 비즈니스용 Skype 서버에서 새 보관 정책 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '요약: 비즈니스용 Skype 서버에 대 한 새 보관 정책을 만드는 방법에 대해 알아봅니다.'
ms.openlocfilehash: d6bf33254feece1fe9f1a4fe848b2601e758faf3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197060"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 새 보관 정책 만들기

**요약:** 비즈니스용 Skype 서버에 대 한 새 보관 정책을 만드는 방법에 대해 알아봅니다.
  
제어판을 사용 하거나 Windows PowerShell cmdlet을 사용 하 여 새 보관 정책을 만들 수 있습니다.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>제어판을 사용 하 여 새 보관 정책 만들기

제어판을 사용 하 여 새 보관 정책을 만들려면 다음을 실행 합니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.
    
4. **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다. 
    
   - 사이트 수준 보관 정책을 만들려면 **사이트 정책을**클릭 한 다음 **사이트 선택**에서 정책을 적용 하려는 사이트를 클릭 합니다.
    
   - 사용자 수준 보관 정책을 만들려면 **사용자 정책을**클릭 합니다.
    
5. **새 보관 정책**에서 다음을 수행 합니다.
    
   - **이름**에 새 정책의 이름 (예: externalcontoso)을 지정 합니다.
    
   - **설명**에서 정책에 대 한 세부 정보를 제공 합니다 (예: Contoso에 대 한 외부 사용자 보관 정책).
    
   - 내부 사용자와의 통신 보관을 제어 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.
    
   - 외부 사용자와의 통신 보관을 제어 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.
    
6. **커밋**을 클릭합니다.
    
    > [!IMPORTANT]
    > 사용자 정책 설정은 정책을 적용 하는 특정 사용자 및 사용자 그룹에만 적용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버에서 사용자에 게 보관 정책 적용](apply-a-policy-to-users.md)을 참조 하세요. 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 새 보관 정책 만들기

Windows PowerShell **New CsArchivingPolicy** cmdlet을 사용 하 여 새 보관 정책을 만들 수도 있습니다. 자세한 내용은 [새 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>사이트 수준에서 새 보관 정책 만들기

이 명령은 Redmond 사이트에 대 한 새 보관 정책을 만듭니다.
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>사용자별 수준에서 새 보관 정책을 만들려면

사용자 당 수준에서 새 보관 정책을 만들려면 정책을 만들 때 고유한 Id를 지정 하면 됩니다.
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>내부 통신 세션 보관을 가능 하 게 하는 새 보관 정책을 만들려면

앞의 명령에 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았기 때문에 새 정책은 해당 속성에 대 한 기본값을 사용 합니다. 다른 속성 값을 사용 하는 정책을 만들려면 적절 한 매개 변수와 매개 변수 값을 포함 하면 됩니다. 예를 들어 다음 명령은 내부 인스턴트 메시징 세션 보관을 허용 하는 보관 정책을 만듭니다. 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>내부 및 외부 통신 세션의 보관을 가능 하 게 하는 새 보관 정책을 만들려면

여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 내부 및 외부 인스턴트 메시징 세션을 모두 보관 하도록 새 정책을 구성 합니다.
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
