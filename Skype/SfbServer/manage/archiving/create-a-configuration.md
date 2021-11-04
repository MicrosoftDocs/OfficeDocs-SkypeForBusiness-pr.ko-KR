---
title: 보관 구성을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: '요약: 사용자에 대한 보관 구성을 만드는 비즈니스용 Skype 서버.'
ms.openlocfilehash: abb7f6c894dae734a45d7668f5b1b590d869c9c6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767906"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>보관 구성을 비즈니스용 Skype 서버

**요약:** 사용자에 대한 보관 구성을 만드는 방법을 비즈니스용 Skype 서버.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>제어판을 사용하여 보관 옵션 구성

특정 사이트 또는 풀에 대한 보관 옵션을 구성합니다. 
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.
    
4. **보관 구성** 페이지에서 **새로 만들기** 를 클릭하고 다음 중 하나를 수행합니다. 
    
   - 사이트 보관 구성을 만들려면 사이트 구성을 클릭한 다음 사이트 선택에서 보관에 대해 구성할 사이트를 선택합니다. 
    
   - 풀 보관 구성을 만들려면 풀 구성을 클릭한 다음 풀 선택에서 보관에 대해 구성할 풀을 선택합니다. 
    
5. **새 보관 설정 만들기** 의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행합니다.
    
   - 메신저 대화 세션에 대해서만 보관을 사용하도록 설정하려면 **메신저 대화 세션 보관** 을 클릭합니다.
    
   - 메신저 대화 세션 및 웹 회의 모두에 대해 보관을 사용하도록 설정하려면 **메신저 대화 및 웹 회의 세션 보관** 을 클릭합니다.
    
   - 이 구성에 대해 보관을 사용하지 않도록 설정하려면 보관 **사용 안 을 클릭합니다.**
    
6. 또한 **새 보관 설정** 에서 다음을 수행합니다.
    
   - 보관을 사용할 수 없을 경우 작업을 차단하려면 **보관에 실패할 경우 메신저 대화 또는 웹 회의 세션 차단** 확인란을 선택합니다.
    
   - 이 Microsoft Exchange Server 사용하여 보관 데이터를 저장하려면 Microsoft Exchange **통합 확인란을** 클릭합니다.
    
   - 데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.
    
     - 특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제** 를 클릭한 다음 일 수를 지정합니다.
    
     - 내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제** 를 클릭합니다,
    
7. **커밋** 을 클릭합니다.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>보관 옵션을 사용하여 Windows PowerShell

**New-CsArchivingConfiguration** cmdlet을 사용하여 특정 사이트 또는 풀에 대한 보관 옵션을 구성할 수도 있습니다.
  
다음 명령을 실행하면 레드몬드 사이트에 대해 새 보관 구성 설정 컬렉션이 만들어집니다.
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다. 
  
다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 다음 예에서는 기본적으로 인스턴트 메시징 세션의 보관만 허용하는 보관 구성 설정 컬렉션을 만듭니다.
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 메신저 대화 세션을 보관하고 보관 서비스를 사용할 수 없는 메신저 대화는 차단하는 새로운 설정을 구성할 수 있습니다.
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

자세한 내용은 [New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.