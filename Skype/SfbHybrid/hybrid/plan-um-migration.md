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
description: 이 항목에서는 기존 비즈니스용 Skype 서버 또는 Exchange Server 배포를 최신 버전으로 마이그레이션하거나 비즈니스용 Skype Online 또는 Exchange Online으로 마이그레이션할지 결정할 때 고려해 야 할 사항에 대해 설명 합니다.
ms.openlocfilehash: cb6d58cf839b6260bc8889817ea568528e4832f4
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359044"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획

이 항목에서는 기존 비즈니스용 Skype 서버 또는 Exchange Server 배포를 Exchange Online으로 마이그레이션하도록 결정할 때 고려해 야 할 사항에 대해 설명 합니다. 마이그레이션할 수 있는 작업과 조직에 이미 설정 되어 있는 상황에 따라 크게 달라 집니다.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 2019의 기능 변경 사항

Exchange 2019 및 비즈니스용 Skype 서버 2019를 사용 하는 경우 지원 되는 기능을 몇 가지 변경 하 게 됩니다.

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019의 통합 메시징 지원

Exchange 2019에서는 UM (통합 메시징)이 더 이상 사용 되지 않습니다. 즉, Exchange 2019은 더 이상 다음과 같은 기능을 제공 하지 않습니다.

- 음성 메일
- 자동 전화 교환

Exchange 2016 2013에서 UM 역할을 배포 했으며 exchange 2019로 업그레이드 하려는 경우 Microsoft 365 또는 Office 365에서 Microsoft 클라우드 음성 메일 서비스로 음성 메일을 마이그레이션해야 합니다. 음성 메일을 클라우드 음성 메일로 마이그레이션하려면 아래의 [exchange 2013/Exchange 2016 및 비즈니스용 skype 2015 To exchange 2019 및 비즈니스용 skype 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) 섹션을 확인 하세요.
> [!IMPORTANT]
> Exchange 2013 또는 Exchange 2016 서버의 사용자에 게 UM 사용 가능 사서함이 있는 경우 비즈니스용 Skype 서버를 비즈니스용 Skype 2019 서버로 업그레이드 하기 전에 Exchange 2019로 이동 하지 말고 음성 메시징 중단을 방지 하기 위해 사용자를 이동 해야 합니다.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype 서버 2019의 PBX 지원

클라우드 음성 메일은 Pbx (Private Branch exchange)에 음성 메시징 기능을 제공 하지 않습니다. Pbx에 대해 Exchange Server 통합 메시징을 사용 하는 경우 exchange Server 2019으로 업그레이드 하려면 [Exchange 팀 블로그에서](https://blogs.technet.microsoft.com/exchange/) [Exchange Online 통합 메시징의 세션 경계 컨트롤러에 대 한 지원 중단을 위해 블로그에 새](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) 블로그 게시 날짜에 나열 된 세 가지 옵션 중 하나를 채택 해야 합니다.

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019의 Exchange Online UM 지원

비즈니스용 Skype 서버 2019를 사용 하 여 Exchange Online UM에서 클라우드 음성 메일로 이동 하 고 있습니다. 사용자가 비즈니스용 Skype 2019 서버로 이동 하면 호스팅된 음성 메일에 대해 구성할 때 클라우드 음성 메일을 사용 하 여 자동으로 시작 됩니다. 현재 Exchange Online UM을 사용 하 고 있는 경우에는 사용자를 비즈니스용 Skype 서버 2019로 이동 하는 것 외에 다른 작업을 수행 하지 않아도 클라우드 음성 메일을 사용 하 여 시작할 수 있습니다. 그러나 알아야 할 몇 가지 기능이 몇 가지 있습니다.

- 조직 자동 전화 교환은 Exchange Online UM에서 자동 전화 교환에 대 한 대체입니다.
- 웹용 Outlook의 사용자 음성 메일 설정은 클라우드 음성 메일에 적용 되지 않습니다.

## <a name="on-premises-um-migration-scenarios"></a>온-프레미스 UM 마이그레이션 시나리오

Microsoft는 다음 시나리오를 지원 하기 때문에 사용자를 Exchange 2019 및 클라우드 음성 메일로 마이그레이션할 수 있습니다.

- Exchange 2013/Exchange 2016 및 비즈니스용 Skype 서버 2015-Exchange 2019 및 비즈니스용 Skype 서버 2019
- Exchange 2013/Exchange 2016가 있는 비즈니스용 skype 서버 2019 (비즈니스용 skype) 2015

다음 시나리오에서는 현재 배포의 일부로 PBX 또는 SBC 구성이 존재 하지 않으며, 온-프레미스 Exchange 서버에 UM이 구성 되어 있다고 가정 합니다. 이러한 각 솔루션은 또한 온-프레미스 비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 배포를 구성 하기로 결정 했다고 가정 합니다. 비즈니스용 Skype 하이브리드 배포에 대 한 자세한 내용은 [하이브리드 연결 계획](plan-hybrid-connectivity.md)을 참조 하십시오.

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 및 비즈니스용 Skype 2015에서 Exchange 2019 및 비즈니스용 Skype 2019

이 시나리오에서는 기존 Exchange 2013, Exchange 2016 및 비즈니스용 Skype 2015 서버를 Exchange 2019 및 비즈니스용 Skype 2019로 마이그레이션해야 합니다.

이 항목의 앞부분에서 설명한 것 처럼 Exchange 2019에는 UM 서비스가 더 이상 포함 되어 있지 않습니다. 즉, Exchange 2019로 이동 하려는 모든 사서함에 대해 클라우드 음성 메일을 사용 하 여 UM 서비스에서 제공 하는 기능을 교체 해야 합니다. 비즈니스용 Skype 서버 2019 및 it와 Microsoft 365 또는 Office 365 간의 하이브리드 배포를 설정 하면 클라우드 음성 메일이 이러한 Exchange UM 음성 메일 서비스를 대체 합니다.

모든 사용자가 음성 메일 기능을 계속 사용할 수 있도록 하려면 사용자를 Exchange 2019 및 비즈니스용 Skype 서버 2019로 이동 하는 것이 중요 합니다. 또한 음성 메일이 처리 되는 위치는 Exchange 및 비즈니스용 Skype 사서함과 사용자가 있는 위치에 따라 결정 됩니다. 다음 표를 참조 하 여 지원 되는 Exchange 및 비즈니스용 Skype 서버의 조합과 음성 메일이 처리 되는 위치를 확인할 수 있습니다.

| 사서함 위치:            | 비즈니스용 Skype 서버 2015에 있는 사용자 | 비즈니스용 Skype 서버 2019에 있는 사용자  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 지원되지 않음                           | 클라우드 음성 메일                          |

비즈니스용 Skype 서버 2019 및 Exchange 2019로의 마이그레이션을 시작 하기 전에 다음 사항에 유의 하세요.

- 클라우드 음성 메일은 GA에서 조직 자동 전화 교환을 지원 하지 않습니다. 자동 전화 교환에서 계속 사용할 수 있도록 클라우드 음성 메일로 사서함을 이동 하려는 경우에는 UM 역할 또는 서비스를 실행 하는 하나 이상의 Exchange 2013 또는 Exchange 2016 서버가 사용 가능 하도록 유지 해야 합니다.
- 사서함을 Exchange 2019로 이동 하기 전에 비즈니스용 Skype 2019 서버를 하나 이상 설정 하 **고** 사용자를 해당 서버로 이동 해야 합니다. 실패 하면 해당 사서함이 음성 메일 메시지를 받을 수 없게 됩니다.
- 음성 메일로 보낸 통화는 녹음 될 클라우드 음성 메일로 전송 됩니다. 통화가 종료 되 면 온-프레미스 Exchange 2019 서버의 받는 사람 사서함에 음성 메일 메시지가 전송 됩니다. 인터넷 연결이 클라우드 음성 메일을 지원 하기에 충분 한지 결정할 때이 음성 트래픽을 고려해 야 합니다.

이 마이그레이션을 완료 하는 높은 수준의 단계는 다음과 같습니다.

1. 새 서버에 비즈니스용 Skype 서버 2019을 설치 하 고 구성 합니다.
2. 새 비즈니스용 Skype 2019 서버를 포함 하도록 하이브리드 배포 구성을 업데이트 합니다.
3. 새 서버에 Exchange Server 2019을 설치 하 고 구성 합니다.
4. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동 합니다.
5. 비즈니스용 Skype 서버 2019로 이동 되는 각 사용자에 대해 호스팅된 음성 메일 정책을 설정 하 여 클라우드 음성 메일을 사용 합니다.
6. Exchange 2013 또는 Exchange 2016 서버에서 Exchange 2019 서버로 사서함을 이동 합니다.
7. 마지막 사용자가 이전에 이동한 후 비즈니스용 Skype 2015 서버를 제거 합니다.
8. 마지막 사서함이 이동 된 후에 Exchange 2013 또는 Exchange 2016 서버를 제거 합니다.

    > [!IMPORTANT]
    > 자동 전화 교환을 사용 하는 경우에는 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행 하 고 사용할 수 있도록 유지 합니다.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Exchange 2013/Exchange 2016가 있는 비즈니스용 skype 서버 2019 (비즈니스용 skype) 2015

이 시나리오에서는 기존 비즈니스용 Skype 2015 서버를 비즈니스용 Skype 서버 2019로 마이그레이션하려고 하지만 Exchange 2013 또는 Exchange 2016은 유지 하려고 합니다.

비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 서버 2019가 동일한 조직에 공존 하면 Exchange UM 및 클라우드 음성 메일과 원활 하 게 작동 하 여 음성 메일이 Exchange 사서함으로 올바르게 배달 되도록 합니다. Exchange UM 또는 클라우드 음성 메일에서 음성 메일을 처리 하는지 여부는 사용자가 비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버 2019에 있는지 여부에 따라 달라 집니다.

- 사용자가 비즈니스용 Skype 서버 2015에 있는 경우 Exchange UM은 음성 메일 메시지를 처리 합니다.
- 사용자가 비즈니스용 Skype 서버 2019에 있는 경우 클라우드 음성 메일은 음성 메일 메시지를 처리 합니다.

Exchange UM 또는 클라우드 음성 메일이 음성 메일 메시지를 처리 하는지 여부에 관계 없이 메시지는 사용자의 Exchange 사서함에 저장 됩니다.

비즈니스용 Skype 서버 2019로 마이그레이션을 시작 하기 전에 다음 사항에 유의 하세요.

- 클라우드 음성 메일은 GA에서 조직 자동 전화 교환을 지원 하지 않습니다. 자동 전화 교환에서 계속 사용할 수 있도록 클라우드 음성 메일로 사서함을 이동 하려는 경우에는 UM 역할 또는 서비스를 실행 하는 하나 이상의 Exchange 2013 또는 Exchange 2016 서버가 사용 가능 하도록 유지 해야 합니다.
- 음성 메일로 보낸 통화는 녹음 될 클라우드 음성 메일로 전송 됩니다. 통화가 종료 되 면 온-프레미스 Exchange 서버의 받는 사람 사서함에 음성 메일 메시지가 전송 됩니다. 인터넷 연결이 클라우드 음성 메일을 지원 하기에 충분 한지 결정할 때이 음성 트래픽을 고려해 야 합니다.

이 마이그레이션을 완료 하는 높은 수준의 단계는 다음과 같습니다.

1. 새 서버에 비즈니스용 Skype 서버 2019을 설치 하 고 구성 합니다.
2. 새 비즈니스용 Skype 2019 서버를 포함 하도록 하이브리드 배포 구성을 업데이트 합니다.
3. 비즈니스용 Skype 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동 합니다.
4. 비즈니스용 Skype 서버 2019로 이동 되는 각 사용자에 대해 호스팅된 음성 메일 정책을 설정 하 여 클라우드 음성 메일을 사용 합니다.
5. 마지막 사용자가 이전에 이동한 후 비즈니스용 Skype 2015 서버를 제거 합니다.

    > [!IMPORTANT]
    > 자동 전화 교환을 사용 하는 경우에는 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행 하 고 사용할 수 있도록 유지 합니다.
