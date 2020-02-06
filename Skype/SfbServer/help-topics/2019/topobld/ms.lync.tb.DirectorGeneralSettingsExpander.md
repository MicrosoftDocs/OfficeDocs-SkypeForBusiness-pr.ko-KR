---
title: Director 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 기존 감독에 대 한 설정을 편집 하려면 다음 섹션이 표시 됩니다.
ms.openlocfilehash: ffdfd169095175346a89eb6d6d001161bec0f465
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793856"
---
# <a name="director-general-settings-expander"></a>Director 일반 설정 확장기
 
기존 감독에 대 한 설정을 편집 하려면 다음 섹션이 표시 됩니다.
  
- 일반 설정
    
- 웹 서비스
    

## <a name="general-settings"></a>일반 설정

디렉터 풀의 FQDN (정규화 된 도메인 이름)입니다. 값을 변경하려면 서버의 FQDN을 편집합니다. 새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.
  
**연결**에서는 다음을 편집하거나 지정할 수 있습니다.
  
사용할 디렉터 풀에 대 한 파일 공유입니다. 이미 토폴로지 작성기에 정의 된 기존 파일 공유를 선택 하거나 **새로** 만들기를 클릭 하 여 새 파일 공유 정의를 만듭니다.
  
SQL Server 저장소 모니터링.
  
> [!IMPORTANT]
> 새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다. 새 파일 공유를 만든 경우 지정 하는 서버에서 파일 공유를 만들어야 합니다. 
  
## <a name="web-services"></a>웹 서비스

디렉터 풀의 웹 서비스에 대 한 추가 설정을 편집 하거나 지정 하려면 내부 웹 서비스 및 외부 웹 서비스에서 설정을 수정 하거나 지정 합니다.
  
**내부 웹 서비스** 의 경우 다음을 지정할 수 있습니다.
  
> [!CAUTION]
> 프런트 엔드 풀 또는 프런트 엔드 서버를 두 개 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 **pool01.contoso.com**로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 **pool01.contoso.com** 를 사용할 수 없습니다. 디렉터를 배포 하는 경우 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프론트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 모든 디렉터 또는 디렉터 풀에서 고유 해야 합니다. 내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.
  
FQDN 다시 정의를 선택하면 풀의 내부 웹 서비스 ID에 대해 다른 FQDN을 지정할 수 있습니다. 기본적으로이 설정은 디렉터 풀에 대해 정의 된 현재 풀 이름입니다.
  
배포에 필요한 HTTP 및 HTTPS에 대 한 수신 대기 및 게시 된 포트를 지정할 수 있습니다. HTTP 및 HTTPS의 포트 443에 대 한 기본 80 설정은 가장 일반적인 설정이 며, 조직 및 인프라 디자인 내에 특정 요구 사항이 없다면 일반적으로 변경 하지 않아도 됩니다.
  
**외부 웹 서비스**의 경우 다음을 지정할 수 있습니다.
  
외부 웹 서비스의 FQDN을 정의할 수 있습니다. 여기에 지정되는 FQDN은 일반적으로 외부 연결 요구 사항(예: 역방향 프록시)에 따라 정의됩니다.
  
배포에 필요한 HTTP 및 HTTPS에 대 한 수신 대기 및 게시 된 포트를 지정할 수 있습니다. 처음에는 HTTP의 경우 포트 8080, HTTPS의 경우 포트 4443이 기본 설정으로 정의됩니다. 수신 대기 포트의 이러한 설정은 역방향 프록시 및 외부 네트워크 요구 사항에 따라 변경할 수 있습니다. 게시된 포트는 기본적으로 HTTP의 경우 포트 80, HTTPS의 경우 포트 443으로 설정됩니다. 이러한 값은 디렉터 풀 또는 디렉터 서버가 들어오는 요청을 수신 대기 하는 포트를 결정 합니다. 일반적으로 풀의 포트 요구 사항 충돌이 없는 경우에는 변경할 필요가 없습니다. 동일한 포트 값을 사용 하는 내부 및 외부 게시 포트가 필요 합니다. 즉, 포트가 충돌하는 것이 아닙니다.
  

