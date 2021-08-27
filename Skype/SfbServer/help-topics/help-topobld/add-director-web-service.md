---
title: 디렉터 웹 서비스 추가
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
ms.openlocfilehash: 4718df8fa1640aaa2e1cab080459f7fee445acc9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610795"
---
# <a name="add-director-web-service"></a>디렉터 웹 서비스 추가
 
기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다. 예를 들어 풀의 웹 서비스에 대한 전체 URL이 인 경우 기본 https://pool01.contoso.net URL은 pool01.contoso.net.
  
디렉터를 하나만 배포하는 경우 내부 웹 서비스 풀 FQDN(정규화된 도메인 이름)을 재정의할 수 없습니다. Director 풀에 대해 DNS(Domain Name System) 부하 분산을 구성하는 경우 서로 다른 내부 기본 URL(풀 FQDN과 달라야 하며 internal- 등)을 지정할 수 있습니다. \<your base URL\>
  
도메인 이름을 차별화하기 위해 내부 기본 URL과 다른 외부 기본 URL을 지정할 수 있습니다. 예를 들어 내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우 contoso.com 도메인 이름을 사용하여 외부 기본 URL을 정의합니다. 이는 에지 배포의 역방향 프록시 서버에 있어 중요합니다. 외부 기본 URL 도메인 이름은 역방향 프록시 FQDN의 도메인 이름과 같아야 합니다. 
  

