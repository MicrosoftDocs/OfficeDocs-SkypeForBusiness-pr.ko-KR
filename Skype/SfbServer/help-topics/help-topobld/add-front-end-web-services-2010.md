---
title: 프론트 엔드 웹 서비스 2010 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685131"
---
# <a name="add-front-end-web-services-2010"></a>프론트 엔드 웹 서비스 2010 추가
 
기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다. 예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.
  
스탠더드 버전 서버에 대 한 내부 웹 서비스 풀의 FQDN (정규화 된 도메인 이름)을 재정의할 수 없습니다. Enterprise Edition 프런트 엔드 풀에 대 한 DNS (Domain Name System) 부하 분산을 구성 하는 경우에는 다른 내부 기본 URL (풀 FQDN과 달라 야 하며 기본 URL\<\>과 같은 경우)을 지정할 수 있습니다.
  
내부 기본 URL에서 다른 외부 기본 URL을 지정 하 여 도메인 명명을 구별할 수 있습니다. 예를 들어 내부 도메인은 contoso.net 외부 도메인 이름은 contoso.com입니다. Contoso.com 도메인 이름을 사용 하 여 외부 기본 URL을 정의 합니다. 이는 edge 배포에 대 한 역방향 프록시 서버에 중요 합니다. 외부 기본 URL 도메인 이름은 역방향 프록시의 FQDN에 대 한 도메인 이름과 동일 해야 합니다. 인스턴트 메시지 및 현재 상태에는 프런트 엔드 풀에 대 한 HTTP 액세스가 필요 합니다.
  

