---
title: PurgeSettings 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 테이블에는 CDR 데이터베이스에서 오래 된 통화 정보 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 비즈니스용 Skype 서버 2015 내에서 제거 관련 정보를 얻을 수도 있습니다.
ms.openlocfilehash: fbbd7908446fdb042c8fdfa2f0c8bec2d83b24d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992918"
---
# <a name="purgesettings-table"></a>PurgeSettings 테이블
 
PurgeSettings 테이블에는 CDR 데이터베이스에서 오래 된 통화 정보 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 비즈니스용 Skype 서버 2015 내에서 제거 관련 정보를 얻을 수도 있습니다.
  
```PowerShell
Get-CsCdrConfiguration
```

관리자는 PurgeSettings 테이블을 읽기 전용으로 처리 해야 합니다. 통화 정보 제거 설정의 변경 사항은 [새로운-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet을 사용해 서만 이루어져야 합니다.
  
이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**I** <br/> |int  <br/> |주요한  <br/> |CDR 제거 설정 컬렉션의 고유 식별자입니다.  <br/> |
|**EnablePurge** <br/> |다소  <br/> ||True (1)로 설정 된 경우 비즈니스용 Skype Server 2015는 CDR 데이터베이스에서 오래 된 레코드를 주기적으로 제거 합니다. 제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다. False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다. 기본값은 True입니다.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||데이터베이스에서 제거 되는 CDR 레코드의 보존 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 CDR 레코드가 데이터베이스에서 제거 됩니다. 기본값은 60 일입니다.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||데이터베이스에서 삭제 되는 오류 보고서 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 오류 보고서 레코드가 데이터베이스에서 제거 됩니다. 기본값은 60 일입니다.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||데이터베이스 제거를 수행할 현지 시간을 지정 합니다. 시간은 24시간제를 사용하여 지정합니다. 일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다. 기본값은 2(오전 2:00)입니다.  <br/> |
   

