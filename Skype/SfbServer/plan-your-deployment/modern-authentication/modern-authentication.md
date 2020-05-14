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
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221582"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>비즈니스용 Skype의 인증 및 권한 부여 논의

인증 및 권한 부여는 관련 된 개념 이지만 다른 작업을 수행 하는 것이 좋습니다 (두 가지 모두 필요 함). Authenciation (인증)은 비밀에만 적합 하며, 유효한 사용자가 알고 있거나 갖고 있으며 암호, 코드, 지문, 인증서, 사용자에 대 한 클레임 조합 또는 함께 사용 되는 이러한 항목의 조합이 될 수 있습니다. 인증는 사용자의 신원을 입증 하기 위한 프로세스입니다.

권한 부여 (인증)는 사용자가 누구 인지 입증 한 후에 액세스 하는 것과 관련 된 것입니다. 이 개체는 보기, 편집 및 기타 액세스를 허용한 사용자를 결정 합니다. 예를 들어 SharePoint Online에 대 한 강력한 사이트 모음 관리자 액세스 권한이 있지만 비즈니스용 Skype Online과 같은 다른 온라인 작업 환경으로 전환 하는 경우에는 서버 구성을 변경 하지 않고 사용자 문제를 해결 하는 데 필요한 권한이 있을 수 있습니다. Exchange Online과 같은 세 번째 작업 부하에서는 평균 사용자 액세스만 있을 수 있습니다. 인증에서는 서비스/진행에 대 한 액세스 권한, 응용 프로그램, 파일 및 기타 데이터를 확인 합니다.

이 예에는 SharePoint 및 Exchange online과 같은 온라인 속성이 포함 되어 있지만 인증 및 인증의 프로세스는 온-프레미스와 하이브리드 프레미스에서 동일한 방식으로 작동 합니다. 궁극적으로, AAD Connect 및 ADFS와 같은 도구는 온-프레미스 계정 및 암호를 클라우드 AD (Azure AD)로 동기화 하거나, 사용자에 게 자격 증명을 입력 하 라는 메시지가 자주 표시 되지 않도록 하 여 인증 및 인증 스토리에 참여 하 게 함으로써 클라우드의 워크 로드를 전환 하 여 Single Sign-on 시나리오를 만드는 것을 말합니다. 하지만 이러한 사용자는 인증 또는 인증을 책임 지는 메커니즘의 일부일 뿐입니다.

오늘날 대부분의 기술은 이러한 프로세스 (인증 및 인증)를 하나의 메커니즘으로 간주 하며, 인증 프로세스에 대 한 많은 참조를 통해 해당 권한 부여도 함께 들을 수 있습니다. 사용자 액세스의 첫 번째 단계는 인증이 고 사용자가 말하고 있다는 것을 입증 하 고, 인증에 사용 되는 사람을 결정 하는 데 도움이 됩니다 (공개 권한 부여 또는 OAuth 표시).

  
## <a name="authentication-and-authorization-planning-topics"></a>인증 및 권한 부여 계획 항목

[비즈니스용 Skype에서 ADAL (최신 인증)을 사용 하는 방법](plan-adal.md)

[최신 인증과 함께 지원 되는 비즈니스용 Skype 토폴로지](topologies-supported.md)

[네트워크에서 내부적으로 또는 외부적으로 레거시 인증 방법을 해제할 계획입니다.](turn-on-modern-auth.md)

