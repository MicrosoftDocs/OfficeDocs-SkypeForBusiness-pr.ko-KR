---
title: 비즈니스용 Skype 서버에서 보관 구성 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 구성을 만드는 방법에 대해 알아봅니다.'
ms.openlocfilehash: bd2a139e7321542e3b13259ebc2ec1e4ba731caf
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992745"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 구성 만들기

**요약:** 비즈니스용 Skype 서버에 대 한 보관 구성을 만드는 방법에 대해 알아봅니다.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>제어판을 사용 하 여 보관 옵션 구성

특정 사이트 또는 풀에 대 한 보관 옵션을 구성 하려면 다음을 수행 합니다. 
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.
    
4. **보관 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다. 
    
   - 사이트 보관 구성을 만들려면 **사이트 구성을**클릭 한 다음 **사이트 선택**에서 보관을 위해 구성할 사이트를 선택 합니다.
    
   - 풀 보관 구성을 만들려면 **풀 구성을**클릭 한 다음 **풀 선택**에서 보관을 위해 구성할 풀을 선택 합니다.
    
5. **새 보관 설정**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행 합니다.
    
   - IM (인스턴트 메시징) 세션에 대해서만 보관을 사용 하도록 설정 하려면 **im 세션 보관**을 클릭 합니다.
    
   - IM 세션과 웹 컨퍼런스 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 웹 회의 세션 보관**을 클릭 합니다.
    
   - 이 구성에 대 한 보관을 사용 하지 않도록 설정 하려면 **보관 사용 안 함을**클릭 합니다.
    
6. 또한 **새 보관 설정**에서 다음을 수행 합니다.
    
   - 보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.
    
   - Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.
    
   - 데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.
    
     - 특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.
    
     - 내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.
    
7. **커밋**을 클릭합니다.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 보관 옵션 구성

**새 CsArchivingConfiguration** cmdlet을 사용 하 여 특정 사이트 또는 풀에 대 한 보관 옵션을 구성할 수도 있습니다.
  
다음 명령은 Redmond 사이트의 보관 구성 설정에 대 한 새 컬렉션을 만듭니다.
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다. 
  
다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다. 다음 예제에서는 기본적으로 메신저 대화 세션만 보관할 수 있는 보관 구성 설정의 컬렉션을 만듭니다.
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 메신저 대화 서비스를 보관 하기 위해 새로운 설정을 구성 하 고 보관 서비스의 인스턴트 메시지를 차단 합니다.
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

자세한 내용은 [새 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
