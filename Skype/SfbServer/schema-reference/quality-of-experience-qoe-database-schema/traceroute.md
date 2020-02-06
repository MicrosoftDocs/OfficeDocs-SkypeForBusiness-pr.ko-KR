---
title: TraceRoute 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 테이블에는 통화의 라우팅 정보가 포함 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805116"
---
# <a name="traceroute-table"></a>TraceRoute 테이블
 
TraceRoute 테이블에는 통화의 라우팅 정보가 포함 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |통화가 시작 된 날짜 및 시간입니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |기본, 외래  <br/> |같은 날짜와 동시에 시작 했을 수 있는 여러 통화를 구분 하는 데 사용 되는 고유 식별자입니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |기본, 외래  <br/> |통화에 사용 되는 영상 회선 유형을 나타냅니다. 사용 가능한 값은 다음과 같습니다.  <br/> 0-오디오  <br/> 1-영상 통화  <br/> 2-파노라마 비디오  <br/> 3-애플리케이션/데스크톱 공유  <br/> |
|**FromCaller** <br/> |다소  <br/> |주요한  <br/> |호출을 배치한 끝점입니다.  <br/> |
|**홉당** <br/> |int  <br/> ||네트워크 홉/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |외부  <br/> |IP 주소에 대 한 고유 식별자입니다. IP 주소 정보는 [IPAddress 테이블](ipaddress.md)에 저장 됩니다.  <br/> |
|**RTT** <br/> |int  <br/> ||왕복 시간입니다. 왕복 시간은 음성 패킷이 목적지에 도달 하는 데 걸리는 시간을 측정 한 다음 받은 알림을 다시 전송 합니다.  <br/> |
   

