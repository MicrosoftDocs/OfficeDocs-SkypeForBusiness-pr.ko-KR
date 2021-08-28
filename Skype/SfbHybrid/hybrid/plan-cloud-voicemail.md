---
title: 클라우드 음성 사서함 사용자를 위한 서비스 계획| PBX 비즈니스용 Skype 서버 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: 이 문서에서는 Microsoft 클라우드 음성 사서함 구현하기 위한 이점, 계획 고려 사항 및 요구 사항에 대해 설명합니다. 구성에 대한 자세한 클라우드 음성 사서함 구성을 클라우드 음성 사서함.
ms.openlocfilehash: df9675c7ebe36f73190240dc612ce83dd0de2263
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594872"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>클라우드 음성 사서함 사용자에 대한 서비스 계획

## <a name="overview"></a>개요

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 문서에서는 혜택, 계획 고려 사항 및 사내 사용자를 위한 Microsoft 클라우드 음성 사서함 서비스를 구현하기 위한 요구 사항에 대해 설명합니다. 서비스 구성에 대한 자세한 클라우드 음성 사서함 [서비스 구성을 클라우드 음성 사서함 참조하세요.](configure-cloud-voicemail.md)

클라우드 음성 사서함 2019 또는 Exchange Server 사서함이 있는 비즈니스용 Skype 2019 음성 사용자를 위한 음성 메시징 기능을 제공하는 Exchange UM(통합 메시징)을 대신하여 Exchange Online. 클라우드 음성 사서함 및 온라인 사용자 모두에게 다음과 같은 이점을 제공합니다.

- 음성메일 응답 및 향상된 음성 전사 기능이 있는 보관 기능

- 비즈니스용 Skype Online 또는 Outlook 사용하여 사용자의 Exchange 사서함에서 음성 메일에 액세스

- 음성 Microsoft 365 관리 센터 관리 하는 기능을 사용 하 고

- Exchange 또는 클라우드의 사서함에 대한 지원

- 통합 메시징에서 기존 사용자 Exchange Online 활용

> [!Important]
> 비즈니스용 Skype 온라인은 2021년 7월 31에 사용 중지되어 사용자가 Exchange Online 클라이언트를 통해 Exchange 음성 메일에 액세스할 비즈니스용 Skype 됩니다.

기능 비교에 대한 자세한 내용은 [Plan for 비즈니스용 Skype 서버 and Exchange Server migration을 참조하십시오.](plan-um-migration.md)

비즈니스용 Skype 서버 2019는 사서함이 이전 버전의 Exchange(2013, 2016)에 있는 사용자에 대해 Exchange Server UM을 계속 사용할 수 있습니다.  Exchange Server 및 비즈니스용 Skype 서버 버전을 기반으로 사용할 음성 메일 솔루션을 파악하는 것은 비즈니스용 Skype 서버 2019 또는 Exchange Server 2019로의 마이그레이션 계획의 중요한 부분입니다. 마이그레이션 및 상호 연결성에 대한 자세한 내용은 [Plan for 비즈니스용 Skype 서버 and Exchange Server 참조하십시오.](plan-um-migration.md)

이 클라우드 음성 사서함 사용하면 관리 작업이 매우 간소화됩니다.

- UM 역할을 구성할 필요가 Exchange 없습니다.
- 설치 작업에 대한 클라우드 음성 사서함 더 간단합니다.
- 음성메일 기능에 대한 업데이트는 클라우드에서 직접 제공될 수 있으므로 사용자는 항상 CU(누적 업데이트)에 의존하지 않고 최신 기능 및 업데이트에 액세스할 수 있습니다.
- 사서함에 대해 동일한 컨트롤 집합이 있는 경우, 모든 사서함에 대해 Exchange 있습니다. 이러한 컨트롤에 대한 자세한 내용은 음성 전화 시스템 [을 참조하세요.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

다음 다이어그램은 하이브리드 클라우드 음성 사서함 배포의 여러 가지 기능을 보여줍니다.

![SfB 클라우드 음성 사서함](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

이에 대한 예가 없는 통화는 다음과 같이 처리됩니다.  

1. 비즈니스용 Skype 2019에 있는 사용자의 경우, 온라인 비즈니스용 Skype 서버 클라우드 음성 사서함 서비스로 전화를 비즈니스용 Skype 서버 없는 통화가 전송됩니다.
2. 서비스는 음성메일을 처리합니다(전사 포함).
3. 그런 다음 서비스는 사서함이 Exchange 온라인이든 사용자의 사서함에 음성 메일을 저장합니다.  
4. 사용자는 자신의 음성 메일 또는 클라이언트에서 음성 비즈니스용 Skype Outlook 있습니다.

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 비즈니스용 Skype 서버 이미 배포했다고 가정합니다.  요구 사항은 시나리오에 따라 다릅니다.

- 이미 Exchange UM을 사용하고 있으며 비즈니스용 Skype 2019로 업그레이드하는 경우 호스팅된 음성 메일 정책을 수정하고 호스팅 공급자가 올바르게 설정되어 있는지 확인해야 합니다. 자세한 내용은 [Configure 클라우드 음성 사서함 참조하세요.](configure-cloud-voicemail.md)

- Exchange UM을 사용하는 경우 또는 Exchange UM 온라인 및 프레미스를 사용하는 사용자가 혼합된 경우 호스팅된 음성메일 정책과 호스팅 공급자를 모두 수정해야 합니다.  자세한 내용은 [Configure 클라우드 음성 사서함 참조하세요.](configure-cloud-voicemail.md)

- 새 구성 클라우드 음성 사서함 Configure [클라우드 음성 사서함 에 설명된 단계를 따르세요.](configure-cloud-voicemail.md)

위의 요구 사항 외에도 아래 요구 사항은 Microsoft 클라우드 음성 사서함 서비스에 연결하도록 구성해야 합니다.

- 하이브리드 연결. 이미 배포된 비즈니스용 Skype 서버 있는 경우 클라우드 음성 사서함 사용자에 대해 클라우드 음성 사서함 사용하도록 설정하려는 경우, 하이브리드 연결이 프레미스 환경과 온라인 환경 간에 설정되어 있는지 확인해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 plan [hybrid connectivity between 비즈니스용 Skype 서버 and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and Configure hybrid [connectivity between 비즈니스용 Skype 서버 and Office 365.](configure-hybrid-connectivity.md)

- Enterprise Voice 및 Hosted Voicemail을 사용할 수 있도록 설정해야 비즈니스용 Skype 서버.

- EWS(외부 Exchange 서비스) URL 및 자동 검색을 설정해야 합니다. 또는 일부 클라우드 음성 사서함 기능이 제한됩니다.

- 프레미스 Exchange 있는 경우 클라우드 음성 사서함 사서함 사용자에 대한 클라우드 음성 사서함 단계를 사용하여 Exchange Server [합니다.](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 실행성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019를 배포하려는 경우 마이그레이션을 신중하게 계획하여 음성 메시징을 계속 사용할 수 있도록 해야 합니다. 다음 사항에 유의해야 합니다.

- Exchange Server 2019에서는 더 이상 UM Exchange 제공하지 못합니다.
- 비즈니스용 Skype 서버 2019는 더 이상 Exchange Online UM과 통합하지 않습니다.

다음 표에서는 클라우드 음성 사서함 버전 상호 상호성 및 지원되는 토폴로지가 나와 있습니다. 이 토폴로지에서는 사용자가 비즈니스용 Skype 서버 사서함을 제공하는 가능한 버전과 함께 사용할 수 있는 Exchange 비교합니다. 2019 또는 클라우드 음성 사서함 2019에서 비즈니스용 Skype 2019를 사용하려면 Exchange Online Exchange Server 합니다.

| Skype/Lync 버전 | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Business Server 2019용 Skype | Exchange Server UM | Exchange Server UM | 클라우드 음성 메일 | 클라우드 음성 메일 |
| Business Server 2015용 Skype | Exchange Server UM | Exchange Server UM | 지원되지 않음 | 클라우드 음성 메일 |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 지원되지 않음 | 클라우드 음성 메일 |

Microsoft에서는 다음과 같은 마이그레이션 경로를 권장합니다.

- 비즈니스용 Skype 서버 2019로 업그레이드하는 경우 Exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 클라우드 음성 사서함 2019를 사용하는 경우 Exchange Server 업그레이드해야 합니다.
- Exchange Server 2019로 업그레이드하는 경우 비즈니스용 Skype 서버 음성 메시징에 이전 버전의 Exchange Server UM을 사용하는 경우 사서함 업그레이드 전에 비즈니스용 Skype 서버 2019로 업그레이드하는 것이 좋습니다.  그렇지 않으면 음성 메시징 기능이 손실됩니다.
- 비즈니스용 Skype 서버 2019로 업그레이드하고 Exchange Online UM을 사용하여 음성 비즈니스용 Skype 서버 2015를 구성한 경우 사용자의 음성메일은 계정이 비즈니스용 Skype 서버 2019로 이동될 때 Exchange Online UM에서 클라우드 음성 사서함 UM으로 자동으로 마이그레이션됩니다. 

마이그레이션 계획에 대한 자세한 내용은 [Plan for 비즈니스용 Skype 서버 and Exchange Server migration을 참조하십시오.](plan-um-migration.md)