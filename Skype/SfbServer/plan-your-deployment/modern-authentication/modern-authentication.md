---
title: 비즈니스용 Skype의 최신 인증 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 다른 제품과의 통합을 포함 하 여 비즈니스용 Skype 서버에 대 한 인증 및 권한 부여에 대 한 계획 항목
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815846"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>비즈니스용 Skype에서 인증 및 권한 부여 논의

인증 및 권한 부여는 관련 개념 이지만 다른 작업을 수행 합니다 (둘 다 필요 하지만). 간단한 용어로, authenciation (AuthN)는 유효한 사용자가 알고 있거나 보유 하 고 있는 비밀에 따라 다르며, 암호, 코드, 지문, 인증서, 참 사용자에 대 한 클레임 조합 또는 이러한 항목의 조합 등을 사용할 수 있습니다. AuthN는 여러분의 의견을 증명할 수 있는 과정입니다.

인증 (인증)은 사용자가 누구 인지 입증 한 후에 액세스 하는 것과 관련이 있습니다. 여기에는 보기, 편집 및 기타 액세스 권한이 허용 된 내용이 결정 됩니다. 예를 들어 SharePoint Online에 대 한 강력한 사이트 모음 관리자 액세스 권한이 있을 수 있지만 비즈니스용 Skype Online과 같은 다른 온라인 작업으로 전환 하는 경우 사용자 문제를 해결 하는 데 필요한 권한이 있을 수 있으며, 다음의 구성은 변경 되지 않습니다. 서버 또는 서버. Exchange Online 등의 세 번째 작업 부하에서는 평균 사용자 액세스만 있을 수 있습니다. 인증을 통해 서비스/기간에 대 한 액세스 권한, 응용 프로그램, 파일 및 기타 데이터를 확인할 수 있습니다.

이 예제에는 SharePoint 및 Exchange online과 같은 온라인 속성이 포함 되지만, 온-프레미스 및 하이브리드 구내에서 AuthN 및 인증 작업 프로세스는 동일한 방식으로 진행 됩니다. 궁극적으로, AAD 연결 및 ADFS와 같은 도구는 온-프레미스 계정 및 암호를 클라우드 광고 (Office 365 또는 Azure의 경우 Azure AD)에 동기화 하거나 인증 흐름에 intruding 하 여 AuthN 및 인증 영역에 관여 하 게 됩니다. 사용자는 자신의 자격 증명을 입력 하 라는 메시지를 표시 하지 않고, 클라우드의 작업 부하 간에 전환 하는 경우 Single Sign-on 시나리오를 만들어 봅니다. 그러나 자기 자신에 게는 AuthN 나 인증을 책임 지는 않지만, 기술의 일부일 뿐입니다.

현재 많은 기술은 이러한 프로세스 (AuthN 및 인증)를 하나의 메커니즘으로 간주 하 고, 인증 프로세스에 대 한 많은 참조를 포함 하 여 해당 사용자에 게 권한을 부여 합니다. 사용자 액세스의 첫 번째 단계는 AuthN이 고, 사용자에 게 자신이 누구 인지를 입증 하는 것이 중요 하며,이 인증은 공개 권한 부여 또는 OAuth를 사용 하 여 볼 수 있는 것과 같이, 자신이 누구에 게 누가 액세스할 수 있는지를 결정 하는 것을 말합니다.

  
## <a name="authentication-and-authorization-planning-topics"></a>인증 및 권한 계획 항목

[비즈니스용 Skype에서 최신 인증 (ADAL)을 사용 하는 방법](plan-adal.md)

[최신 인증으로 지원 되는 비즈니스용 Skype 토폴로지](topologies-supported.md)

[네트워크의 내부 및 외부에서 레거시 인증 방법을 해제할 계획입니다.](turn-on-modern-auth.md)

