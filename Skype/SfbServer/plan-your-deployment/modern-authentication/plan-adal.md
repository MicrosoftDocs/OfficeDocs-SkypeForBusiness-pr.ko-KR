---
title: 비즈니스용 Skype를 사용하는 ADAL(최신 인증) 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 이 문서에서는 ADAL(Active Directory 인증 라이브러리) 및 OAuth 2.0을 기반으로 하는 최신 인증에 대해 설명합니다.
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816228"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>비즈니스용 Skype에서 ADAL(최신 인증)을 사용하는 방법
 
이 문서에서는 비즈니스용 Skype 서버 2016년 3월 누적 업데이트 또는 비즈니스용 Skype 서버 2019의 초기 릴리스에서 찾을 수 있는 최신 인증(ADAL(Active Directory 인증 라이브러리) 및 OAuth 2.0을 기반으로 하는 최신 인증을 소개합니다.
  
## <a name="what-is-adal"></a>ADAL이란?

ADAL은 'Active Directory 인증 라이브러리'의 약어로, OAuth 2.0과 함께 최신 인증의 기조입니다. 이 코드 라이브러리는 보안 토큰을 통해 디렉터리의 보안 리소스를 클라이언트 응용 프로그램(예: 비즈니스용 Skype)에서 사용할 수 있도록 설계되었습니다. ADAL은 OAuth 2.0과 함께 작동하여 MFA(Multi-Factor Authentication) 및 더 많은 형태의 SAML 인증과 같은 더 많은 인증 및 권한 부여 시나리오를 가능하게 합니다.
  
클라이언트 역할을 하는 다양한 앱은 보안 리소스에 대한 도움말을 위해 최신 인증을 활용할 수 있습니다. 비즈니스용 Skype 서버에서는 사용자에게 리소스에 대한 적절한 수준의 권한 부여를 제공하기 위해 이 기술이 On-premises 클라이언트와 온라인 서버 간에 사용됩니다.
  
ADAL 및 OAuth 2.0을 기반으로 하는 최신 인증 대화에는 몇 가지 공통 요소가 있습니다.
  
- 리소스 요청을 하는 클라이언트가 있습니다. 이 경우 클라이언트는 비즈니스용 Skype입니다.
    
- 클라이언트에 특정 수준의 액세스가 필요한 리소스가 있으며, 이 리소스는 디렉터리 서비스(이 경우 리소스는 비즈니스용 Skype 서버)에 의해 보호됩니다.
    
- OAuth 연결이 있습니다. 즉, 사용자가 리소스에 액세스할  수 있도록 권한을 부여하기 위한 연결이 있습니다. (OAuth는 보다 설명적인 이름인 '서버 간' auth로도 알려져 있으며 종종 S2S로 약어로도 알려져 있습니다.)
    
비즈니스용 Skype 서버 ADAL(최신 인증) 대화에서 비즈니스용 Skype 서버는 ADFS(WINDOWS SERVER 2012 R2의 ADFS 3.0)를 통해 통신합니다. 일부 다른 IdP(ID 공급자)를 사용하여 인증이 진행될 수 있지만, ADFS와 직접 통신하도록 비즈니스용 Skype 서버를 구성해야 합니다. 비즈니스용 Skype 서버에서 작동하도록 ADFS를 구성하지 않은 경우 ADFS 설치를 [완료하세요.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)
  
ADAL은 비즈니스용 Skype 서버 2016년 3월 누적 업데이트에 포함되어 있으며 성공적인 구성을 위해 비즈니스용 Skype의 2016년 3월 누적 업데이트를 설치해야 합니다.  비즈니스용 Skype 서버 2019의 경우 제품의 초기 릴리스에서 사용할 수 있습니다.
  
> [!NOTE]
> 초기 릴리스 동안에는 Skype 토폴로지가 혼합되어 있는 경우와 함께 사용할 수 없는 경우만, On-premises 환경의 최신 인증이 지원됩니다. 예를 들어 환경이 전적으로 비즈니스용 Skype 서버인 경우 이 설명은 변경될 수 있습니다. 
  
성공적인 구성을 위해 ADAL에서 사용하는 명령이 있는 .ps1 파일을 포함한 PowerShell 패키지를 다운로드해야 합니다.

비즈니스용 Skype에서 최신 인증을 구현하는 방법에 대한 자세한 내용은 [다음을 참조하세요. 비즈니스용 Skype에서 ADAL(최신 인증)을](../../manage/authentication/use-adal.md) 사용하는 방법
