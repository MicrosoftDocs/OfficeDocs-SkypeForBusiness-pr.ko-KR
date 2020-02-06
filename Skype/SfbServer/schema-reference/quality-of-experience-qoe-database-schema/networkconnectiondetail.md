---
title: NetworkConnectionDetail 테이블
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 테이블은 환경 데이터베이스의 다른 곳에서 사용 되는 네트워크 연결 식별자에 네트워크 연결 유형을 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807506"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 테이블
 
NetworkConnectionDetail 테이블은 환경 데이터베이스의 다른 곳에서 사용 되는 네트워크 연결 식별자에 네트워크 연결 유형을 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |주요한  <br/> |네트워크 연결 형식의 고유 식별자입니다.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |독특한  <br/> |NetworkConnectionDetailKey에 해당 하는 네트워크 연결 형식입니다. 사용 가능한 값은 다음과 같습니다.  <br/> 0--유선  <br/> 1--WiFi  <br/> 2--이더넷  <br/> 3--MobileBB  <br/> 4--기타  <br/> 5--터널  <br/> |
   

