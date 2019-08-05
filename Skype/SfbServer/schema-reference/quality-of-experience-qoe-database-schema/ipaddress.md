---
title: IPAddress 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 테이블은 경력 데이터베이스의 다른 곳에 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196562"
---
# <a name="ipaddress-table"></a>IPAddress 테이블
 
IPAddress 테이블은 경력 데이터베이스의 다른 곳에 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |주요한  <br/> |지정 된 IP 주소에 대 한 고유 식별자입니다.  <br/> |
|**IPAddress** <br/> |varchar (50)  <br/> |독특한  <br/> |IpAddressKey에 매핑되는 고유 IP 주소 (예: 189.168.1.1)입니다. IPv4 또는 IPv6 주소 일 수 있습니다.  <br/> |
   

