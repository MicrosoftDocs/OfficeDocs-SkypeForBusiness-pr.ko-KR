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
description: 이 항목에서는 기존 비즈니스용 Skype 서버 또는 Exchange Server 배포를 최신 버전으로 마이그레이션하거나 비즈니스용 Skype Online 또는 Exchange Online.
ms.openlocfilehash: e933f1754023daa0991961204224176c34254f7821168eedbc30956c0188410a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341074"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 항목에서는 기존 비즈니스용 Skype 서버 또는 Exchange Server 배포를 마이그레이션하기로 결정할 때 고려해야 할 Exchange Online. 마이그레이션할 수 있는 작업 및 언제는 조직에서 이미 설정한 설정에 따라 크게 달라 하게 됩니다.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 기능 변경 사항

Exchange 2019 및 비즈니스용 Skype 서버 2019를 통해 지원되는 기능을 일부 변경하고 있습니다.

### <a name="unified-messaging-support-in-exchange-2019"></a>2019년 Exchange 통합 메시징 지원

UM(통합 메시징)은 2019년 Exchange 더 이상 사용되지 않습니다. 즉, Exchange 더 이상 다음 기능을 제공하지 않습니다.

- 음성 메일
- 자동 전화 교환

Exchange 2013 또는 Exchange 2016에서 UM 서비스를 배포하고 Exchange 2019로 업그레이드하려면 음성 Microsoft 클라우드 음성 사서함 서비스로 음성 Microsoft 365 또는 Office 365. 음성 클라우드 음성 사서함 마이그레이션하려면 아래의 Exchange [2013/Exchange 2016 및 비즈니스용 Skype 2015에서 Exchange 2019 및 비즈니스용 Skype 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) 섹션을 참조하세요.
> [!IMPORTANT]
> Exchange 2013 또는 Exchange 2016 서버에 UM 사용 가능 사서함이 있는 경우 비즈니스용 Skype 서버를 비즈니스용 Skype 서버 2019로 업그레이드하고 음성 메시징이 정체되지 않도록 사용자를 이동하기 전에 UM 사용 가능 사서함을 Exchange 2019로 이동하지 않도록 합니다.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 PBX 지원

클라우드 음성 사서함 PBX(Private Branch Exchange)에 음성 메시징 기능을 제공하지 않습니다. PBX에 Exchange Server 통합 메시징을 사용 중이고 Exchange Server 2019로 업그레이드하려는 경우 Exchange Online [Exchange](https://blogs.technet.microsoft.com/exchange/)팀 블로그의 Exchange Online 통합 메시징에 대한 [](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) 지원 중단을 위한 새 날짜 블로그 게시물에 나열된 세 가지 옵션 중 하나를 채택해야 합니다.

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online 2019년 비즈니스용 Skype 서버 UM 지원

2019년 비즈니스용 Skype 서버 UM에서 Exchange Online UM으로 클라우드 음성 사서함. 사용자가 비즈니스용 Skype 2019 서버로 이동하면 호스팅된 음성 클라우드 음성 사서함 자동으로 사용이 시작됩니다. 현재 Exchange Online UM을 사용하는 경우 UM 사용을 시작하기 위해 사용자를 비즈니스용 Skype 서버 2019로 이동하는 것 외의 다른 클라우드 음성 사서함. 그러나 다음에 유의해야 하는 몇 가지 기능이 변경됩니다.

- 조직 자동 전화 교환 UM에서 자동 전화 교환을 대체하는 Exchange Online 합니다.
- 웹용 Outlook 사용자 음성 클라우드 음성 사서함.

## <a name="on-premises-um-migration-scenarios"></a>사내 UM 마이그레이션 시나리오

사용자를 2019 및 2019로 마이그레이션할 수 있도록 하는 다음과 같은 Exchange 지원 클라우드 음성 사서함.

- Exchange 2013/Exchange 2016 및 비즈니스용 Skype 서버 2015 - Exchange 2019 및 비즈니스용 Skype 서버 2019
- 비즈니스용 Skype 서버 2015- 비즈니스용 Skype 서버 2019 및 Exchange 2013/Exchange 2016

다음 시나리오에서는 현재 배포의 일부로 PBX 또는 SBC 구성이 존재하지 않는 것이 필요하며, UM이 현재 배포 서버에 구성되어 있는 것으로 Exchange 합니다. 또한 이러한 각 솔루션에서는 사용자가 해당 서버와 프레미스 서버 또는 비즈니스용 Skype 서버 간에 하이브리드 배포를 구성하기로 Microsoft 365 Office 365. 하이브리드 배포에 대한 비즈니스용 Skype 내용은 Plan [hybrid connectivity을 참조하십시오.](plan-hybrid-connectivity.md)

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 및 비즈니스용 Skype 2015 - Exchange 2019 및 비즈니스용 Skype 2019

이 시나리오에서는 기존 Exchange 2013, Exchange 2016 및 비즈니스용 Skype 2015 서버를 Exchange 2019 및 비즈니스용 Skype 2019로 마이그레이션할 수 있습니다.

이 항목의 앞부분에서 설명한 대로 Exchange 2019에는 더 이상 UM 서비스가 포함되어 없습니다. 즉, Exchange 2019로 이동하려는 사서함의 경우 클라우드 음성 사서함 UM 서비스에서 제공한 기능을 교체해야 합니다. 2019와 2019 및 비즈니스용 Skype 서버 또는 Microsoft 365 또는 Office 365 클라우드 음성 사서함 UM 음성 Exchange 대체합니다.

사용자를 Exchange 2019 및 비즈니스용 Skype 서버 2019로 이동하는 순서는 모든 사용자가 음성메일 기능을 계속 사용할 수 있도록 하는 데 중요합니다. 음성 메일이 처리되는 위치는 사서함 및 Exchange 비즈니스용 Skype 사용자에 따라 결정됩니다. 다음 표에서 지원되는 음성 Exchange 및 음성 비즈니스용 Skype 서버 처리 위치를 살펴 봐야 합니다.

| 에 있는 사서함:            | 비즈니스용 Skype 서버 2015에 있는 사용자 | 2019년 비즈니스용 Skype 서버 사용자  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 지원되지 않음                           | 클라우드 음성 메일                          |

비즈니스용 Skype 서버 2019 및 Exchange 마이그레이션을 시작하기 전에 다음에 유의해야 합니다.

- 클라우드 음성메일은 GA의 조직 자동 전화 교환 지원하지 않습니다. 자동 전화 클라우드 음성 사서함 사서함을 계속 사용할 수 있도록 사서함을 이동하려는 경우 UM 역할 또는 서비스를 실행하는 Exchange 2013 또는 Exchange 2016 서버를 하나 이상 유지해야 합니다.
- 사서함을 2019년 2019로 이동하기 전에 2019 비즈니스용 Skype 서버를 하나 이상 설정하고 사용자를 해당 서버로 이동해야 Exchange 있습니다.  이렇게 하지 못하면 사서함에서 음성 메일 메시지를 받을 수 없게 됩니다.
- 음성 메일로 전송된 통화는 녹음할 클라우드 음성 사서함 전송됩니다. 통화가 종료된 후 음성 메일 메시지가 2019년 8월 2019년 프레미스 서버의 받는 사람의 사서함으로 Exchange 전송됩니다. 인터넷 연결이 음성 트래픽을 지원하기에 충분한지 여부를 결정할 때 이 음성 트래픽을 클라우드 음성 사서함.

다음은 이 마이그레이션을 완료하기 위한 고급 단계입니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치하고 구성합니다.
2. 하이브리드 배포 구성을 업데이트하여 새 2019 비즈니스용 Skype 포함합니다.
3. 새 서버에 Exchange Server 2019를 설치하고 구성합니다.
4. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동합니다.
5. 비즈니스용 Skype 서버 2019로 이동한 각 사용자에 대해 호스팅된 음성 클라우드 음성 사서함.
6. Exchange 2013 또는 Exchange 2016 서버에서 Exchange 2019 서버로 사서함을 이동합니다.
7. 마지막 사용자가 비즈니스용 Skype 후 2015 서버를 해제합니다.
8. 마지막 사서함이 Exchange 2013 또는 Exchange 2016 서버를 해제합니다.

    > [!IMPORTANT]
    > 자동 회의를 사용 중인 경우 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행하고 사용할 수 있도록 합니다.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>비즈니스용 Skype 서버 2015- 비즈니스용 Skype 서버 2019 및 Exchange 2013/Exchange 2016

이 시나리오에서는 기존 비즈니스용 Skype 2015 서버를 비즈니스용 Skype 서버 2019로 마이그레이션하지만 Exchange 2013 또는 Exchange 2016에 남아 있습니다.

비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 서버 2019가 동일한 조직에 공존하는 경우 Exchange UM 및 클라우드 음성 사서함 원활하게 작동하여 음성 메일이 Exchange 사서함으로 올바르게 배달되도록 합니다. 음성 Exchange UM 또는 클라우드 음성 사서함 음성 비즈니스용 Skype 서버 2015 또는 2019에 있는지에 따라 비즈니스용 Skype 서버 있습니다.

- 사용자가 비즈니스용 Skype 서버 2015에 있는 Exchange UM에서 음성 메일 메시지를 처리합니다.
- 사용자가 2019년 비즈니스용 Skype 서버 있는 경우 클라우드 음성 사서함 메시지를 처리합니다.

UM 또는 Exchange 클라우드 음성 사서함 메시지 처리 여부에 관계없이 메시지는 사용자의 사서함에 Exchange 저장됩니다.

2019년으로 마이그레이션을 시작하기 비즈니스용 Skype 서버 다음에 유의하십시오.

- 클라우드 음성메일은 GA의 조직 자동 전화 교환 지원하지 않습니다. 자동 전화 클라우드 음성 사서함 사서함을 계속 사용할 수 있도록 사서함을 이동하려는 경우 UM 역할 또는 서비스를 실행하는 Exchange 2013 또는 Exchange 2016 서버를 하나 이상 유지해야 합니다.
- 음성 메일로 전송된 통화는 녹음할 클라우드 음성 사서함 전송됩니다. 통화가 종료 Exchange된 후 음성 메일 메시지가 받는 사람의 사서함에 전송됩니다. 인터넷 연결이 음성 트래픽을 지원하기에 충분한지 여부를 결정할 때 이 음성 트래픽을 클라우드 음성 사서함.

다음은 이 마이그레이션을 완료하기 위한 고급 단계입니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치하고 구성합니다.
2. 하이브리드 배포 구성을 업데이트하여 새 2019 비즈니스용 Skype 포함합니다.
3. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동합니다.
4. 비즈니스용 Skype 서버 2019로 이동한 각 사용자에 대해 호스팅된 음성 클라우드 음성 사서함.
5. 마지막 사용자가 비즈니스용 Skype 후 2015 서버를 해제합니다.

    > [!IMPORTANT]
    > 자동 회의를 사용 중인 경우 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행하고 사용할 수 있도록 합니다.
