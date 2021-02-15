---
title: CodecDescription 테이블
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
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다. 이 표는 Microsoft Lync Server 2013에서 도입
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831348"
---
# <a name="codecdescription-table"></a>CodecDescription 테이블
 
CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다. 코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다. 이 표는 Microsoft Lync Server 2013에서 도입
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |코덱에 할당된 고유 식별자입니다.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |고유  <br/> |CodecDescriptionKey에 해당하는 코덱의 고유한 설명입니다.  <br/> |
   

