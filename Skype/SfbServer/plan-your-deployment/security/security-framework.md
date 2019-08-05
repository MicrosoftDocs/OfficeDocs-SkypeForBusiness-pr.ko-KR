---
title: 비즈니스용 Skype 서버용 보안 프레임 워크
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 이 섹션에서는 비즈니스용 Skype 서버에 대 한 보안 프레임 워크를 구성 하는 기본 요소에 대해 간략하게 설명 합니다. 이러한 요소가 함께 작동 하는 방식을 이해 하는 것은 특정 비즈니스용 Skype 서버 배포 보안에 대 한 의사 결정을 내리는 데 반드시 필요 합니다.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196829"
---
# <a name="security-framework-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 보안 프레임 워크
 
이 섹션에서는 비즈니스용 Skype 서버에 대 한 보안 프레임 워크를 구성 하는 기본 요소에 대해 간략하게 설명 합니다. 이러한 요소가 함께 작동 하는 방식을 이해 하는 것은 특정 비즈니스용 Skype 서버 배포 보안에 대 한 의사 결정을 내리는 데 반드시 필요 합니다.
  
이러한 요소는 다음과 같습니다.
  
- AD DS (Active Directory 도메인 서비스)는 사용자 계정 및 네트워크 리소스에 대해 신뢰할 수 있는 단일 백 엔드 리포지토리를 제공 합니다.
    
- RBAC (역할 기반 액세스 제어)를 사용 하 여 보안을 위해 높은 표준을 유지 하면서 관리 작업을 위임할 수 있습니다.
    
- PKI (공개 키 인프라)는 신뢰할 수 있는 Ca (인증 기관)에서 발급 한 인증서를 사용 하 여 서버를 인증 하 고 데이터 무결성을 보장 합니다.
    
- TLS (전송 계층 보안), https over SSL (HTTPS) 및 상호 TLS (MTLS)로 끝점 인증 및 IM 암호화를 사용 하도록 설정 합니다. 지점간 오디오, 비디오 및 응용 프로그램 공유 스트림은 보안 실시간 전송 프로토콜 (SRTP)을 사용 하 여 암호화 됩니다.
    
- 가능 하면 사용자 인증을 위한 업계 표준 프로토콜입니다.
    
- Windows PowerShell은 사용자가 스크립트를 쉽게 실행할 수 없도록 기본적으로 활성화 된 보안 기능을 제공 합니다.
    
이러한 기본 보안 요소는 신뢰할 수 있는 사용자, 서버, 연결, 작업을 정의 하 여 비즈니스용 Skype 서버를 위한 안전한 토대를 보장 하는 데 도움을 줍니다.
  
## <a name="in-this-section"></a>이 섹션의

이 섹션의 항목에서는 이러한 기본 요소가 각각의 비즈니스용 Skype 서버 인프라의 보안을 강화 하는 방법에 대해 설명 합니다.
  
- [비즈니스용 Skype 서버용 Active Directory 도메인 서비스](active-directory-domain-services.md)
    
- [비즈니스용 Skype 서버용에 대 한 RBAC (역할 기반 액세스 제어)](role-based-access-control-rbac.md)
    
- [비즈니스용 Skype 서버용 공개 키 인프라](public-key-infrastructure-for-skype.md)
    
- [비즈니스용 Skype 서버용 TLS 및 MTLS](tls-and-mtls.md)
    
- [비즈니스용 Skype 서버 암호화](encryption.md)
    
- [비즈니스용 Skype 서버에 대 한 사용자 및 클라이언트 인증](user-and-client-authentication.md)
    
- [Windows PowerShell 및 비즈니스용 Skype 서버 관리 도구](management-tools.md)
    

