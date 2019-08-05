---
title: Media 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 각 레코드는 피어 투 피어 세션에 사용 되는 하나의 미디어 유형을 나타냅니다. 하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다.
ms.openlocfilehash: 181a78a9fc3fabe8c166f4cdc8c452b5a16b016b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196717"
---
# <a name="media-table"></a>Media 테이블
 
각 레코드는 피어 투 피어 세션에 사용 되는 하나의 미디어 유형을 나타냅니다. 하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다.
  
> [!NOTE]
> 미디어 테이블은 세션의 미디어 기간을 계산 하는 데 사용해 서는 안 됩니다. 이 표에는 세션의 미디어 교환 신호 세부 정보가 포함 되어 있습니다. 미디어 교환은 초대 요청에 의해 수행 되며 StartTime은 초대를 보낸 시간을 나타냅니다. 세션을 수락 하는 경우에만 미디어가 시작 되므로 초대 시간이 반드시 미디어 시작 시간을 의미 하는 것은 아닙니다. EndTime은 일반적으로이 세션의 종료 시간을 의미 합니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**MediaId** <br/> |tinyint  <br/> |기본, 외래  <br/> |이 미디어 유형을 식별 하는 고유 번호입니다. 자세한 내용은 [Medialist 테이블](medialist.md) 을 참조 하세요. <br/> |
|**StartTime** <br/> |dmtf  <br/> |주요한  <br/> |이것은 실제 미디어 시작 시간이 아닌 미디어 요청이 전송 된 시간입니다. **StartTime** 에는 세션 설정 시간이 포함 됩니다. <br/> |
|**EndTime** <br/> |dmtf  <br/> ||세션 종료 시간입니다.  <br/> |
   

