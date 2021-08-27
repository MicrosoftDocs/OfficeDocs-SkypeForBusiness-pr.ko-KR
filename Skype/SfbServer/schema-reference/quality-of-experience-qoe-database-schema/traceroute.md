---
title: TraceRoute 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 테이블에는 통화의 라우팅 정보가 포함되어 있습니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 2cecfb0fe941404668d6eedd7c146fdc92aaadd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578562"
---
# <a name="traceroute-table"></a>TraceRoute 테이블
 
TraceRoute 테이블에는 통화의 라우팅 정보가 포함되어 있습니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |통화가 시작된 날짜 및 시간입니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |같은 날짜와 동시에 시작될 수 있는 여러 통화를 구분하는 데 사용되는 고유 식별자입니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary, Foreign  <br/> |통화에서 사용되는 비디오 라인의 유형을 나타냅니다. 허용되는 값은 다음과 같습니다.  <br/> 0 - 오디오  <br/> 1 - 비디오  <br/> 2 - 파노라마 비디오  <br/> 3 - 응용 프로그램/데스크톱 공유  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |통화를 시작한 끝점입니다.  <br/> |
|**홉** <br/> |int  <br/> ||네트워크 홉/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |외계인  <br/> |IP 주소의 고유 식별자입니다. IP 주소 정보는 [IPAddress 테이블에 저장됩니다.](ipaddress.md)  <br/> |
|**RTT** <br/> |int  <br/> ||왕복 시간입니다. 왕복 시간은 음성 패킷이 대상에 도달한 다음 수신된 알림을 다시 보내는 데 걸리는 시간을 측정합니다.  <br/> |
   

