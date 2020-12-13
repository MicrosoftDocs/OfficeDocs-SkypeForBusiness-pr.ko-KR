---
title: On-premises 사용자를 위한 클라우드 음성메일 서비스 계획| PBX 비즈니스용 Skype 서버 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 이 문서에서는 Microsoft Cloud Voicemail 서비스를 구현하기 위한 이점, 계획 고려 사항 및 요구 사항에 대해 설명합니다. 클라우드 음성메일 구성에 대한 자세한 내용은 클라우드 음성메일 구성을 참조하십시오.
ms.openlocfilehash: 8a75c670448cf69cf6d9d772c670c9451fd94f80
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662093"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>On-premises 사용자를 위한 클라우드 음성메일 서비스 계획

## <a name="overview"></a>개요

이 문서에서는 혜택, 계획 고려 사항 및 Microsoft Cloud Voicemail 서비스를 구현하기 위한 요구 사항에 대해 설명하고 있습니다. 클라우드 음성메일 구성에 대한 자세한 내용은 [Cloud Voicemail 서비스 구성을 참조하십시오.](configure-cloud-voicemail.md)

Cloud Voicemail은 비즈니스용 Skype 2019 또는 Exchange Online에 사서함이 있는 비즈니스용 Skype 2019 음성 사용자에 대해 음성 메시징 기능을 제공하는 Exchange Server UM(통합 메시징)을 대신합니다. Cloud Voicemail은 다음과 같은 이점을 제공합니다.

- 향상된 음성 전사 기능이 있는 음성메일 응답 및 보관 기능

- 비즈니스용 Skype Online 또는 Outlook 클라이언트를 사용하여 사용자의 Exchange 사서함에서 음성 메일에 액세스

- Microsoft 365 관리 센터를 사용하여 음성메일 옵션을 관리하는 능력

- Exchange 사서함에 대한 지원(프레미스 또는 클라우드)

- Exchange Online 통합 메시징에서 기존 사용자 인사말 활용

> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 사용 중지됩니다. 이 경우 사용자는 더 이상 비즈니스용 Skype Online 클라이언트를 통해 Exchange 사서함의 음성 메일에 액세스할 수 없습니다.

기능 비교에 대한 자세한 내용은 비즈니스용 Skype 서버 계획 및 마이그레이션 [Exchange Server 참조하세요.](plan-um-migration.md)

비즈니스용 Skype 서버 2019는 사서함이 이전 버전의 Exchange Server(2013, 2016)에 있는 사용자에 대해 Exchange UM을 계속 사용하게 됩니다.  Exchange Server 및 비즈니스용 Skype 서버 버전을 기반으로 사용할 음성 메일 솔루션을 이해하는 것은 비즈니스용 Skype 서버 2019 또는 Exchange Server 2019로의 마이그레이션을 계획하는 데 중요한 부분입니다. 마이그레이션 및 상호 연결성에 대한 자세한 내용은 비즈니스용 Skype 서버 계획 및 마이그레이션 Exchange Server [참조하세요.](plan-um-migration.md)

Cloud Voicemail을 사용하면 다음 때문에 관리 작업이 크게 간소화됩니다.

- Exchange UM 역할을 구성할 필요가 없습니다.
- 클라우드 음성메일의 설치 작업이 더 간단합니다.
- 음성메일 기능에 대한 업데이트는 클라우드에서 직접 제공될 수 있으므로 사용자는 항상 CU(누적 업데이트)에 의존하지 않고 최신 기능 및 업데이트에 액세스할 수 있습니다.
- Exchange 사서함과 온라인 Exchange 사서함에 대해 동일한 컨트롤 집합이 있습니다. 이러한 컨트롤에 대한 자세한 내용은 전화 시스템 음성메일 [설정을 참조하세요.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

다음 다이어그램에는 하이브리드 배포의 클라우드 음성메일이 표시됩니다.

![SfB 클라우드 음성메일](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

이에 대한 예가 없는 통화는 다음과 같이 처리됩니다.  

1. 비즈니스용 Skype 2019에 있는 사용자의 경우, 온라인 클라우드 음성 메일 서비스로 전화를 걸면 해당 전화가 온라인 프레미스 비즈니스용 Skype 서버에서 전송됩니다.
2. 서비스는 전사 등을 포함하여 음성메일을 처리합니다.
3. 그런 다음 서비스는 사서함이 온라인인지에 따라 사용자의 Exchange 사서함에 음성 메일을 보관합니다.  
4. 사용자는 비즈니스용 Skype 또는 Outlook 클라이언트에서 음성 메일에 액세스할 수 있습니다.

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 비즈니스용 Skype 서버가 이미 배포된 것으로 가정합니다.  요구 사항은 시나리오에 따라 다릅니다.

- 이미 Exchange UM 온라인을 사용하고 있으며 비즈니스용 Skype 2019로 업그레이드하는 경우 호스팅된 음성 메일 정책을 수정하고 호스팅 공급자가 올바르게 설정되어 있는지 확인해야 합니다. 자세한 내용은 [Cloud Voicemail 서비스 구성을 참조하세요.](configure-cloud-voicemail.md)

- Exchange UM을 사용하는 경우 또는 Exchange UM 온라인 및 프레미스를 사용하는 사용자가 혼합되어 있는 경우 호스팅된 음성메일 정책과 호스팅 공급자를 모두 수정해야 합니다.  자세한 내용은 [Cloud Voicemail 서비스 구성을 참조하세요.](configure-cloud-voicemail.md)

- Cloud Voicemail의 새 구성을 확인하려면 클라우드 음성메일 서비스 구성에 설명된 [단계를 따르세요.](configure-cloud-voicemail.md)

위의 요구 사항 외에도 Microsoft Cloud Voicemail 서비스에 연결하도록 아래 요구 사항을 구성해야 합니다.

- 하이브리드 연결. 비즈니스용 Skype 서버가 이미 배포되어 있으며, 비즈니스용 Skype 사용자에 대해 클라우드 음성메일을 사용하도록 설정하려는 경우, 하이브리드 연결이 프레미스 환경과 온라인 환경 간에 설정되어 있는지 확인해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 비즈니스용 Skype 서버와 [Microsoft 365 또는 Office 365](plan-hybrid-connectivity.md) 간의 하이브리드 연결 계획과 비즈니스용 [Skype 서버와 Office 365](configure-hybrid-connectivity.md)간의 하이브리드 연결 구성을 참조하세요.

- 비즈니스용 Skype 서버에서는 Enterprise Voice 및 호스팅된 음성메일을 사용할 수 있도록 설정해야 합니다.

- EWS(외부 Exchange 웹 서비스) URL 및 자동 검색을 설정해야 합니다. 또는 일부 클라우드 음성메일 기능이 제한됩니다.

- 프레미스 Exchange 서버가 있는 경우 사서함 사용자에 대해 클라우드 음성 메일 설정 Exchange Server [사용하여 Cloud Voicemail을 설정하십시오.](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 실행성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019를 배포하려는 경우 마이그레이션을 신중하게 계획하여 음성 메시징을 계속 사용할 수 있도록 해야 합니다. 다음 사항에 유의해야 합니다.

- Exchange Server 2019에서 더 이상 Exchange UM 기능을 제공하지 않습니다.
- 비즈니스용 Skype 서버 2019가 Exchange Online UM과 더 이상 통합되지 않습니다.

다음 표에는 클라우드 음성 메일에 대한 버전 상호 관리 및 지원되는 토폴로지가 나와 있습니다. 이 표에서는 사용자가 홈으로 사용할 수 있는 비즈니스용 Skype 서버 버전과 Exchange 사서함을 제공하는 가능한 버전을 비교합니다. Exchange Online 또는 2019에서 비즈니스용 Skype 2019를 사용하려면 클라우드 음성 Exchange Server 필요합니다.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Business Server 2019용 Skype | Exchange Server UM | Exchange Server UM | 클라우드 음성 메일 | 클라우드 음성 메일 |
| Business Server 2015용 Skype | Exchange Server UM | Exchange Server UM | 지원되지 않음 | 클라우드 음성 메일 |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 지원되지 않음 | 클라우드 음성 메일 |

Microsoft는 다음과 같은 마이그레이션 경로를 권장합니다.

- 비즈니스용 Skype 서버 2019로 업그레이드하는 경우 Exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019를 사용하는 경우 Cloud Voicemail로 업그레이드해야 합니다.
- Exchange Server 2019로 업그레이드하는 경우 이전 버전의 Exchange Server UM for Business Server 음성 메시징을 사용하는 경우 사서함 업그레이드 전에 비즈니스용 Skype 서버 2019로 업그레이드하는 것이 좋습니다.  그렇지 않으면 음성 메시징 기능이 손실됩니다.
- 비즈니스용 Skype 서버 2019로 업그레이드하는 경우 Exchange Online UM을 사용하여 비즈니스용 Skype 서버 2015를 음성메일로 구성한 경우 사용자의 음성메일은 계정이 비즈니스용 Skype 서버 2019로 이동될 때 Exchange Online UM에서 클라우드 음성메일로 자동으로 마이그레이션됩니다. 

마이그레이션 계획에 대한 자세한 내용은 비즈니스용 Skype 서버 계획 및 마이그레이션 [Exchange Server 참조하세요.](plan-um-migration.md)
