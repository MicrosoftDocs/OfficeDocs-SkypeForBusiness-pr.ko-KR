---
title: 비즈니스용 Skype 서버 2015의 ClientVersions 테이블
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 테이블은 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.
ms.openlocfilehash: dd9afc6addef78bf255e6237f1b29f5cac4ee071
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386327"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ClientVersions 테이블
 
ClientVersions 테이블은 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |이 클라이언트 유형 및 버전을 식별하는 고유 번호입니다.  <br/> |
|**버전** <br/> |**nvarchar(256)** <br/> ||버전 이름입니다.  <br/> |
|**ClientType** <br/> |int  <br/> ||세션에 사용된 클라이언트 유형을 지정합니다. 자세한 내용은 [UserAgentDef 테이블](useragentdef.md) 을 참조하십시오. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
   

