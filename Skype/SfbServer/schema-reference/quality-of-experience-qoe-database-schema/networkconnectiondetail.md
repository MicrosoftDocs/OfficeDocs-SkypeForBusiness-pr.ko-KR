---
title: NetworkConnectionDetail 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 테이블은 네트워크 연결 유형을 품질 데이터베이스의 다른 곳에서 사용되는 네트워크 연결 식별자에 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 6d39d9e8432a20102d42cea649a51596ce2c1762
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833192"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 테이블
 
NetworkConnectionDetail 테이블은 네트워크 연결 유형을 품질 데이터베이스의 다른 곳에서 사용되는 네트워크 연결 식별자에 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |네트워크 연결 유형의 고유 식별자입니다.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Unique  <br/> |NetworkConnectionDetailKey에 해당하는 네트워크 연결 유형입니다. 사용 가능한 값은 다음과 같습니다.  <br/> 0 -- 유선  <br/> 1 -- WiFi  <br/> 2 -- 이더넷  <br/> 3 -- MobileBB  <br/> 4 -- 기타  <br/> 5 -- Tunnel  <br/> |
   

