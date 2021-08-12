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
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
ms.openlocfilehash: b82cc8383efc32a92b46b798503a7780df82aad8c235c3d75561f895e13cdc02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314494"
---
# <a name="add-front-end-web-services"></a>프런트 엔드 웹 서비스 추가
 
기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
  
Standard Edition 서버의 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 재정의할 수 없습니다. Enterprise Edition 프런트 엔드 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 풀 FQDN(예: internal- )과 달라야 하는 다른 내부 기본 URL을 지정할 수 있습니다. \<your base URL\>
  
도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 예를 들어 내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우 contoso.com 도메인 이름을 사용하여 외부 기본 URL을 정의합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다. 인스턴트 메시징 및 현재 상태를 사용하려면 프런트 엔드 풀에 대한 HTTP 액세스가 필요합니다.
  

