---
title: 비즈니스용 Skype 서버 2015의 McuJoinsAndLeaves 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 이 테이블의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다. 예를 들어 사용자가 웹 회의 및 오디오/비디오 요소를 포함 하는 회의에 참가 하는 경우 해당 사용자의 웹 회의 참가에 대해 하나의 레코드가 만들어지고 사용자의 오디오/비디오 회의 참가에 대해 다른 레코드가 만들어집니다.
ms.openlocfilehash: d61b3c1ef1aa6fe481a4022f7bc434b523b68213
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196726"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 McuJoinsAndLeaves 테이블
 
이 테이블의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다. 예를 들어 사용자가 웹 회의 및 오디오/비디오 요소를 포함 하는 회의에 참가 하는 경우 해당 사용자의 웹 회의 참가에 대해 하나의 레코드가 만들어지고 사용자의 오디오/비디오 회의 참가에 대해 다른 레코드가 만들어집니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |컨퍼런스 인스턴스 시간. 회의 인스턴스를 고유 하 게 식별 하기 위해 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |회의 인스턴스를 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**UserId** <br/> |int  <br/> |기본, 외래  <br/> |이 사용자를 식별 하는 고유 번호입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**McuUserInstance** <br/> |int  <br/> |주요한  <br/> |사용자가 한 번에 여러 컴퓨터 또는 장치에 로그온 한 경우 McuUserInstance는 사용자/장치 조합을 고유 하 게 식별 합니다.  <br/> |
|**Is찡그린 Mpstn** <br/> |다소  <br/> | <br/> |사용자가 PSTN에서 가입 하 고 있는지 여부.  <br/> |
|**McuId** <br/> |int  <br/> |기본, 외래  <br/> |이 회의 서버를 식별 하는 고유 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 Mcus 테이블](mcus.md) 을 참조 하세요. <br/> |
|**DialogSessionIdTime** <br/> |dmtf  <br/> |외부  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |외부  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**UserJoinTime** <br/> |dmtf  <br/> | <br/> |이 사용자가 회의 서버에 참가 한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |dmtf  <br/> | <br/> |이 사용자가 회의 서버를 나간 시간입니다.  <br/> |
|**ClientVerId** <br/> |int  <br/> |외부  <br/> |회의에서 클라이언트 소프트웨어 사용의 버전 번호를 지정 하는 식별자입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Clientversions 테이블](clientversions.md) 을 참조 하세요. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   

