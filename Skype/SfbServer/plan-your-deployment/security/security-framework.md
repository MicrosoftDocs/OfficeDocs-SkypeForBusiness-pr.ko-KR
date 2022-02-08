---
title: 보안 프레임워크를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 이 섹션에서는 보안 프레임워크를 구성하는 기본 요소에 대한 개요를 비즈니스용 Skype 서버. 이러한 요소가 함께 작동되는 방식에 대한 이해는 특정 구성 요소 배포의 보안에 대한 정보를 비즈니스용 Skype 서버 중요합니다.
ms.openlocfilehash: 927b51fca298d665e45597d943bbb8cbd3e2a2ac
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394970"
---
# <a name="security-framework-for-skype-for-business-server"></a>보안 프레임워크를 비즈니스용 Skype 서버
 
이 섹션에서는 보안 프레임워크를 구성하는 기본 요소에 대한 개요를 비즈니스용 Skype 서버. 이러한 요소가 함께 작동되는 방식에 대한 이해는 특정 구성 요소 배포의 보안에 대한 정보를 비즈니스용 Skype 서버 중요합니다.
  
이러한 요소는 다음과 같습니다.
  
- AD DS(Active Directory 도메인 서비스)는 사용자 계정 및 네트워크 리소스에 대해 신뢰할 수 있는 단일 백 엔드 리포지토리를 제공합니다.
    
- Role-Based(액세스 제어)를 사용하면 높은 보안 표준을 유지하면서 관리 작업을 위임할 수 있습니다.
    
- PKI(공개 키 인프라)는 신뢰할 수 있는 CAS(인증 기관)에서 발급한 인증서를 사용하여 서버를 인증하고 데이터 무결성을 보장합니다.
    
- TLS(전송 계층 보안), HTTPS over SSL(HTTPS) 및 MTLS(상호 TLS)를 통해 끝점 인증 및 IM 암호화를 사용할 수 있습니다. 지점 대 지점 오디오, 비디오 및 응용 프로그램 공유 스트림은 SRTP(Secure Real-Time 전송 프로토콜)를 사용하여 암호화됩니다.
    
- 가능한 경우 사용자 인증을 위한 업계 표준 프로토콜입니다.
    
- Windows PowerShell 사용자가 스크립트를 쉽게 또는 무의미하게 실행할 수 없는 보안 기능을 기본적으로 제공합니다.
    
이러한 기본 보안 요소는 함께 작동하여 신뢰할 수 있는 사용자, 서버, 연결 및 작업을 정의하여 보안 기반을 비즈니스용 Skype 서버.
  
## <a name="in-this-section"></a>이 섹션의 내용

이 섹션의 항목에서는 이러한 각 기본 요소가 기본 인프라의 보안을 향상시키는 비즈니스용 Skype 서버 설명합니다.
  
- [Active Directory Domain Services for 비즈니스용 Skype 서버](active-directory-domain-services.md)
    
- [사용자용 RBAC(역할 기반 액세스 제어) 비즈니스용 Skype 서버](role-based-access-control-rbac.md)
    
- [관리용 공개 키 비즈니스용 Skype 서버](public-key-infrastructure-for-skype.md)
    
- [TLS 및 MTLS를 비즈니스용 Skype 서버](tls-and-mtls.md)
    
- [암호화를 비즈니스용 Skype 서버](encryption.md)
    
- [사용자 및 클라이언트 인증을 비즈니스용 Skype 서버](user-and-client-authentication.md)
    
- [Windows PowerShell 및 비즈니스용 Skype 서버 도구](management-tools.md)
    

