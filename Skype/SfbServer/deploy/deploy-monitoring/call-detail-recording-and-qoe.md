---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 및 환경 품질 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '요약: 비즈니스용 Skype 서버에서 CDR 및 체감 품질를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 3e0ff3e8dab09f38d71f9b5211f900e0f0e5fe9f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790056"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 정보 기록 및 환경 품질 설정 구성
 
**요약:** 비즈니스용 Skype 서버에서 CDR 및 체감 품질를 구성 하는 방법에 대해 알아봅니다.
  
비즈니스용 Skype 서버용 SQL Server Reporting Services 보고서를 사용 하 여 CDR 및 체감 품질 모니터링을 구성 합니다.
  
## <a name="configure-cdr-and-qoe"></a>CDR 및 체감 품질 구성

프런트 엔드 풀과 모니터링 저장소를 연결 하 고 모니터링 저장소를 설정한 다음 설치 및 구성 SQL Server Reporting Services 및 모니터링 보고서를 사용 하 여, CDR (통화 정보 기록) 및 경력 (체감 품질)을 관리할 수 있습니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 모니터링 비즈니스용 skype 서버 관리 셸 cmdlet을 사용 하면 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 CDR 및/또는 체감 품질 모니터링을 활성화 및 비활성화할 수 있습니다. 다음과 같이 간단한 명령으로 수행할 수 있습니다.
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

비즈니스용 Skype 서버를 설치 하는 경우에는 CDR 및 체감 품질에 대해 미리 정의 된 전역 구성 설정 모음도 설치 됩니다. 통화 정보 기록에 사용 되는 일반적으로 사용 되는 일부 설정에 대 한 기본값은 다음 표에 나와 있습니다.
  
|**속성**|**설명**|**기본값**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |CDR를 사용할 수 있는지 여부를 나타냅니다. True 인 경우 모든 CDR 레코드가 수집 되 고 모니터링 데이터베이스에 기록 됩니다.  <br/> |False  <br/> |
|EnablePurging  <br/> |CDR 레코드를 데이터베이스에서 정기적으로 삭제할지 여부를 나타냅니다. True 인 경우 KeepCallDetailForDays 속성 (CDR 레코드) 및 KeepErrorReportForDays (CDR 오류의 경우)에서 지정한 기간 후 레코드가 삭제 됩니다. False 인 경우, CDR 레코드가 무기한 유지 됩니다.  <br/> |False  <br/> |
|KeepCallDetailForDays  <br/> |CDR 레코드가 데이터베이스에 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다. 그러나이는 제거가 활성화 된 경우에만 발생 합니다.  <br/> KeepCallDetailForDays는 1 ~ 2562 일 (약 7 년) 사이의 정수 값으로 설정할 수 있습니다.  <br/> |60일  <br/> |
|KeepErrorReportForDays  <br/> |CDR 오류 보고서 보관 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 보고서는 자동으로 삭제 됩니다. CDR 오류 보고서는 비즈니스용 Skype 서버와 같은 클라이언트 응용 프로그램에서 업로드 하는 진단 보고서입니다.  <br/> 이 속성은 1에서 2562 일 사이의 정수 값으로 설정할 수 있습니다.  <br/> |60일  <br/> |
   
마찬가지로, 선택한 체감 품질 설정에 대 한 기본값이이 표에 표시 됩니다.
  
|**속성**|**설명**|**기본값**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |체감 품질 모니터링을 사용할 수 있는지 여부를 나타냅니다. True 인 경우 모든 체감 품질 레코드가 수집 되 고 모니터링 데이터베이스에 기록 됩니다.  <br/> |False  <br/> |
|EnablePurging  <br/> |체감 품질 레코드를 데이터베이스에서 정기적으로 삭제할지 여부를 나타냅니다. True 인 경우 KeepQoEDataForDays 속성에 지정 된 기간 후에 레코드가 삭제 됩니다. False 인 경우 체감 품질 레코드는 무한정 유지 됩니다.  <br/> |False  <br/> |
|KeepQoEDataForDays  <br/> |체감 품질 레코드가 데이터베이스에 유지 되는 일 수를 나타냅니다. 지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다. 그러나이는 제거가 활성화 된 경우에만 발생 합니다.  <br/> KeepCallDetailForDays는 1에서 2562 일 사이의 모든 정수 값으로 설정할 수 있습니다.  <br/> |60일  <br/> |
   
이러한 전역 설정을 수정 해야 하는 경우 CsCdrConfiguration 및 CsQoEConfiguration cmdlet을 사용 하 여이 작업을 수행할 수 있습니다. 예를 들어 비즈니스용 Skype 서버 관리 셸에서 실행 되는이 명령은 전역 범위에서 CDR 모니터링을 사용 하지 않도록 설정 합니다. 이것은 EnableCDR 속성을 False ($False)로 설정 하 여 수행 됩니다.
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

모니터링을 사용 하지 않도록 설정 해도 프런트 엔드 풀의 모니터링 저장소는 분리 되지 않으며 백엔드 모니터링 데이터베이스에 대 한 제거 또는 영향을 받지 않는다는 점에 유의 하세요. 비즈니스용 Skype Server Management Shell을 사용 하 여 CDR 또는 체감 품질 모니터링을 비활성화 하는 경우, 일시적으로 비즈니스용 Skype Server가 모니터링 데이터를 수집 및 보관 하지 못하도록 합니다. 이 경우,이 경우 CDR 데이터를 수집 하 고 보관 하는 작업을 다시 시작 하려면 EnableCDR 속성을 True ($True)로 다시 설정 하기만 하면 됩니다.
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

마찬가지로,이 명령은 전역 범위에서 체감 품질 레코드 제거를 비활성화 합니다.
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

전역 설정 외에 CDR 및 체감 품질 구성 설정은 사이트 범위에 할당할 수 있습니다. 이렇게 하면 모니터링할 때 추가적으로 관리 유연성을 제공 합니다. 예를 들어 관리자는 Redmond 사이트에 대해 CDR 모니터링을 사용 하도록 설정할 수 있지만, 더블린 사이트에 대 한 CDR 모니터링을 사용 하지 않도록 설정 합니다. 사이트 범위에서 새 CDR 구성 설정을 만들려면 다음과 같은 명령을 사용 합니다.
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

사이트 범위에서 구성한 설정이 전역 범위에서 구성 된 설정 보다 우선 한다는 점에 유의 하세요. 예를 들어, 전역 범위에서 CDR 모니터링을 사용 하도록 설정 했지만 사이트 범위 (Redmond 사이트의 경우)에서 사용할 수 없는 경우 이는 레드먼드 사이트의 사용자에 대 한 통화 정보 기록 정보가 보관 되지 않는다는 의미입니다. 그러나 다른 사이트 (즉, Redmond 사이트 설정 대신 전역 설정에서 관리 하는 사용자)의 사용자에 게는 통화 정보 기록 정보가 보관 됩니다.
  
다음과 같은 명령을 사용 하 여 사이트 범위에서 새 체감 품질 구성 설정을 만들 수 있습니다.
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

자세한 내용은 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 하세요.
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
