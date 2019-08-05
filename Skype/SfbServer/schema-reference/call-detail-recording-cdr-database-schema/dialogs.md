---
title: 비즈니스용 Skype 서버 2015의 대화 상자 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 테이블은 피어 투 피어 세션에 대 한 DialogIDs에 대 한 정보를 저장 하는 지원 테이블입니다.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196763"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 대화 상자 테이블
 
Dialogs 테이블은 피어 투 피어 세션에 대 한 DialogIDs에 대 한 정보를 저장 하는 지원 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |주요한  <br/> |세션 요청 시간 세션을 고유 하 게 식별 하는 SessionIDSeq와 함께 사용 됩니다.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |주요한  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIDTime과 함께 사용 됩니다.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID의 체크섬입니다. 이 필드는 데이터베이스 검색 속도를 높이는 데 사용 됩니다.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |이진으로 저장 된 SIP 대화 상자 ID입니다. 이진 파일의 형식은 다음과 같습니다.  <br/> 대화 상자; from 태그; 태그  <br/> 이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

