---
title: 비즈니스용 Skype 서버의 EdgeServers 테이블
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
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 통화와 관련된 하나의 에지 서버에 대한 정보를 저장합니다.
ms.openlocfilehash: 98f37ecbf976fb08ae27e080f5e9e498558131fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813208"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 EdgeServers 테이블
 
EdgeServers 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 통화와 관련된 하나의 에지 서버에 대한 정보를 저장합니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primary  <br/> |이 에지 서버를 식별하는 고유 번호입니다.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |에지 서버 이름입니다.  <br/> |
   

