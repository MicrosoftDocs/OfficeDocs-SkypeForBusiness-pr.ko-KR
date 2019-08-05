---
title: McuJoinsAndLeaves 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves 보기는 사용자가 1 회의 서버에 대 한 정보를 참가 및 탈퇴 하는 정보를 저장 합니다. 이 보기의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 9d5617449e5b12c13d855c1a93b39490e2177f0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196727"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves 보기
 
McuJoinsAndLeaves 보기는 사용자가 1 회의 서버에 대 한 정보를 참가 및 탈퇴 하는 정보를 저장 합니다. 이 보기의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |컨퍼런스 인스턴스 시간. 회의 인스턴스를 고유 하 게 식별 하기 위해 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |회의 인스턴스를 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**McuUri** <br/> |nvarchar (256)  <br/> |사용자가 연결 된 회의 서버의 URI입니다.  <br/> |
|**McuUriType** <br/> |nvarchar (256)  <br/> |사용자가 연결 된 회의 서버의 URI입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |회의 서버 참여/종료 정보를 캡처한 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |회의 서버 참여/종료 정보를 캡처한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**UserTenant 넌 트** <br/> |nvarchar (256)  <br/> |회의 서버 참여/종료 정보를 캡처한 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**UserClientVersion** <br/> |nvarchar (256)  <br/> |회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 버전입니다.  <br/> |
|**UserClientType** <br/> |int  <br/> |회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 범주의 이름입니다.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.  <br/> |
|**Isuser찡그린 Mpstn** <br/> |다소  <br/> |사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.  <br/> |
|**DialogSessionIdTime** <br/> |dmtf  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |세션의 SIP 대화 상자 ID입니다. 형식은 대화 상자, from 태그, to 태그입니다.  <br/> |
|**UserJoinTime** <br/> |dmtf  <br/> |사용자가 회의 서버에 참가 한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |dmtf  <br/> |사용자가 회의 서버를 남겨진 시간입니다.  <br/> |
   

