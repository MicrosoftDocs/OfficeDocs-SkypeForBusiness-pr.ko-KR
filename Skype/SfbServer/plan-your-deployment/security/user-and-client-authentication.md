---
title: 사용자 및 클라이언트 인증을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 신뢰할 수 있는 사용자는 자격 증명이 해당 사용자의 신뢰할 수 있는 서버에서 인증된 사용자 비즈니스용 Skype 서버. 이 서버는 일반적으로 Standard Edition 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다. 비즈니스용 Skype 서버 Active Directory 도메인 서비스를 사용자 자격 증명의 신뢰할 수 있는 단일 백 엔드 리포지토리로 사용하게 됩니다.
ms.openlocfilehash: d256efdf69afce16a06b3b055a9446b29deb7cb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737644"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>사용자 및 클라이언트 인증을 비즈니스용 Skype 서버
 
신뢰할 수 있는 사용자는 자격 증명이 해당 사용자의 신뢰할 수 있는 서버에서 인증된 사용자 비즈니스용 Skype 서버. 이 서버는 일반적으로 Standard Edition 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다. 비즈니스용 Skype 서버 Active Directory 도메인 서비스를 사용자 자격 증명의 신뢰할 수 있는 단일 백 엔드 리포지토리로 사용하게 됩니다.
  
인증은 트러스트된 서버에 대한 사용자 자격 증명을 제공하는 과정입니다. 비즈니스용 Skype 서버 상태 및 위치에 따라 다음 인증 프로토콜을 사용합니다.
  
- Active Directory 자격 증명이 있는 내부 사용자를 위한 **MIT Kerberos 버전 5 보안 프로토콜**. Kerberos를 사용하려면 클라이언트가 Active Directory 도메인 서비스에 연결해야 하므로, 회사 방화벽 외부의 클라이언트를 인증하는 데는 Kerberos를 사용할 수 없습니다.
    
- 회사 방화벽 외부의 끝점에서 연결하며 Active Directory 자격 증명이 있는 사용자를 위한 **NTLM 프로토콜**. 액세스 에지 서비스는 인증을 위해 로그온 요청을 디렉터(있는 경우) 또는 프런트 엔드 서버로 전달합니다. 액세스 에지 서비스 자체는 인증을 수행하지 않습니다.
    
    > [!NOTE]
    > NTLM 프로토콜은 Kerberos보다 공격 보호 수준이 낮으므로 일부 조직에서는 NTLM 사용을 최소화합니다. 따라서 VPN 또는 비즈니스용 Skype 서버 연결에 연결된 내부 또는 클라이언트로 액세스가 제한될 수 있습니다. 
  
- 익명 사용자를 위한 **다이제스트 프로토콜**. 익명 사용자는 인식할 수 있는 Active Directory 자격 증명을 가지고 있지는 않지만 온-프레미스 전화 회의에 초대를 받았으며 유효한 전화 회의 키를 소유한 외부 사용자입니다. 다른 클라이언트 상호 작용에는 다이제스트 인증이 사용되지 않습니다.
    
비즈니스용 Skype 서버 인증은 다음 두 단계로 구성됩니다.
  
1. 클라이언트와 서버 사이에 보안 연결이 설정됩니다.
    
2. 클라이언트 및 서버가 기존 보안 연결을 사용하여 보내는 메시지에 서명하고 받는 메시지를 확인합니다. 서버에서 인증이 활성화된 경우 클라이언트에서 보낸 인증되지 않은 메시지는 허용되지 않습니다.
    
사용자 트러스트는 사용자 ID가 아니라 사용자가 생성한 각 메시지에 첨부됩니다. 서버에서는 각 메시지에 올바른 사용자 자격 증명이 있는지 확인합니다. 사용자 자격 증명이 유효하면 메시지를 받는 첫 번째 서버뿐만 아니라 트러스트된 서버 집단의 다른 모든 서버에서도 메시지가 바로 전달됩니다.
  
페더레이션 파트너에서 발급한 유효한 자격 증명이 있는 사용자는 트러스트되지만, 필요한 경우에는 추가적인 제한이 적용되므로 내부 사용자에게 제공되는 전체 권한을 사용할 수 없습니다.
  
ICE 및 TURN 프로토콜 역시 IETF TURN RFC에 설명되어 있는 것처럼 다이제스트 방식을 사용합니다.
  
클라이언트 인증서는 클라이언트 인증서를 통해 사용자를 인증할 수 있는 대체 비즈니스용 Skype 서버. 사용자 이름 및 암호를 제공하는 대신 사용자가 암호화 시도를 확인하는 데 필요한 인증서 및 해당 인증서에 따른 개인 키를 사용할 수 있습니다. (이 인증서에는 사용자를 식별하는 주체 이름 또는 주체 대체 이름이 있어야 합니다. 이 인증서는 비즈니스용 Skype 서버 실행 서버에서 신뢰하는 루트 CA에서 발급되어야 합니다. 인증서의 유효 기간 내에 있으며 해지되지 않은 것입니다.) 인증을 위해 사용자는 PIN(개인 식별 번호)만 입력하면 됩니다. 인증서는 사용자 이름과 암호를 입력하기 어려운 전화, 휴대폰 및 기타 장치에 특히 유용합니다.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>ASP.NET 4.5로 인한 암호화 요구 사항 

2015년 비즈니스용 Skype 서버 현재 AES는 ASP.NET 4.6에서 지원되지 않습니다. 이로 인해 Skype 모임 앱이 시작되지 않을 수 있습니다. 클라이언트가 AES를 컴퓨터 키 유효성 검사 값으로 사용하는 경우 IIS의 Skype 모임 앱 사이트 수준에서 컴퓨터 키 값을 SHA-1 또는 다른 지원 알고리즘으로 다시 설정해야 합니다. 필요한 경우 [IIS 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) ASP.NET 구성 관리를 참조하세요.
  
지원되는 다른 값은 같습니다.
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  AES, 3DES 및 MD5 값은 한 번 ASP.NET 4에 있는 경우 더 이상 허용되지 않습니다. [암호화 개선된 ASP.NET 4.5, pt. 2에](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) 더 많은 세부 정보가 있습니다.
