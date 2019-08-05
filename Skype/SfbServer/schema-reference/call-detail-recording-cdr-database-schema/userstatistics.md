---
title: UserStatistics 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 테이블은 지원 테이블입니다. 표의 각 레코드에는 시스템의 개별 사용자 사용에 대 한 정보가 저장 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196666"
---
# <a name="userstatistics-table"></a>UserStatistics 테이블
 
UserStatistics 테이블은 지원 테이블입니다. 표의 각 레코드에는 시스템의 개별 사용자 사용에 대 한 정보가 저장 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |주요한  <br/> |이 사용자를 식별 하는 고유 번호입니다.  <br/> |
|**LastLogInTime** <br/> |dmtf  <br/> ||사용자가 마지막으로 로그인 한 시간  <br/> |
|**LastConfOrganizedTime** <br/> |dmtf  <br/> ||사용자가 회의를 마지막으로 구성한 시간입니다.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |dmtf  <br/> ||마지막으로 사용자에 게 전화 실패가 발생 한 시간입니다.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |dmtf  <br/> ||마지막으로 사용자에 게 컨퍼런스 이끌이로 인해 전화 실패가 발생 한 시간입니다.  <br/> |
   

