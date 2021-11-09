---
title: ADAL(최신 인증)에 대한 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 이 문서에서는 ADAL(Active Directory 인증 라이브러리) 및 OAuth 2.0 기반의 최신 인증에 대해 설명합니다.
ms.openlocfilehash: 40bf87317b68e258fc6576b1ce7be7b8decc6939
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834084"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>ADAL(최신 인증)을 사용하는 비즈니스용 Skype
 
이 문서에서는 비즈니스용 Skype for 비즈니스용 Skype 서버 2015의 2016년 3월 누적 업데이트 또는 비즈니스용 Skype 서버 2019의 초기 릴리스에서 찾을 수 있는 최신 인증(ADAL(Active Directory 인증 라이브러리) 및 OAuth 2.0 기반)을 소개합니다.
  
## <a name="what-is-adal"></a>ADAL이란?

ADAL은 'Active Directory 인증 라이브러리'의 약어로, OAuth 2.0과 함께 최신 인증의 기조입니다. 이 코드 라이브러리는 보안 토큰을 통해 디렉터리의 보안 리소스를 클라이언트 응용 프로그램(예: 비즈니스용 Skype)에서 사용할 수 있도록 설계되었습니다. ADAL은 OAuth 2.0과 함께 작동하여 MFA(Multi-Factor Authentication) 및 더 많은 형태의 SAML 인증과 같은 더 많은 인증 및 권한 부여 시나리오를 사용할 수 있도록 합니다.
  
클라이언트 역할을 하는 다양한 앱은 보안 리소스에 대한 도움말을 위해 최신 인증을 활용할 수 있습니다. 이 비즈니스용 Skype 서버 이 기술은 사용자에게 리소스에 대한 적절한 수준의 권한 부여를 제공하기 위해 사내 클라이언트와 사내 서버 간에 사용됩니다.
  
ADAL 및 OAuth 2.0 기반의 최신 인증 대화에는 몇 가지 공통 요소가 있습니다.
  
- 리소스 요청을 하는 클라이언트가 있습니다. 이 경우 클라이언트는 비즈니스용 Skype.
    
- 클라이언트에 특정 수준의 액세스가 필요한 리소스가 있으며 이 리소스는 디렉터리 서비스에 의해 보호됩니다. 이 경우 리소스가 비즈니스용 Skype 서버.
    
- 즉, 사용자가 리소스에 액세스할 수 있도록 권한을 부여하는  데 전용으로 사용할 수 있는 OAuth 연결이 있습니다. (OAuth는 보다 설명적인 이름인 '서버 간' auth로도 알려져 있으며 종종 S2S로 약식으로도 알려져 있습니다.)
    
ADAL(비즈니스용 Skype 서버 최신 인증) 대화에서 비즈니스용 SKYPE 서버 R2의 ADFS 3.0을 Windows Server 2012 통신합니다. 인증은 다른 IdP(ID 공급자)를 사용하여 비즈니스용 Skype ADFS와 직접 통신하도록 구성해야 합니다. ADFS를 사용하도록 구성하지 않은 경우 ADFS 비즈니스용 Skype 서버 [설치를 완료하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))
  
ADAL은 비즈니스용 Skype 서버 2015년 3월 누적 업데이트에 포함되어 있으며, 비즈니스용 Skype 대한 2016년 3월 누적 업데이트를 설치해야 합니다. 성공적인 구성을 위해 필요합니다.  2019년 비즈니스용 Skype 서버 제품의 초기 릴리스부터 사용할 수 있습니다.
  
> [!NOTE]
> 초기 릴리스 동안에는 모든 토폴로지가 혼합된 토폴로지가 없는 경우만 사내 환경의 최신 인증이 Skype 지원됩니다. 예를 들어 환경이 전적으로 비즈니스용 Skype 서버. 이 설명은 변경될 수 있습니다. 
  
성공적인 구성을 .ps1 ADAL에서 사용하는 명령이 있는 파일 포함 PowerShell 패키지를 다운로드해야 합니다.

최신 인증을 구현하는 방법에 대한 자세한 내용은 비즈니스용 Skype: [ADAL(최신](/microsoft-365/enterprise/hybrid-modern-auth-overview) 인증)을 사용하는 비즈니스용 Skype