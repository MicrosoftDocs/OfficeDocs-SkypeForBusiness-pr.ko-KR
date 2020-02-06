---
title: 비즈니스용 Skype 서버 2015의 FocusJoinsAndLeaves 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 이 테이블의 각 레코드에는 한 회의에 대 한 사용자의 참가 및 탈퇴 정보에 대 한 CDR 정보가 포함 됩니다. 각 회의는 사용자가 회의에 참가 하 고 떠날 때마다이 테이블에 하나의 레코드로 표시 됩니다.
ms.openlocfilehash: ac5e2b7316dd7d3477d76675d3a3960154b90f35
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815186"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 FocusJoinsAndLeaves 테이블
 
이 테이블의 각 레코드에는 한 회의에 대 한 사용자의 참가 및 탈퇴 정보에 대 한 CDR 정보가 포함 됩니다. 각 회의는 사용자가 회의에 참가 하 고 떠날 때마다이 테이블에 하나의 레코드로 표시 됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |컨퍼런스 인스턴스 시간. 회의 인스턴스를 고유 하 게 식별 하기 위해 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |회의 인스턴스를 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요. <br/> |
|**DialogSessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**UserId** <br/> |int  <br/> |외부  <br/> |이 사용자를 식별 하는 고유 번호로, [Users 테이블](users.md)에서 참조 합니다.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 한 경우 **UserInstance** 는 사용자/장치 조합을 고유 하 게 식별 하는 데 사용 됩니다. <br/> |
|**IsUserInternal** <br/> |다소  <br/> | <br/> |사용자가 내부에서 로그온 했는지 여부  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |발표자 또는 참석자와 같이 회의에서이 사용자의 역할입니다.  <br/> |
|**UserJoinTime** <br/> |dmtf  <br/> | <br/> |이 사용자가 회의에 참가 한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |dmtf  <br/> | <br/> |이 사용자가 회의를 떠난 시간입니다.  <br/> |
|**ClientVerId** <br/> |int  <br/> |외부  <br/> |[비즈니스용 Skype 서버 2015의 Clientversions 테이블로](clientversions.md)참조 되는 사용자 클라이언트 소프트웨어의 버전입니다.  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||회의에 사용 되는 끝점의 전역 고유 식별자 (GUID)입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   

