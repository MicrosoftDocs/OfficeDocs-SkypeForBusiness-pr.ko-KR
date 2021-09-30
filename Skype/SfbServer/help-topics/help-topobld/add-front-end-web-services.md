---
title: 프런트 엔드 웹 서비스 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 `https://pool01.contoso.net` URL은 `pool01.contoso.net` 입니다.
ms.openlocfilehash: 871a9266e0d64175a6e3d11978627d22d110304f
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013972"
---
# <a name="add-front-end-web-services"></a>프런트 엔드 웹 서비스 추가
 
기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 `https://pool01.contoso.net` URL은 `pool01.contoso.net` 입니다.
  
Standard Edition 서버의 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 재정의할 수 없습니다. Enterprise Edition 프런트 엔드 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 풀 FQDN(예: internal- )과 달라야 하는 다른 내부 기본 URL을 지정할 수 있습니다. \<your base URL\>
  
도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 예를 들어 내부 도메인은 이지만 외부 `contoso.net` 도메인 이름은 `contoso.com` 입니다. 도메인 이름을 사용하여 외부 기본 `contoso.com` URL을 정의합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다. 인스턴트 메시징 및 현재 상태는 프런트 엔드 풀에 HTTP 액세스가 필요합니다.
  

