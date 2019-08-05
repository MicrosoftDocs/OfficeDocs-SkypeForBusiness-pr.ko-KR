---
title: 비즈니스용 Skype 서버 2015의 게이트웨이 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: 게이트웨이 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 PSTN (공개 교환 통신망) 통화와 관련 된 게이트웨이 하나에 대 한 정보를 저장 합니다.
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196742"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 게이트웨이 테이블
 
게이트웨이 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 PSTN (공개 교환 통신망) 통화와 관련 된 게이트웨이 하나에 대 한 정보를 저장 합니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |주요한  <br/> |이 게이트웨이를 식별 하는 고유 번호입니다.  <br/> |
|**게이트웨이와** <br/> |nvarchar (256)  <br/> | <br/> |게이트웨이 이름입니다.  <br/> |
   

