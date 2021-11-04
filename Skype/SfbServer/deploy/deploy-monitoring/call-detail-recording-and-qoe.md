---
title: 통화 정보 기록 및 품질 설정을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '요약: 사용자 계정에서 CDR 및 QoE를 구성하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: abb6996a7483afb8526731ac69404174883ce313
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745324"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>통화 정보 기록 및 품질 설정을 비즈니스용 Skype 서버
 
**요약:** CDR 및 QoE를 구성하는 방법을 비즈니스용 Skype 서버.
  
CDR 및 QoE 모니터링을 구성하기 위해 SQL Server Reporting Services 보고서를 비즈니스용 Skype 서버.
  
## <a name="configure-cdr-and-qoe"></a>CDR 및 QoE 구성

모니터링 저장소를 프런트 엔드 풀과 연결한 후 모니터링 저장소를 설정한 다음 SQL Server Reporting Services 및 모니터링 보고서를 설치 및 구성하면 비즈니스용 Skype 서버 관리 셸을 사용하여 CDR(통화 정보 기록) 및 QoE(QoE) 모니터링을 관리할 수 있습니다. 비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하면 특정 사이트 또는 전체 사이트 배포에 대해 CDR 및/또는 QoE 모니터링을 비즈니스용 Skype 서버 수 있습니다. 이 명령은 다음과 같은 간단한 명령으로 수행될 수 있습니다.
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

설치 비즈니스용 Skype 서버 CDR 및 QoE 모두에 대해 미리 정의한 전역 구성 설정 컬렉션도 설치합니다. 통화 정보 기록에서 사용하는 보다 일반적으로 사용되는 설정 중 일부의 기본값이 아래 표에 나와 있습니다.
  
|**속성**|**설명**|**기본값**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |CDR을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 CDR 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.  <br/> |True  <br/> |
|EnablePurging  <br/> |CDR 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepCallDetailForDays(CDR 레코드) 및 KeepErrorReportForDays(CDR 오류) 속성에 지정된 기간이 지난 후 기록이 삭제됩니다. False인 경우에는 CDR 레코드가 무기한 유지됩니다.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |CDR 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.  <br/> KeepCallDetailForDays는 1에서 2562일(약 7년) 사이의 정수 값으로 설정할 수 있습니다.  <br/> |60일  <br/> |
|KeepErrorReportForDays  <br/> |CDR 오류 보고서가 보관되는 일 수를 나타냅니다. 지정된 일 수보다 오래된 보고서는 자동으로 삭제됩니다. CDR 오류 보고서는 오류 보고서와 같은 클라이언트 응용 프로그램에서 업로드하는 진단 비즈니스용 Skype 서버.  <br/> 이 속성은 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.  <br/> |60일  <br/> |
   
마찬가지로, 선택한 QoE 설정에 대한 기본값이 아래 표에 나와 있습니다.
  
|**속성**|**설명**|**기본값**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |QoE 모니터링을 사용할 수 있는지 여부를 나타냅니다. True인 경우 모든 QoE 레코드가 수집되어 모니터링 데이터베이스에 기록됩니다.  <br/> |True  <br/> |
|EnablePurging  <br/> |QoE 레코드를 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다. True이면 KeepQoEDataForDays 속성에 지정된 기간이 지난 후 레코드가 삭제됩니다. False인 경우 QoE 레코드는 무기한 유지됩니다.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |QoE 레코드를 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 레코드는 모두 자동으로 삭제됩니다. 그러나 이 작업은 삭제가 사용하도록 설정된 경우에만 수행됩니다.  <br/> KeepCallDetailForDays는 1에서 2562일 사이의 정수 값으로 설정할 수 있습니다.  <br/> |60일  <br/> |
   
이러한 전역 설정을 수정해야 하는 경우 Set-CsCdrConfiguration cmdlet을 사용하여 Set-CsQoEConfiguration 수 있습니다. 예를 들어 이 명령(비즈니스용 Skype 서버 관리 셸 내에서 실행)은 전역 범위에서 CDR 모니터링을 사용하지 않도록 설정합니다. EnableCDR 속성을 False($False) 설정하여 이 $False.
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

모니터링을 사용하지 않도록 설정해도 프런트 엔드 풀에서 모니터링 저장소의 연결이 해제되지 않으며, 백 엔드 모니터링 데이터베이스가 제거되거나 다른 방식으로 영향을 받지도 않습니다. 관리 비즈니스용 Skype 서버 사용하여 CDR 또는 QoE 모니터링을 사용하지 않도록 설정하는 경우 실제로는 모니터링 데이터 수집 및 보관을 일시적으로 비즈니스용 Skype 서버 중지하면 됩니다. 이 경우 CDR 데이터 수집 및 보관을 다시 시작하려면 EnableCDR 속성을 다시 True($True)로 설정하기만 하면 됩니다.
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

마찬가지로, 다음 명령은 전역 범위에서 QoE 레코드 삭제를 사용하지 않도록 설정합니다.
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

이처럼 전역 설정을 사용할 수 있을 뿐 아니라, CDR 및 QoE 구성 설정을 사이트 범위에도 할당할 수 있습니다. 이렇게 하면 모니터링을 보다 유동적으로 관리할 수 있습니다. 예를 들어 관리자는 Redmond 사이트에 대해서는 CDR 모니터링을 사용하도록 설정하고 Dublin 사이트에 대해서는 CDR 모니터링을 사용하지 않도록 설정할 수 있습니다. 사이트 범위에서 새 CDR 구성 설정을 만들려면 다음과 같은 명령을 사용합니다.
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다. 예를 들어 Redmond 사이트에 대해 CDR 모니터링이 전역 범위에서는 사용하도록 설정되고 사이트 범위에서는 사용하지 않도록 설정되어 있다고 가정해 보겠습니다. 이는 Redmond 사이트에 있는 사용자의 통화 정보 기록 정보가 보관되지 않음을 의미합니다. 그러나 다른 사이트에 있는 사용자(Redmond 사이트 설정 대신 전역 설정에 의해 관리되는 사용자)의 통화 정보 기록 정보는 보관됩니다.
  
다음과 같은 명령을 사용하면 사이트 범위에서 새 QoE 구성 설정을 만들 수 있습니다.
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

자세한 내용은 관리 셸의 비즈니스용 Skype 서버 입력합니다.
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
