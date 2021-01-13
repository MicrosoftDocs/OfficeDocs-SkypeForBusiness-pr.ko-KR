---
title: 비즈니스용 Skype의 최신 인증 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 다른 제품과의 통합을 포함하여 비즈니스용 Skype 서버의 인증 및 권한 부여 계획 항목
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816248"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>비즈니스용 Skype에서 인증 및 권한 부여 설명

인증 및 권한 부여는 관련된 개념이지만 서로 다른 작업을 합니다(둘 다 필요한 경우). 간단하게 말하면, 인증(AuthN)은 암호, 코드, 지문, 인증서, 참인 사용자에 대한 클레임 조합 또는 함께 사용되는 이러한 작업의 조합일 수 있는 유효한 사용자만 알고 있는 암호에 의존합니다. AuthN은 사용자 신원을 증명하기 위해 진행하는 프로세스입니다.

인증(AuthZ)은 정체가 입증된 후 액세스할 수 있는 권한과 관련이 있습니다. 확인, 편집 및 기타 액세스가 허용된 기능을 결정하는 데 사용할 수 있는 권한이 결정됩니다. 예를 들어 SharePoint Online에 대한 강력한 사이트 모음 관리자 액세스 권한이 있을 수 있지만 비즈니스용 Skype Online과 같은 다른 온라인 작업으로 전환하는 경우 서버 또는 서버의 구성을 변경하지 말고 사용자 문제를 해결할 수 있는 권한이 있을 수 있습니다. Exchange Online과 같은 세 번째 작업에서는 평균 사용자의 액세스만 있을 수 있습니다. AuthZ는 서비스/worloads, 응용 프로그램, 파일 및 기타 데이터에 대한 액세스 권한을 확인하고 그 양을 검사합니다.

이 예제에는 SharePoint 및 Exchange Online과 같은 온라인 속성이 포함되지만, AuthN 및 AuthZ 프로세스는 같은 방식으로 하이브리드 프레미스 및 하이브리드 프레미스에서 작동됩니다. 궁극적으로, AAD Connect 및 ADFS와 같은 도구는 AuthN 및 AuthZ 스토리에 참여하게 됩니다. 즉, 클라우드의 워크로드 간을 전환할 때 사용자에게 자격 증명을 요청하지 않는 등, AuthZ 흐름을 침입하여 AuthN 및 Auth Sign-On Z 스토리에 참여하게 됩니다. 그러나 자체적으로 책임이 있는 AuthN 또는 AuthZ가 아니라, 바로 이러한 AuthZ를 사용할 수 있습니다.

오늘날 많은 기술은 이러한 프로세스(AuthN 및 AuthZ)를 하나의 메커니즘으로 고려하고 인증 프로세스에 대한 많은 참조를 들리며 권한 부여도 포함합니다. 사용자 액세스의 첫 번째 단계는 AuthN으로, 사용자가 누구인지를 알 수 있으며, AuthZ는 사용자가 액세스할 수 있는 사용자에 대한 지식을 사용하여 액세스 권한을 부여(Open Authorization 또는 OAuth에 표시)합니다.

  
## <a name="authentication-and-authorization-planning-topics"></a>인증 및 권한 부여 계획 항목

[비즈니스용 Skype에서 ADAL(최신 인증)을 사용하는 방법](plan-adal.md)

[최신 인증으로 지원되는 비즈니스용 Skype 토폴로지](topologies-supported.md)

[네트워크 내부 및 외부에서 레거시 인증 방법을 해제할 계획입니다.](turn-on-modern-auth.md)

