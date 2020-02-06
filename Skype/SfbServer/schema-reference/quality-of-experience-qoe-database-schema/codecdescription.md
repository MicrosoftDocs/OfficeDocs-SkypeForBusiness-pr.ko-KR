---
title: CodecDescription 테이블
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 테이블은 고유 코덱 식별자를 해당 하는 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트에 대 한 디지털 신호를 인코딩한 다음 재생을 위해 해당 신호를 디코딩 하는 데 사용 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810366"
---
# <a name="codecdescription-table"></a>CodecDescription 테이블
 
CodecDescription 테이블은 고유 코덱 식별자를 해당 하는 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트에 대 한 디지털 신호를 인코딩한 다음 재생을 위해 해당 신호를 디코딩 하는 데 사용 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |주요한  <br/> |코덱에 할당 된 고유 식별자입니다.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |독특한  <br/> |CodecDescriptionKey에 해당 하는 코덱에 대 한 고유한 설명입니다.  <br/> |
   

