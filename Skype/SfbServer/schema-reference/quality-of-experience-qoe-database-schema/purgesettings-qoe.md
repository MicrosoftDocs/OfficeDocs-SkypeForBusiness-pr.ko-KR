---
title: PurgeSettings 테이블(QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 테이블은 오래된 체감 품질 레코드가 QoE 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 포함합니다. 제거 관련 정보는 다음 명령을 실행하여 비즈니스용 Skype 서버 관리 셸 내에서 얻을 수도 있습니다.
ms.openlocfilehash: eb5b0570073498580ec2ad468ea50474e0246b07
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620824"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings 테이블(QoE)
 
PurgeSettings 테이블은 오래된 체감 품질 레코드가 QoE 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 포함합니다. 제거 관련 정보는 다음 명령을 실행하여 비즈니스용 Skype 서버 관리 셸 내에서 얻을 수도 있습니다.
  
```PowerShell
Get-CsQoEConfiguration
```

이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |QoE 삭제 설정 컬렉션의 고유 식별자입니다.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||True(1)로 설정하면 Microsoft Lync Server 2013이 QoE 데이터베이스에서 기한이 지난 레코드를 주기적으로 제거합니다. 삭제는 매일 PurgeHour 설정으로 지정된 시간에 수행됩니다. False(0)로 설정하면 레코드가 데이터베이스에서 자동으로 삭제되지 않습니다. 기본값은 True입니다.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||QoE 레코드가 데이터베이스에서 삭제되는 기간(일)을 지정합니다. 삭제가 사용하도록 설정된 경우 이 값보다 오래된 QoE 레코드가 데이터베이스에서 제거됩니다. 기본값은 60일입니다.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||데이터베이스 삭제가 수행되는 로컬 시간을 지정합니다. 시간은 24시간제를 사용하여 지정되며 0이 자정(오전 12시)을, 23이 오후 11시를 나타냅니다. 시간 단위만 지정할 수 있습니다. 즉, 오전 10시를 나타내는 10은 값으로 허용되지만 오전 10시 30분을 나타내는 10:30 또는 10.5는 값으로 허용되지 않습니다. 기본값은 1(오전 1시)입니다.  <br/> |
   

