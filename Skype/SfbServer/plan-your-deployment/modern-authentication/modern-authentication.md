---
title: 2016년 8월의 최신 인증 비즈니스용 Skype
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
description: 다른 제품과의 통합을 포함하여 비즈니스용 Skype 서버 인증 및 권한 부여에 대한 계획 항목
ms.openlocfilehash: 0ba25ce4a1c314e2df96c1a1009254254277f4636d937fa2f14277a92976b7b8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349930"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>2013에서 인증 및 권한 부여 비즈니스용 Skype

인증 및 권한 부여는 관련된 개념이지만 둘 다 필요한 경우와는 다른 작업을 합니다. 간단하게 말하면, AuthN(Authenciation)은 유효한 사용자가 알고 있는 암호만 사용하며 암호, 코드, 지문, 인증서, 참인 사용자에 대한 클레임 조합 또는 이러한 두 가지를 함께 사용하는 조합일 수 있습니다. AuthN은 사용자 신원을 증명하기 위해 진행하는 프로세스입니다.

인증(AuthZ)은 사용자 신원을 입증한 후 액세스할 수 있는 권한과 관련이 있습니다. 확인, 편집 및 기타 액세스가 허용된 기능을 파악합니다. 예를 들어 SharePoint Online에 대한 강력한 사이트 모음 관리자 액세스 권한이 있지만 비즈니스용 Skype Online과 같은 다른 온라인 작업으로 전환하는 경우 서버 또는 서버의 구성을 변경하지 말고 사용자 문제를 해결할 수 있는 권한이 있을 수 있습니다. 작업량(예: Exchange Online 경우 평균 사용자 액세스만 있을 수 있습니다. AuthZ는 서비스/worload, 응용 프로그램, 파일 및 기타 데이터에 대한 액세스의 양과 권한을 검사합니다.

예제에는 SharePoint 및 Exchange 온라인과 같은 온라인 속성이 포함되지만, AuthN 및 AuthZ 프로세스는 동일한 방식으로 하이브리드 프레미스와 하이브리드 프레미스에서 작동됩니다. 궁극적으로, AAD 커넥트 및 ADFS와 같은 도구가 AuthN 및 AuthZ 스토리에 참여하게 됩니다. 즉, 클라우드의 워크로드 간을 전환할 때처럼 사용자에게 자격 증명을 자주 묻지 못하도록 Auth Sign-On Z 흐름을 침입하여 AuthN 및 AuthZ 시나리오를 만들 수 있습니다. 그러나 그 자체로는 AuthN 또는 AuthZ를 책임지는 것이 아니라, 이러한 AuthZ에 대한 책임이 있습니다.

오늘날 많은 기술은 이러한 프로세스(AuthN 및 AuthZ)를 하나의 메커니즘으로 고려하며 인증 프로세스에 대한 많은 참조를 들을 수 있으며 이러한 프로세스에 대한 권한 부여도 포함됩니다. 사용자 액세스의 첫 번째 단계는 AuthN으로, 사용자가 자신의 신원을 확인하며, AuthZ는 사용자가 액세스할 수 있는 사용자를 확인하는 데 사용할 수 있는 지식을 사용(Open Authorization 또는 OAuth와 함께 표시)합니다.

  
## <a name="authentication-and-authorization-planning-topics"></a>인증 및 권한 부여 계획 항목

[ADAL(최신 인증)을 사용하는 비즈니스용 Skype](plan-adal.md)

[최신 인증으로 지원되는 비즈니스용 Skype 토폴로지](topologies-supported.md)

[네트워크 내부 및 외부에서 레거시 인증 방법을 끄기 위한 계획](turn-on-modern-auth.md)

