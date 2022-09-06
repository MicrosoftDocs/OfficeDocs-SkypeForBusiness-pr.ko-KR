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
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: 이 항목에서는 기존 비즈니스용 Skype 서버 또는 Exchange Server 배포를 최신 버전으로 마이그레이션하거나 온라인 또는 Exchange Online 비즈니스용 Skype 때 고려해야 할 사항에 대해 설명합니다.
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486993"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 항목에서는 기존 비즈니스용 Skype 서버 또는 Exchange Server 배포를 Exchange Online 마이그레이션할 때 고려해야 할 사항에 대해 설명합니다. 마이그레이션할 수 있는 항목과 시기는 조직에서 이미 설정한 항목에 따라 크게 달라집니다.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 2019의 기능 변경

Exchange 2019 및 비즈니스용 Skype 서버 2019에서는 지원 기능을 일부 변경하고 있습니다.

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019의 통합 메시징 지원

UM(통합 메시징)은 Exchange 2019에서 더 이상 사용되지 않습니다. 즉, Exchange 2019는 더 이상 다음 기능을 제공하지 않습니다.

- 음성 메일
- 자동 전화 교환

Exchange 2013에서 UM 역할을 배포했거나 Exchange 2016의 UM 서비스를 Exchange 2019로 업그레이드하려는 경우 음성 메일을 Microsoft 365 또는 Office 365 Microsoft 클라우드 음성 사서함 서비스로 마이그레이션해야 합니다. 음성 메일을 클라우드 음성 사서함 마이그레이션하려면 [Exchange 2013/Exchange 2016 및 2015 비즈니스용 Skype Exchange 2019 및 비즈니스용 Skype 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) 섹션을 살펴보세요.
> [!IMPORTANT]
> Exchange 2013 또는 Exchange 2016 서버의 사용자에게 UM 사용 사서함이 있는 경우 비즈니스용 Skype 서버를 비즈니스용 Skype 서버 2019로 업그레이드하기 전에 Exchange 2019로 이동하지 말고 음성 메시징 중단을 방지하기 위해 사용자를 해당 서버로 이동합니다.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 2019의 PBX 지원

클라우드 음성 사서함 PBX(Private Branch Exchange)에 음성 메시징 기능을 제공하지 않습니다. PBX용 Exchange Server 통합 메시징을 사용하고 Exchange Server 2019로 업그레이드하려는 경우 Exchange [팀 블로그](https://blogs.technet.microsoft.com/exchange/)의 Exchange Online [통합 메시징에서 세션 테두리 컨트롤러에 대한 지원을 중단하기 위해 블로그 게시물 새 날짜](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)에 나열된 세 가지 옵션 중 하나를 채택해야 합니다.

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>2019년 비즈니스용 Skype 서버 Exchange Online UM 지원

2019년 비즈니스용 Skype 서버 Exchange Online UM에서 클라우드 음성 사서함. 사용자가 비즈니스용 Skype 2019 서버로 이동하면 호스트된 음성 메일에 대해 구성된 경우 클라우드 음성 사서함 자동으로 사용하기 시작합니다. 현재 Exchange Online UM을 사용하는 경우 클라우드 음성 사서함 사용을 시작하기 위해 사용자를 비즈니스용 Skype 서버 2019로 이동하는 것 외에는 아무 작업도 수행할 필요가 없습니다. 그러나 주의해야 할 기능에는 몇 가지 변경 사항이 있습니다.

- 조직 자동 전화 교환은 Exchange Online UM에서 자동 전화 교환을 대체합니다.
- 웹용 Outlook의 사용자 음성 메일 설정은 클라우드 음성 사서함 적용되지 않습니다.

## <a name="on-premises-um-migration-scenarios"></a>온-프레미스 UM 마이그레이션 시나리오

Exchange 2019 및 클라우드 음성 사서함 둘 다로 사용자를 마이그레이션할 수 있는 다음 시나리오를 지원합니다.

- Exchange 2013/Exchange 2016 및 비즈니스용 Skype 서버 2015에서 Exchange 2019 및 비즈니스용 Skype 서버 2019로
- exchange 2013/Exchange 2016을 사용하여 2015~비즈니스용 Skype 서버 2019 비즈니스용 Skype 서버

다음 시나리오에서는 현재 배포의 일부로 PBX 또는 SBC 구성이 존재하지 않으며 온-프레미스 Exchange 서버에 UM이 구성되어 있다고 가정해야 합니다. 또한 이러한 각 솔루션은 온-프레미스 비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 배포를 구성하기로 결정했다고 가정합니다. 비즈니스용 Skype 하이브리드 배포에 대한 자세한 내용은 [하이브리드 연결 계획을 참조하세요](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 및 비즈니스용 Skype 2015에서 Exchange 2019 및 비즈니스용 Skype 2019로

이 시나리오에서는 기존 Exchange 2013, Exchange 2016 및 비즈니스용 Skype 2015 서버를 Exchange 2019 및 비즈니스용 Skype 2019로 마이그레이션하려고 합니다.

이 항목의 앞부분에서 설명한 것처럼 Exchange 2019에는 더 이상 UM 서비스가 포함되어 있지 않습니다. 즉, Exchange 2019로 이동하려는 사서함의 경우 클라우드 음성 사서함 사용하여 UM 서비스에서 제공한 기능을 대체해야 합니다. 비즈니스용 Skype 서버 2019를 설정하고 Microsoft 365 또는 Office 365 간에 하이브리드 배포를 설정하면 클라우드 음성 사서함 이러한 Exchange UM 음성 메일 서비스를 대체합니다.

사용자를 Exchange 2019 및 비즈니스용 Skype 서버 2019로 이동하는 순서는 음성 메일 기능을 모든 사용자가 계속 사용할 수 있도록 하는 데 중요합니다. 음성 메일이 처리되는 위치는 Exchange 및 비즈니스용 Skype 사서함 및 사용자가 있는 위치에 따라 결정됩니다. 다음 표를 참조하여 지원되는 Exchange 및 비즈니스용 Skype 서버 조합과 음성 메일이 처리되는 위치를 확인합니다.

| 사서함 위치:            | 비즈니스용 Skype 서버 2015에 있는 사용자 | 비즈니스용 Skype 서버 2019에 있는 사용자  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 지원되지 않음                           | 클라우드 음성 메일                          |

비즈니스용 Skype 서버 2019 및 Exchange 2019로 마이그레이션을 시작하기 전에 다음 사항에 유의하세요.

- 사서함을 Exchange 2019 **로 이동하기 전에** 하나 이상의 비즈니스용 Skype 2019 서버를 설정하고 사용자를 해당 서버로 이동해야 합니다. 이렇게 하지 않으면 해당 사서함이 음성 메일 메시지를 받을 수 없게 됩니다.
- 음성 메일로 전송된 통화는 녹음될 클라우드 음성 사서함 전송됩니다. 통화가 종료되면 음성 메일 메시지가 온-프레미스 Exchange 2019 서버의 받는 사람 사서함으로 전송됩니다. 인터넷 연결이 클라우드 음성 사서함 지원하기에 충분한지 여부를 결정할 때 이 음성 트래픽을 고려해야 합니다.

이 마이그레이션을 완료하는 대략적인 단계는 다음과 같습니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치하고 구성합니다.
2. 새 비즈니스용 Skype 2019 서버를 포함하도록 하이브리드 배포 구성을 업데이트합니다.
3. 새 서버에 Exchange Server 2019를 설치하고 구성합니다.
4. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동합니다.
5. 클라우드 음성 사서함 사용하도록 비즈니스용 Skype 서버 2019로 이동한 각 사용자에 대해 호스팅된 음성 메일 정책을 설정합니다.
6. Exchange 2013 또는 Exchange 2016 서버에서 Exchange 2019 서버로 사서함을 이동합니다.
7. 마지막 사용자가 제거된 후 비즈니스용 Skype 2015 서버의 서비스를 해제합니다.
8. 마지막 사서함이 제거된 후 Exchange 2013 또는 Exchange 2016 서버의 서비스를 해제합니다.


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>exchange 2013/Exchange 2016을 사용하여 2015~비즈니스용 Skype 서버 2019 비즈니스용 Skype 서버

이 시나리오에서는 기존 비즈니스용 Skype 2015 서버를 비즈니스용 Skype 서버 2019로 마이그레이션하려고 하지만 Exchange 2013 또는 Exchange 2016에 남아 있습니다.

비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 서버 2019가 동일한 조직에서 공존하는 경우 Exchange UM 및 클라우드 음성 사서함 원활하게 작동하여 음성 메일이 Exchange 사서함에 올바르게 배달되도록 합니다. Exchange UM 또는 클라우드 음성 사서함 음성 메일 처리 여부는 사용자가 비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버 2019에 있는지 여부에 따라 달라집니다.

- 사용자가 비즈니스용 Skype 서버 2015에 있는 경우 Exchange UM은 음성 메일 메시지를 처리합니다.
- 사용자가 비즈니스용 Skype 서버 2019에 있는 경우 클라우드 음성 사서함 음성 메일 메시지를 처리합니다.

Exchange UM 또는 클라우드 음성 사서함 음성 메일 메시지를 처리하는지 여부에 관계없이 메시지는 사용자의 Exchange 사서함에 저장됩니다.

비즈니스용 Skype 서버 2019로 마이그레이션을 시작하기 전에 다음 사항에 유의하세요.

- 음성 메일로 전송된 통화는 녹음될 클라우드 음성 사서함 전송됩니다. 통화가 종료되면 음성 메일 메시지가 온-프레미스 Exchange 서버의 받는 사람 사서함으로 전송됩니다. 인터넷 연결이 클라우드 음성 사서함 지원하기에 충분한지 여부를 결정할 때 이 음성 트래픽을 고려해야 합니다.

이 마이그레이션을 완료하는 대략적인 단계는 다음과 같습니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치하고 구성합니다.
2. 새 비즈니스용 Skype 2019 서버를 포함하도록 하이브리드 배포 구성을 업데이트합니다.
3. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동합니다.
4. 클라우드 음성 사서함 사용하도록 비즈니스용 Skype 서버 2019로 이동한 각 사용자에 대해 호스팅된 음성 메일 정책을 설정합니다.
5. 마지막 사용자가 제거된 후 비즈니스용 Skype 2015 서버의 서비스를 해제합니다.

