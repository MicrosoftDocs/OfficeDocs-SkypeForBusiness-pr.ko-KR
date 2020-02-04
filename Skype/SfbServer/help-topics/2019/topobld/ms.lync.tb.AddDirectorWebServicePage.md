---
title: Director 웹 서비스 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: 기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.
ms.openlocfilehash: 140012c548152f9473308b3be17f95adf53e918b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703183"
---
# <a name="add-director-web-service"></a>Director 웹 서비스 추가
 
기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.
  
단일 디렉터만 배포 하는 경우 내부 웹 서비스 풀의 FQDN (정규화 된 도메인 이름)을 재정의할 수 없습니다. 디렉터 풀에 대 한 DNS (Domain Name System) 부하 분산을 구성 하는 경우에는 다른 내부 기본 URL을 지정할 수 있습니다 (예를 들어, 기본 URL\<\>이 있는 경우에는 풀 FQDN과 달라 야 함).
  
내부 기본 URL에서 다른 외부 기본 URL을 지정 하 여 도메인 명명을 구별할 수 있습니다. 예를 들어 내부 도메인은 contoso.net 외부 도메인 이름은 contoso.com입니다. Contoso.com 도메인 이름을 사용 하 여 외부 기본 URL을 정의 합니다. 이는 edge 배포에 대 한 역방향 프록시 서버에 중요 합니다. 외부 기본 URL 도메인 이름은 역방향 프록시의 FQDN에 대 한 도메인 이름과 동일 해야 합니다. 
  

