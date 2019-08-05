---
title: FocusJoinsAndLeaves 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves 보기는 한 회의에 대 한 참가 및 탈퇴 정보에 대 한 정보를 저장 합니다. 각 회의는 사용자가 회의에 참가 하 고 떠날 때마다 기록 하는 레코드를 기준으로이 보기로 표시 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: f739ae390b636913d96b49dd516d2618c72515e6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196747"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves 보기
 
FocusJoinsAndLeaves 보기는 한 회의에 대 한 참가 및 탈퇴 정보에 대 한 정보를 저장 합니다. 각 회의는 사용자가 회의에 참가 하 고 떠날 때마다 기록 하는 레코드를 기준으로이 보기로 표시 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |컨퍼런스 인스턴스 시간. 회의 인스턴스를 고유 하 게 식별 하기 위해 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |회의 인스턴스를 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |회의 참가/정보 남기기를 캡처한 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |회의 참가/정보 남기기를 캡처한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**UserTenant 넌 트** <br/> |nvarchar (256)  <br/> |회의 참가/정보 남기기를 캡처한 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |회의 참가/종료 정보가 캡처 된 사용자의 고유 식별자입니다.  <br/> |
|**UserClientVersion** <br/> |nvarchar (256)  <br/> |회의 참가/정보 남기기를 캡처한 사용자가 사용 하는 클라이언트 버전입니다.  <br/> |
|**UserClientType** <br/> |int  <br/> |회의 참가/정보 남기기를 캡처한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |회의 참가/정보 남기기를 캡처한 사용자가 사용 하는 클라이언트 범주의 이름입니다.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |다소  <br/> |사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.  <br/> |
|**DialogSessionIdTime** <br/> |dmtf  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 한 경우 UserInstance는 사용자/장치 조합을 고유 하 게 식별 하는 데 사용 됩니다.  <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |세션의 SIP 대화 상자 ID입니다. 형식은 대화 상자, from 태그, to 태그입니다.  <br/> |
|**UserJoinTime** <br/> |dmtf  <br/> |사용자가 회의에 참가 한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |dmtf  <br/> |사용자가 회의를 남겨진 시간입니다.  <br/> |
|**UserRole** <br/> |nvarchar (256)  <br/> |회의에서 사용자의 역할 (예: 발표자 또는 참석자)  <br/> |
   

