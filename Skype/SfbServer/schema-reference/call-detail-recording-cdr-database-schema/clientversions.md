---
title: 비즈니스용 Skype 서버 2015의 ClientVersions 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 테이블은 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196788"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ClientVersions 테이블
 
ClientVersions 테이블은 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**#** <br/> |**int** <br/> |주요한  <br/> |이 클라이언트 유형 및 버전을 식별 하는 고유 번호입니다.  <br/> |
|**버전** <br/> |**nvarchar (256)** <br/> ||버전 이름입니다.  <br/> |
|**ClientType** <br/> |int  <br/> ||세션에 사용 되는 클라이언트 유형을 지정 합니다. 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
   

