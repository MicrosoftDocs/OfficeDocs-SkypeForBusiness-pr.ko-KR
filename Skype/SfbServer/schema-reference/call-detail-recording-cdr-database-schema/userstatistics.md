---
title: UserStatistics 테이블
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 개별 사용자의 시스템 사용에 대한 정보가 저장됩니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 29c710f86560ff204d1e6f97794cf6760a924242
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393680"
---
# <a name="userstatistics-table"></a>UserStatistics 테이블
 
UserStatistics 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 개별 사용자의 시스템 사용에 대한 정보가 저장됩니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |이 사용자를 식별하는 고유 번호입니다.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||사용자가 마지막으로 로그인한 시간입니다.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||사용자가 회의를 마지막으로 구성한 시간입니다.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||사용자가 마지막으로 호출 실패를 경험한 시간입니다.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||사용자가 전화 회의 이끌이로 통화에 마지막으로 실패한 시간입니다.  <br/> |
   

