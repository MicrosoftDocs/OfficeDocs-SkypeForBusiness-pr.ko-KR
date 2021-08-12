---
title: 미디어 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 각 레코드는 피어-투-피어 세션에 사용된 하나의 미디어 유형을 나타냅니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.
ms.openlocfilehash: 095e1f3227bbaf3335f581acbebbddaccd6b73de33639b2a0d04302a5c104393
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322950"
---
# <a name="media-table"></a>미디어 테이블
 
각 레코드는 피어-투-피어 세션에 사용된 하나의 미디어 유형을 나타냅니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.
  
> [!NOTE]
> Media 테이블을 사용하여 세션의 미디어 기간을 계산해서는 안 됩니다. 이 테이블에는 세션에 포함된 미디어 교환의 신호 세부 정보가 포함됩니다. 미디어 교환은 INVITE 요청에 의해 수행되며 StartTime은 INVITE가 전송된 시간을 나타냅니다. 미디어는 세션 참가자가 세션을 수락한 후에만 시작되므로 초대 시간이 반드시 미디어 시작 시간인 것은 아닙니다. EndTime은 일반적으로 이 세션의 종료 시간을 의미합니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |세션 요청 시간입니다. **SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primary, Foreign  <br/> |이 미디어 유형을 식별하는 고유 번호입니다. 자세한 내용은 [MediaList 테이블을](medialist.md) 참조하세요. <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |실제 미디어 시작 시간이 아니라 미디어 요청이 전송된 시간입니다. **StartTime** 에는 세션 설정 시간이 포함됩니다.<br/> |
|**EndTime** <br/> |datetime  <br/> ||세션의 종료 시간입니다.  <br/> |
   

