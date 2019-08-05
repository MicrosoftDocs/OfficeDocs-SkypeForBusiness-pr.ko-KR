---
title: 비즈니스용 Skype를 사용 하 여 최신 인증 (ADAL) 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 이 문서에서는 ADAL (Active Directory Authentication Library) 및 OAuth 2.0을 기반으로 하는 최신 인증에 대해 설명 합니다.
ms.openlocfilehash: c984e2468e1735a46c5246806afc57dd67327990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196872"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>비즈니스용 Skype에서 최신 인증 (ADAL)을 사용 하는 방법
 
이 문서에는 비즈니스용 Skype for Business Server 2015 또는 초기 기간에 대해 3 월 2016 누적 업데이트에서 찾을 수 있는 최신 인증 (Active Directory Authentication Library (ADAL) 및 OAuth 2.0에 기반을 둔)이 도입 되었습니다. 비즈니스용 Skype 서버 2019 릴리스.
  
## <a name="what-is-adal"></a>ADAL 이란?

ADAL은 ' Active Directory Authentication Library '의 머리글자어 이며, OAuth 2.0와 함께 최신 인증의 underpinning입니다. 이 코드 라이브러리는 보안 토큰을 통해 디렉터리의 보안 리소스를 클라이언트 응용 프로그램 (비즈니스용 Skype 등)에서 사용할 수 있도록 설계 되었습니다. ADAL은 OAuth 2.0와 함께 작동 하 여 여러 가지 인증 및 권한 부여 시나리오 (예: MFA)와 더 많은 유형의 SAML 인증을 사용 하도록 설정 합니다.
  
클라이언트 역할을 하는 다양 한 앱에서 최신 인증을 활용 하 여 보안 리소스를 얻을 수 있습니다. 비즈니스용 Skype Server에서이 기술은 사용자에 게 리소스에 대 한 적절 한 수준의 권한을 부여 하기 위해 온-프레미스 클라이언트와 온-프레미스 서버 사이에 사용 됩니다.
  
최신 인증 대화 (ADAL 및 OAuth 2.0에 기반 하는)에는 몇 가지 공통 요소가 있습니다.
  
- 리소스 요청을 하는 클라이언트가 있는 경우,이 경우 클라이언트는 비즈니스용 Skype입니다.
    
- 클라이언트에 게 특정 수준의 액세스 권한이 필요 하며,이 리소스는 디렉터리 서비스에 의해 보호 되며,이 경우 비즈니스용 Skype 서버용 리소스입니다.
    
- OAuth 연결, 즉 사용자에 게 리소스에 대 한 액세스 *권한을 부여* 하는 전용 연결이 있습니다. (OAuth는 더 설명적인 이름 ' 서버 대 서버 ' 인증으로 알려져 있으며 일반적으로 S2S로 간략 한 것입니다.)
    
ADAL (비즈니스용 Skype Server 인증) 대화에서 비즈니스용 Skype 서버는 ADFS를 통해 통신 합니다 (Windows Server 2012 R2의 ADFS 3.0). 인증은 일부 다른 Id 공급자 (IdP)를 사용 하 여 발생할 수 있지만, ADFS와 통신 하려면 비즈니스용 Skype 서버를 구성 해야 합니다. 비즈니스용 Skype 서버에서 작동 하도록 ADFS를 구성 하지 않은 경우에는 [adfs 설치](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)를 완료 하세요.
  
ADAL은 비즈니스용 Skype Server 2015에 대 한 3 월 2016 누적 업데이트에 포함 되어 있으며, 비즈니스용 Skype에 대 한 3 월 **** 2016 누적 업데이트를 설치 하 고 성공적인 구성을 위해 필요 합니다. 비즈니스용 Skype 서버 2019의 경우 제품의 최초 릴리스에서 사용할 수 있습니다.
  
> [!NOTE]
> 초기 릴리스에서는 온-프레미스 환경의 최신 인증은 관련 된 혼합 Skype 토폴로지가 없는 경우에만 지원 됩니다. 예를 들어, 환경이 비즈니스용 Skype 서버용 일 경우에만 사용할 수 있습니다. 이 문장은 변경 될 수 있습니다. 
  
ADAL에서 사용 하는 명령이 포함 된 ps1 파일을 포함 하는 PowerShell 패키지는 성공적인 구성을 위해 다운로드 해야 합니다.

비즈니스용 Skype에서 최신 인증을 구현 하는 방법에 대 한 자세한 내용은 비즈니스용 [skype에서 최신 인증 (ADAL)을 사용 하는 방법](../../manage/authentication/use-adal.md) 을 참조 하세요.
