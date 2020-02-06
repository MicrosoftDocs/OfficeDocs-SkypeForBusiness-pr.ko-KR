---
title: PurgeSettings 테이블 (체감 품질)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 테이블에는 체감 품질 데이터베이스에서 오래 된 경력 품질 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 비즈니스용 Skype 서버 관리 셸에서 제거 관련 정보를 얻을 수도 있습니다.
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807336"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings 테이블 (체감 품질)
 
PurgeSettings 테이블에는 체감 품질 데이터베이스에서 오래 된 경력 품질 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 비즈니스용 Skype 서버 관리 셸에서 제거 관련 정보를 얻을 수도 있습니다.
  
```PowerShell
Get-CsQoEConfiguration
```

이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**I** <br/> |int  <br/> |주요한  <br/> |체감 품질 purge 설정 컬렉션의 고유 식별자입니다.  <br/> |
|**EnablePurge** <br/> |다소  <br/> ||True (1)로 설정 하면 Microsoft Lync Server 2013 체감 품질 데이터베이스에서 오래 된 레코드가 주기적으로 제거 됩니다. 제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다. False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다. 기본값은 True입니다.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||데이터베이스에서 삭제 되는 체감 품질 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 체감 품질 레코드는 데이터베이스에서 제거 됩니다. 기본값은 60 일입니다.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||데이터베이스 제거를 수행할 현지 시간을 지정 합니다. 시간은 24시간제를 사용하여 지정합니다. 일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다. 기본값은 1 (1:00 AM)입니다. 데이터베이스 제거를 수행할 현지 시간을 지정 합니다. 시간은 24시간제를 사용하여 지정합니다. 일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다. 기본값은 1 (1:00 AM)입니다.  <br/> |
   

