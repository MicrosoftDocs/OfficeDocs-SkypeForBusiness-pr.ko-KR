---
title: CodecDescription 테이블
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다. 이 표는 Microsoft Lync Server 2013에서 도입된 표입니다.
ms.openlocfilehash: 3f95de9cf7b6e9aaa778644896bcc458229a23d3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384176"
---
# <a name="codecdescription-table"></a>CodecDescription 테이블
 
CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다. 이 표는 Microsoft Lync Server 2013에서 도입된 표입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |코덱에 할당된 고유 식별자입니다.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Unique  <br/> |CodecDescriptionKey에 해당하는 코덱의 고유한 설명입니다.  <br/> |
   

