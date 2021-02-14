---
title: 비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: 이 항목에서는 기존 비즈니스용 Skype 서버 또는 비즈니스용 Skype 서버 또는 Exchange Server 최신 버전 또는 비즈니스용 Skype Online 또는 Exchange Online으로 마이그레이션하기로 결정할 때 고려해야 할 항목에 대해 설명합니다.
ms.openlocfilehash: cb6d58cf839b6260bc8889817ea568528e4832f4
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359044"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획

이 항목에서는 기존 비즈니스용 Skype 서버 또는 Exchange Online으로 마이그레이션하기로 결정할 때 고려해야 Exchange Server 설명합니다. 마이그레이션할 수 있는 작업 및 마이그레이션 시간은 조직에서 이미 설정한 설정에 따라 크게 다를 수 있습니다.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 2019의 기능 변경 사항

Exchange 2019 및 비즈니스용 Skype 서버 2019에서는 지원되는 기능이 일부 변경되었습니다.

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019의 통합 메시징 지원

Exchange 2019에서는 UM(통합 메시징)이 더 이상 사용되지 않습니다. 즉, Exchange 2019는 더 이상 다음 기능을 제공하지 않습니다.

- 음성 메일
- 자동 회의

Exchange 2013 또는 Exchange 2016의 UM 서비스에 UM 역할을 배포한 경우 Exchange 2019로 업그레이드하려는 경우 음성메일을 Microsoft 365 또는 Office 365의 Microsoft Cloud Voicemail 서비스로 마이그레이션해야 합니다. 음성메일을 Cloud Voicemail로 마이그레이션하려면 [아래 Exchange 2013/Exchange 2016 및 비즈니스용 Skype 2015에서 Exchange 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) 및 비즈니스용 Skype 2019 섹션을 살펴보세요.
> [!IMPORTANT]
> Exchange 2013 또는 Exchange 2016 서버의 사용자에게 UM 사용 가능 사서함이 있는 경우 비즈니스용 Skype 서버를 비즈니스용 Skype 서버 2019로 업그레이드하고 음성 메시징이 정전되지 않도록 사용자를 이동하기 전에 Exchange 2019로 이동하지 않도록 합니다.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 2019의 PBX 지원

Cloud Voicemail은 PBX(Private Branch Exchange)에 음성 메시징 기능을 제공하지 않습니다. PBX에 Exchange Server 통합 메시징을 사용 중일 때 Exchange Server 2019로 업그레이드하려는 경우 [Exchange](https://blogs.technet.microsoft.com/exchange/)팀 블로그의 [Exchange Online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) 통합 메시징에서 세션 경계 컨트롤러에 대한 지원이 중단될 새 날짜 블로그 게시물에 나열된 세 가지 옵션 중 하나를 채택해야 합니다.

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019의 Exchange Online UM 지원

비즈니스용 Skype 서버 2019에서는 Exchange Online UM에서 클라우드 음성메일로 전환하고 있습니다. 사용자가 비즈니스용 Skype 2019 서버로 이동되면 호스팅된 음성메일에 대해 구성된 경우 자동으로 Cloud Voicemail 사용을 시작하게 됩니다. 현재 Exchange Online UM을 사용하고 있는 경우 클라우드 음성메일 사용을 시작하려면 사용자를 비즈니스용 Skype 서버 2019로 이동하는 것 외의 작업을 할 필요가 없습니다. 그러나 다음에 유의해야 하는 몇 가지 기능이 변경됩니다.

- 조직 자동 전화 교환 Exchange Online UM의 자동 교환을 대체합니다.
- 웹에서 Outlook의 사용자 음성 메일 설정은 클라우드 음성 메일에 적용되지 않습니다.

## <a name="on-premises-um-migration-scenarios"></a>On-premises UM migration scenarios

사용자를 Exchange 2019와 Cloud Voicemail로 마이그레이션할 수 있도록 하는 다음과 같은 시나리오가 지원됩니다.

- Exchange 2013/Exchange 2016 및 비즈니스용 Skype 서버 2015 - Exchange 2019 및 비즈니스용 Skype 서버 2019
- Exchange 2013/Exchange 2016을 통해 비즈니스용 Skype 서버 2019로

다음 시나리오에서는 현재 배포의 일부로 PBX 또는 SBC 구성이 존재하지 않는 것이 필요하며, 사용자가 UM을 구성한 것으로 가정합니다. 또한 이러한 각 솔루션은 사용자가 비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 배포를 구성하기로 결정했다고 가정합니다. 비즈니스용 Skype 하이브리드 배포에 대한 자세한 내용은 하이브리드 연결 [계획을 참조하세요.](plan-hybrid-connectivity.md)

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 및 비즈니스용 Skype 2015에서 Exchange 2019 및 비즈니스용 Skype 2019로

이 시나리오에서는 기존 Exchange 2013, Exchange 2016 및 비즈니스용 Skype 2015 서버를 Exchange 2019 및 비즈니스용 Skype 2019로 마이그레이션할 수 있습니다.

이 항목의 앞부분에서 설명한 대로 Exchange 2019는 더 이상 UM 서비스를 포함하지 않습니다. 즉, Exchange 2019로 이동하려는 모든 사서함의 경우 Cloud Voicemail을 사용하여 UM 서비스에서 제공한 기능을 대체해야 합니다. 비즈니스용 Skype 서버 2019를 설정하고 이 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 배포를 설정하면 Cloud Voicemail이 이러한 Exchange UM 음성메일 서비스를 대체합니다.

사용자를 Exchange 2019 및 비즈니스용 Skype 서버 2019로 이동하는 순서는 모든 사용자가 음성메일 기능을 계속 사용할 수 있도록 하는 데 중요합니다. 음성 메일이 처리되는 위치는 Exchange 및 비즈니스용 Skype 사서함과 사용자의 위치도 결정됩니다. 다음 표에서 지원되는 Exchange 및 비즈니스용 Skype 서버 조합과 음성메일이 처리되는 위치를 살펴 봐야 합니다.

| 사서함 위치:            | 비즈니스용 Skype 서버 2015에 있는 사용자 | 비즈니스용 Skype 서버 2019에 있는 사용자  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 지원되지 않음                           | 클라우드 음성 메일                          |

비즈니스용 Skype 서버 2019 및 Exchange 2019로의 마이그레이션을 시작하기 전에 다음에 유의하세요.

- 클라우드 음성메일은 GA의 조직 자동 전화 교환 지원하지 않습니다. 사서함을 Cloud Voicemail로 이동한 경우 자동 전화 교환을 통해 계속 사용할 수 있도록 하려는 경우 UM 역할 또는 서비스를 실행하는 하나 이상의 Exchange 2013 또는 Exchange 2016 서버를 사용할 수 있도록 유지해야 합니다.
- 사서함을 Exchange 2019로 이동하기 전에  하나 이상의 비즈니스용 Skype 2019 서버를 설정하고 사용자를 해당 서버로 이동해야 합니다. 이렇게 하지 못하면 해당 사서함에서 음성 메일 메시지를 받을 수 없게 됩니다.
- 음성 메일로 전송된 통화는 녹음되는 클라우드 음성 메일로 전송됩니다. 통화가 끝나면 음성 메일 메시지가 받는 사람의 사서함으로 전송됩니다. 인터넷 연결이 클라우드 음성메일을 지원하기에 충분할지 결정할 때 이 음성 트래픽을 고려해야 합니다.

다음은 이 마이그레이션을 완료하기 위한 높은 수준의 단계입니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치하고 구성합니다.
2. 새 비즈니스용 Skype 2019 서버를 포함하려면 하이브리드 배포 구성을 업데이트합니다.
3. 새 서버에 Exchange Server 2019를 설치하고 구성합니다.
4. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동합니다.
5. 클라우드 음성메일을 사용하기 위해 비즈니스용 Skype 서버 2019로 이동한 각 사용자에 대해 호스팅된 음성메일 정책을 설정할 수 있습니다.
6. Exchange 2013 또는 Exchange 2016 서버에서 Exchange 2019 서버로 사서함을 이동합니다.
7. 마지막 사용자가 벗어났을 때 비즈니스용 Skype 2015 서버를 해제합니다.
8. 마지막 사서함이 제거된 후 Exchange 2013 또는 Exchange 2016 서버를 해제합니다.

    > [!IMPORTANT]
    > 자동 교환을 사용 중인 경우 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행하고 사용할 수 있도록 유지해야 합니다.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Exchange 2013/Exchange 2016을 통해 비즈니스용 Skype 서버 2019로

이 시나리오에서는 기존 비즈니스용 Skype 2015 서버를 비즈니스용 Skype 서버 2019로 마이그레이션하지만 Exchange 2013 또는 Exchange 2016에 남아 있습니다.

비즈니스용 Skype 서버 2015와 비즈니스용 Skype 서버 2019가 동일한 조직에 공존하는 경우 Exchange UM 및 클라우드 음성 메일과 원활하게 작동하여 음성 메일이 Exchange 사서함으로 올바르게 배달되도록 합니다. Exchange UM 또는 클라우드 음성 전송에서 음성메일을 처리하는지 여부는 사용자가 비즈니스용 Skype 서버 2015에 있는지 아니면 비즈니스용 Skype 서버 2019에 있는지에 따라 결정됩니다.

- 사용자가 비즈니스용 Skype 서버 2015에 있는 경우 Exchange UM은 음성 메일 메시지를 처리합니다.
- 사용자가 비즈니스용 Skype 서버 2019에 있는 경우 Cloud Voicemail은 음성 메일 메시지를 처리합니다.

Exchange UM 또는 Cloud Voicemail에서 음성 메일 메시지를 처리하는지 여부에 관계없이 메시지는 사용자의 Exchange 사서함에 저장됩니다.

비즈니스용 Skype 서버 2019로의 마이그레이션을 시작하기 전에 다음에 유의하세요.

- 클라우드 음성메일은 GA의 조직 자동 전화 교환 지원하지 않습니다. 사서함을 Cloud Voicemail로 이동한 경우 자동 전화 교환을 통해 계속 사용할 수 있도록 하려는 경우 UM 역할 또는 서비스를 실행하는 하나 이상의 Exchange 2013 또는 Exchange 2016 서버를 사용할 수 있도록 유지해야 합니다.
- 음성 메일로 전송된 통화는 녹음되는 클라우드 음성 메일로 전송됩니다. 통화가 종료된 후 음성 메일 메시지가 받는 사람의 사서함으로 전송됩니다. 인터넷 연결이 클라우드 음성메일을 지원하기에 충분할지 결정할 때 이 음성 트래픽을 고려해야 합니다.

다음은 이 마이그레이션을 완료하기 위한 높은 수준의 단계입니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치하고 구성합니다.
2. 새 비즈니스용 Skype 2019 서버를 포함하려면 하이브리드 배포 구성을 업데이트합니다.
3. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동합니다.
4. 클라우드 음성메일을 사용하기 위해 비즈니스용 Skype 서버 2019로 이동한 각 사용자에 대해 호스팅된 음성메일 정책을 설정할 수 있습니다.
5. 마지막 사용자가 벗어났을 때 비즈니스용 Skype 2015 서버를 해제합니다.

    > [!IMPORTANT]
    > 자동 교환을 사용 중인 경우 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행하고 사용할 수 있도록 유지해야 합니다.
