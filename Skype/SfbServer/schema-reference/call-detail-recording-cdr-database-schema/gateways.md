---
title: 비즈니스용 Skype 서버 2015의 Gateways 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 PSTN(Public Switched Telephone Network) 통화와 관련된 하나의 게이트웨이에 대한 정보를 저장합니다.
ms.openlocfilehash: 35b552239d272f47d1f21c0940620dda4e6f075d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777758"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 Gateways 테이블
 
Gateways 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 PSTN(Public Switched Telephone Network) 통화와 관련된 하나의 게이트웨이에 대한 정보를 저장합니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |이 게이트웨이를 식별하는 고유 번호입니다.  <br/> |
|**게이트웨이** <br/> |nvarchar(256)  <br/> | <br/> |게이트웨이 이름입니다.  <br/> |
   

