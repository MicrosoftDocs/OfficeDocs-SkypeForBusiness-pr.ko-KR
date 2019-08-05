---
title: 비즈니스용 Skype 서버에 대 한 사용자 및 클라이언트 인증
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 신뢰할 수 있는 사용자는 비즈니스용 Skype 서버의 신뢰할 수 있는 서버에서 자격 증명을 인증 한 것입니다. 이 서버는 일반적으로 스탠더드 버전 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다. 비즈니스용 Skype Server는 Active Directory 도메인 서비스를 사용자 자격 증명의 단일 신뢰할 수 있는 백 엔드 리포지토리로 사용 합니다.
ms.openlocfilehash: 35d1c6861ba8863e308939997fd802d4abcea404
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196824"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 사용자 및 클라이언트 인증
 
신뢰할 수 있는 사용자는 비즈니스용 Skype 서버의 신뢰할 수 있는 서버에서 자격 증명을 인증 한 것입니다. 이 서버는 일반적으로 스탠더드 버전 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다. 비즈니스용 Skype Server는 Active Directory 도메인 서비스를 사용자 자격 증명의 단일 신뢰할 수 있는 백 엔드 리포지토리로 사용 합니다.
  
인증은 신뢰할 수 있는 서버에 대 한 사용자 자격 증명을 제공 하는 것입니다. 비즈니스용 Skype 서버는 사용자의 상태와 위치에 따라 다음 인증 프로토콜을 사용 합니다.
  
- Active Directory 자격 증명을 사용 하는 내부 사용자 용 **MIT Kerberos 버전 5 보안 프로토콜** 입니다. Kerberos에는 Active Directory 도메인 서비스에 대 한 클라이언트 연결이 필요 하며,이 때문에 회사 방화벽 외부에서 클라이언트를 인증 하는 데 사용할 수 없습니다.
    
- 회사 방화벽 외부의 끝점에서 연결 하는 Active Directory 자격 증명이 있는 사용자에 대 한 **NTLM 프로토콜** 입니다. 액세스에 지 서비스가 로그인 요청을 디렉터 (있는 경우) 또는 프런트 엔드 서버 (인증)에 게 전달 합니다. 액세스에 지 서비스 자체는 인증을 수행 하지 않습니다.
    
    > [!NOTE]
    > NTLM 프로토콜은 Kerberos 보다 약한 공격 보호 기능을 제공 하므로 일부 조직에서는 NTLM의 사용을 최소화 합니다. 따라서 비즈니스용 Skype 서버에 대 한 액세스가 VPN 또는 DirectAccess 연결을 통해 연결 된 내부 또는 클라이언트로 제한 될 수 있습니다. 
  
- 익명 사용자 라고 불리는 **다이제스트 프로토콜** 입니다. 익명 사용자는 Active Directory 자격 증명을 인식할 수 없지만 온-프레미스 회의에 초대 하 고 유효한 컨퍼런스 키를 소유 하는 사용자 외부입니다. 다이제스트 인증은 다른 클라이언트 조작에는 사용 되지 않습니다.
    
비즈니스용 Skype 서버 인증은 다음 두 단계로 구성 됩니다.
  
1. 클라이언트와 서버 간에 보안 연결이 설정 됩니다.
    
2. 클라이언트와 서버는 기존 보안 연결을 사용 하 여 보내는 메시지에 서명 하 고 자신이 받은 메시지를 확인 합니다. 서버에서 인증을 사용 하도록 설정 되어 있는 경우에는 클라이언트의 인증 되지 않은 메시지가 수락 되지 않습니다.
    
사용자 신뢰는 사용자 id 자체가 아니라 사용자 로부터 들어오는 각 메시지에 연결 됩니다. 서버가 각 메시지에 유효한 사용자 자격 증명을 검사 합니다. 사용자 자격 증명이 유효 하 게 표시 되는 경우에는 해당 메시지가 첫 번째 서버 에서만 수신 되 고 신뢰 된 서버 클라우드의 다른 모든 서버에서 unchallenged 됩니다.
  
페더레이션 파트너가 발급 하는 유효한 자격 증명을 사용 하는 사용자는 신뢰할 수 있지만 필요에 따라 추가 제약 조건에서 내부 사용자에 게 적용 되는 모든 범위의 권한을 제공 하지 못하게 됩니다.
  
또한 얼음 및 선반 가공 프로토콜은 IETF RFC에서 설명한 대로 다이제스트 챌린지를 사용 합니다.
  
클라이언트 인증서는 비즈니스용 Skype 서버에서 사용자를 인증 하는 대체 방법을 제공 합니다. 사용자 이름 및 암호를 제공 하는 대신, 사용자는 인증서와 암호화 챌린지를 해결 하는 데 필요한 인증서에 해당 하는 개인 키를가지고 있습니다. (이 인증서에는 사용자를 식별 하는 주체 이름 또는 주체 대체 이름이 있어야 하며, 비즈니스용 Skype Server를 실행 하는 서버에서 신뢰 하는 루트 CA가 발급 해야 하며, 인증서의 유효 기간 내에 있어야 하며, 해지 되지 않았습니다.) 인증을 받기 위해 사용자는 PIN (개인 식별 번호)을 입력 하기만 하면 됩니다. 인증서는 사용자 이름 및 암호를 입력 하는 것이 어려운 전화, 휴대 전화 및 기타 장치에 특히 유용 합니다.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>ASP .NET 4.5으로 인 한 암호화 요구 사항 

비즈니스용 Skype Server 2015 CU5의 경우 ASP.NET 4.6에는 AES가 지원 되지 않으며,이로 인해 Skype 모임 앱이 시작 되지 않을 수 있습니다. 클라이언트가 컴퓨터 키 유효성 검사 값으로 AES를 사용 하는 경우에는 IIS의 Skype Meeting App site level에서 컴퓨터 키 값을 SHA-1 또는 다른 지원 되는 알고리즘으로 다시 설정 해야 합니다. 필요한 경우 [IIS 8.0 ASP.NET 구성 관리](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) 에 대 한 지침을 참조 하세요.
  
기타 지원 되는 값은 다음과 같습니다.
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  AES, 3DES 및 MD5 값은 ASP.NET 4에 비해 더 이상 사용할 수 없습니다. [ASP.NET 4.5, pt. 2의 암호화 개선](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) 사항에 대 한 세부 정보가 더 있습니다.
  
