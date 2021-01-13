---
title: PurgeSettings 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 테이블에는 오래된 통화 정보 기록을 CDR 데이터베이스에서 자동으로 삭제할지 여부 및 시기를 지정하는 정보가 포함됩니다. 다음 명령을 실행하여 비즈니스용 Skype 서버 2015 내에서도 제거 관련 정보를 얻을 수 있습니다.
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823168"
---
# <a name="purgesettings-table"></a>PurgeSettings 테이블
 
PurgeSettings 테이블에는 오래된 통화 정보 기록을 CDR 데이터베이스에서 자동으로 삭제할지 여부 및 시기를 지정하는 정보가 포함됩니다. 다음 명령을 실행하여 비즈니스용 Skype 서버 2015 내에서도 제거 관련 정보를 얻을 수 있습니다.
  
```PowerShell
Get-CsCdrConfiguration
```

관리자는 PurgeSettings 테이블을 읽기 전용으로 처리해야 합니다. 통화 정보 삭제 설정은 [New-CsCdrConfiguration 또는 Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여만 변경해야 합니다. [](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Primary  <br/> |CDR 삭제 설정 컬렉션에 대한 고유 식별자입니다.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||True(1)로 설정하면 비즈니스용 Skype 서버 2015가 CDR 데이터베이스에서 기한이 지난 레코드를 주기적으로 제거합니다. 삭제는 매일 PurgeHour 설정으로 지정된 시간에 수행됩니다. False(0)로 설정하면 레코드가 데이터베이스에서 자동으로 삭제되지 않습니다. 기본값은 True입니다.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||데이터베이스에서 삭제할 CDR 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 CDR 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||데이터베이스에서 삭제할 오류 보고서 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 오류 보고서 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||데이터베이스 삭제가 수행되는 현지 시간을 지정합니다. 시간은 24시간제를 사용하여 지정합니다. 0은 자정(오전 12:00)을 나타내고 23은 오후 11:00를 나타냅니다. 시간만 지정할 수 있습니다. 즉, 값으로 10(오전 10:00)은 사용할 수는 있지만, 10:30 또는 10.5(오전 10:30)는 사용할 수 없습니다. 기본값은 2(오전 2:00)입니다.  <br/> |
   

