---
title: 미디어 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 미디어 보기는 피어 투 피어 세션에 사용 되는 미디어 형식에 대 한 정보를 저장 합니다. 하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196718"
---
# <a name="media-view"></a>미디어 보기
 
미디어 보기는 피어 투 피어 세션에 사용 되는 미디어 형식에 대 한 정보를 저장 합니다. 하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
> [!NOTE]
> 미디어 보기는 세션의 미디어 기간을 계산 하는 데 사용해 서는 안 됩니다. 이 보기에는 세션의 미디어 교환에 대 한 신호 세부 정보가 포함 됩니다. 미디어 교환은 초대 요청에 의해 수행 되며 StartTime은 초대를 보낸 시간을 나타냅니다. 세션이 허용 된 후에만 미디어가 시작 되므로 초대 시간이 반드시 미디어 시작 시간을 의미 하는 것은 아닙니다. 
  
미디어 보기에는 [Sessiondetails 보기](sessiondetails-0.md) 의 모든 열이 포함 되어 있으며 아래 목록에 나열 되어 있습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**미디어** <br/> |nvarchar (256)  <br/> |미디어 유형입니다. 자세한 내용은 [Medialist 테이블](medialist.md) 을 참조 하세요. <br/> |
|**MediaStartTime** <br/> |dmtf  <br/> |미디어 요청이 전송 된 시간입니다.  <br/> |
|**MediaEndTime** <br/> |dmtf  <br/> |세션 종료 시간입니다.  <br/> |
   

