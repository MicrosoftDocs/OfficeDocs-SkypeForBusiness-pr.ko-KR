---
title: 디렉터 일반 설정 확장기
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
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 다음 섹션에서 기존 디렉터의 설정을 편집할 수 있습니다.
ms.openlocfilehash: b7478779e54a7860726ae967eb1e203625c8b17b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835338"
---
# <a name="director-general-settings-expander"></a>디렉터 일반 설정 확장기
 
다음 섹션에서 기존 디렉터의 설정을 편집할 수 있습니다.
  
- 일반 설정
    
- 웹 서비스
    


## <a name="general-settings"></a>일반 설정

디렉터 풀의 FQDN(정규화된 도메인 이름). 값을 변경하려면 서버의 FQDN을 편집합니다. 새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.
  
**연결** 에서는 다음을 편집하거나 지정할 수 있습니다.
  
디렉터 풀에서 사용할 파일 공유. 토폴로지 작성기에서 이미 정의된 기존 파일 공유를 선택하거나 새로 만들기를 클릭하여 새 파일 공유 정의를 만들 수 있습니다. 
  
모니터링 SQL Server 저장소
  
> [!IMPORTANT]
> 새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다. 새 파일 공유를 만드는 경우 지정한 서버에서 파일 공유를 만들어야 합니다. 
  
## <a name="web-services"></a>웹 서비스

디렉터 풀의 웹 서비스에 대한 추가 설정을 편집하거나 지정하려면 내부 웹 서비스 및 외부 웹 서비스의 설정을 수정하거나 지정하면 됩니다.
  
**내부 웹 서비스** 에 대해 다음을 지정할 수 있습니다.
  
> [!CAUTION]
> 프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우 외부 웹 서비스 FQDN은 고유해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 pool01.contoso.com 다른 프런트  엔드 풀 또는 프런트 엔드 pool01.contoso.com 사용할 수 없습니다.  또한 Director를 배포하는 경우 모든 Director 또는 Director 풀에 대해 정의된 외부 웹 서비스 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버뿐만 아니라 다른 모든 Director 또는 Director 풀에서 고유해야 합니다. 내부 웹 서비스를 자체 정의 FQDN으로 다시 정의하려면 각 FQDN이 다른 프런트 엔드 풀, Director 또는 Director 풀과 고유해야 합니다.
  
FQDN 다시 정의를 선택하면 풀의 내부 웹 서비스 ID에 대해 다른 FQDN을 지정할 수 있습니다. 기본적으로 디렉터 풀에 정의된 현재 풀 이름이 설정됩니다.
  
배포에 필요한 HTTP 및 HTTPS용 수신 대기 포트 및 게시된 포트를 지정할 수 있습니다. 기본 설정(HTTP의 경우 포트 80, HTTPS의 경우 포트 443)은 가장 일반적인 설정이므로 조직 내에 특정 요구 사항이 있거나 인프라 디자인에 필요한 경우가 아니면 기본 설정을 변경할 필요가 없습니다.
  
**외부 웹 서비스** 에 대해 다음을 지정할 수 있습니다.
  
외부 웹 서비스의 FQDN을 정의할 수 있습니다. 여기에 지정되는 FQDN은 일반적으로 외부 연결 요구 사항(예: 역방향 프록시)에 따라 정의됩니다.
  
배포에 필요한 HTTP 및 HTTPS용 수신 대기 포트 및 게시된 포트를 지정할 수 있습니다. 처음에는 HTTP의 경우 포트 8080, HTTPS의 경우 포트 4443이 기본 설정으로 정의됩니다. 수신 대기 포트의 이러한 설정은 역방향 프록시 및 외부 네트워크 요구 사항에 따라 변경할 수 있습니다. 게시된 포트는 기본적으로 HTTP의 경우 포트 80, HTTPS의 경우 포트 443으로 설정됩니다. 이러한 값에 따라 디렉터 풀 또는 디렉터 서버에서 들어오는 요청을 수신 대기할 포트가 결정됩니다. 일반적으로 풀에서 포트 요구 사항이 충돌하지 않는 한, 이러한 설정을 변경할 필요는 없습니다. 게시된 내부 및 외부 포트에서 동일한 포트 값을 사용하는 것은 이미 예상되는 상황입니다. 즉, 포트가 충돌하는 것이 아닙니다.
  

