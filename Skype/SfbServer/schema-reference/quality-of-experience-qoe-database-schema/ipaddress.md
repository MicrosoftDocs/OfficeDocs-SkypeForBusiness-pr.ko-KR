---
title: IPAddress 테이블
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
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 테이블은 QoE(체감 품질) 데이터베이스의 모든 위치에서 사용되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: db9405a05335974456f77d8117f9e3f64e9832750c3d2c23441a5a587ca91d7a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305100"
---
# <a name="ipaddress-table"></a>IPAddress 테이블
 
IPAddress 테이블은 QoE(체감 품질) 데이터베이스의 모든 위치에서 사용되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |지정된 IP 주소의 고유 식별자입니다.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Unique  <br/> |IpAddressKey에 매핑되는 고유 IP 주소(예: 189.168.1.1)입니다. IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
   

