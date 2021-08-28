---
title: 보관 옵션을 구성하여 오류 처리를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '요약: 보관을 차단하는 오류 발생 시 IM 및 회의 세션을 비즈니스용 Skype 서버 방법을 설명하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: f86b26178963621b4d71a657e589a63f1351aeef
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592572"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>보관 옵션을 구성하여 오류 처리를 비즈니스용 Skype 서버

**요약:** 보관을 차단하는 오류 발생 시 IM 및 회의 세션을 비즈니스용 Skype 서버 방법을 학습합니다.
  
조직에 보관이 필요한 경우 보관을 차단하는 오류 발생 시 IM 및 회의 세션을 비즈니스용 Skype 서버 수 있습니다. 이를 중요 모드라고도 합니다. 예를 들어 저장소 서비스에 문제가 있는 경우 통신이 보관을 사용하도록 설정된 사용자에 대해 IM이 차단됩니다. 오류가 수정된 다음에는 IM 및 회의 모두 자동으로 복구됩니다. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>제어판을 사용하여 중요 모드 구성

보관을 차단하는 오류 발생 시 통신 세션을 허용할지 여부를 지정합니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.
    
4. 보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성의 이름을 클릭하고 편집을 **클릭한** 다음 자세한 정보 **표시를 클릭합니다.**
    
5. 보관이 실패할 경우 보관이 작동되는 방식을 설정하려면 **보관이 실패할 경우 IM(인스턴트 메시징) 또는 웹 회의 세션 차단** 확인란을 선택하거나 선택 취소합니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>사용자 설정을 사용하여 중요 모드 Windows PowerShell

**또한 Set-CsArchivingConfiguration** cmdlet을 BlockOnArchiveFailure 매개 변수와 함께 사용하여 보관을 방지하는 오류가 발생하면 통신 세션을 허용할지 여부를 지정할 수 있습니다.
  
예를 들어 다음 명령은 보관 실패 시 통신을 사용하지 않도록 설정합니다.
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

다음 명령은 보관 실패 시 통신을 사용할 수 있습니다.
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

자세한 내용은 [Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
