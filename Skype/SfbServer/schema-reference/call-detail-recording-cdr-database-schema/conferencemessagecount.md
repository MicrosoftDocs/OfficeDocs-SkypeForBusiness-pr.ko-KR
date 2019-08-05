---
title: 비즈니스용 Skype 서버 2015의 ConferenceMessageCount 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 이 테이블의 각 레코드는 한 명의 IM 회의에 있는 한 명의 사용자를 나타내고 해당 사용자가 보낸 메시지 수를 포함 합니다. 각 회의는이 테이블의 여러 레코드로 표시 됩니다. 각 사용자에 대 한 레코드 하나.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196783"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ConferenceMessageCount 테이블
 
이 테이블의 각 레코드는 한 명의 IM 회의에 있는 한 명의 사용자를 나타내고 해당 사용자가 보낸 메시지 수를 포함 합니다. 각 회의는이 테이블의 여러 레코드로 표시 됩니다. 각 사용자에 대 한 레코드 하나.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |컨퍼런스 인스턴스 시간. 회의 인스턴스를 고유 하 게 식별 하기 위해 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |회의 인스턴스를 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**UserId** <br/> |int  <br/> |외부  <br/> |이 사용자를 식별 하는 고유 번호로, [Users 테이블](users.md)에서 참조 합니다.  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |이 회의가 진행 되는 동안이 사용자가 보낸 메시지 수입니다.  <br/> |
   

