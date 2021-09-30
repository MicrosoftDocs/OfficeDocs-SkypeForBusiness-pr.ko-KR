---
title: 2013에서 CDR 구성 설정 컬렉션을 만들거나 비즈니스용 Skype 서버
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: '요약: CDR(통화 정보 기록)에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: 1f508df7d139d81d3c91dc1cf9355b61fd028dbc
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015152"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>2013에서 CDR 구성 설정 컬렉션을 만들거나 비즈니스용 Skype 서버
 
**요약:** CDR(통화 정보 기록)에 대해 비즈니스용 Skype 서버.
  
CDR(통화 정보 기록)을 사용하면 피어 투 피어 메신저 대화 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.
  
CDR 비즈니스용 Skype 서버 컬렉션을 설치하면 전역 CDR 구성 설정 컬렉션이 만들어집니다. 관리자에게는 또한 사이트 범위에서 사용자 지정 설정을 만드는 옵션이 제공됩니다. 이러한 사이트 범위의 설정은 사용될 때마다 전역 설정보다 높은 우선 순위를 갖습니다. 예를 들어 레드몬드 사이트에 사이트 범위의 설정을 만들면 전역 설정이 아닌 해당 설정이 레드몬드의 CDR 관리에 사용됩니다.
  
제어판 또는 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여 CDR 비즈니스용 Skype 서버 만들 수 있습니다. 제어판 비즈니스용 Skype 서버 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여 기존 설정을 수정할 수 있습니다. 제어판을 사용하여 비즈니스용 Skype 서버 만들거나 수정하는 경우 다음 옵션을 사용할 수 있습니다.
  
|**UI 설정**|**PowerShell 매개 변수**|**설명**|
|:-----|:-----|:-----|
|이름  <br/> |ID  <br/> |CDR 구성 설정에 대한 고유 ID가 만들어집니다. 이러한 설정은 사이트 범위에서만 만들 수 있습니다.  <br/> |
|CDR 모니터링 사용  <br/> |EnableCDR  <br/> |CDR을 사용할 수 있는지 여부를 나타냅니다.  <br/> |
|CDR 삭제 사용  <br/> |EnablePurging  <br/> |CDR을 CDR 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다.  <br/> |
|최대 기간(일) 동안 CDR 유지  <br/> |KeepCallDetailForDays  <br/> |CDR 기록을 CDR 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 기록은 모두 자동으로 삭제됩니다. 삭제는 삭제를 사용하도록 설정한 경우에만 수행됩니다.  <br/> |
|최대 기간(일) 동안 오류 보고서 데이터 유지  <br/> |KeepErrorReportForDays  <br/> |CDR 오류 보고서를 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 보고서는 모두 자동으로 삭제됩니다. CDR 오류 보고서는 클라이언트 응용 프로그램에서 업로드하는 진단 보고서입니다.  <br/> |
   
> [!NOTE]
> New-CsCdrConfiguration Set-CsCdrConfiguration cmdlet에는 제어판에서 사용할 수 없는 추가 옵션이 비즈니스용 Skype 서버 있습니다. 자세한 [내용은 New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 및 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) 도움말 항목을 참조하십시오.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 CDR 구성 설정을 비즈니스용 Skype 서버

1. 비즈니스용 Skype 서버 제어판에서 **모니터링 및 보관을 클릭합니다.**
    
2. 통화 정보 **기록 탭에서** 새로 추가를 **클릭합니다.**
    
3. **사이트 선택** 대화 상자에서 새 구성 설정을 만들 사이트를 선택합니다. 대화 상자가 빈 상태이면 이미 사이트가 모두 CDR 구성 설정 컬렉션에 할당되었다는 의미입니다. 각 사이트는 단일 CDR 컬렉션으로 제한됩니다. 따라서 설정을 삭제한 후 다시 만들거나, 간단히 기존 설정을 수정하면 됩니다.
    
4. **새 통화 정보 기록 설정 만들기** 대화 상자에서 원하는 항목을 선택한 다음 **커밋** 을 클릭합니다.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 기존 CDR 구성 비즈니스용 Skype 서버 수정하려면

1. 비즈니스용 Skype 서버 제어판에서 **모니터링 및 보관을 클릭합니다.**
    
2. 수정할 설정 컬렉션을 두 번 클릭하거나 컬렉션을 선택하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다. 한 번에 한 컬렉션만 수정할 수 있습니다. 여러 컬렉션을 동일하게 변경하기 위해 비즈니스용 Skype 서버 관리 셸을 사용합니다.
    
3. **통화 정보 기록 설정 편집** 대화 상자에서 원하는 항목을 선택한 다음 **커밋** 을 클릭합니다.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 CDR 구성 Windows PowerShell 만들기

CDR 구성 설정은 **New-CsCdrConfiguration** cmdlet을 사용하여 만들 수도 Windows PowerShell 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>새 CDR 구성 설정 컬렉션을 만들려면

 다음 명령을 실행하면 레드몬드 사이트에 적용되는 새 CDR 구성 설정을 만들 수 있습니다.
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>CDR(통화 정보 기록)을 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면

 이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 CDR(통화 정보 기록)을 기본적으로 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면 다음과 같은 명령을 실행하면 됩니다.
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>새 CDR 구성 설정 컬렉션을 만들 때 여러 속성 값을 지정하려면

 여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 CDR(통화 정보 기록)을 30일 동안, 오류 보고서를 90일 동안 보관하는 새 설정을 구성할 수 있습니다.
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

자세한 내용은 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
