---
title: 비즈니스용 Skype 서버 및 Exchange Server 마이그레이션 계획
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: 이 항목에서는 기존 비즈니스용 Skype Server 또는 Exchange Server 배포를 최신 버전 또는 비즈니스용 Skype Online 또는 Exchange Online으로 마이그레이션하도록 결정할 때 고려해 야 할 사항에 대해 설명 합니다.
ms.openlocfilehash: 864a777c1fcb483df7f3779e9b105c1af551748e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237473"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>비즈니스용 Skype 서버 및 Exchange Server 마이그레이션 계획

이 항목에서는 기존 비즈니스용 Skype Server 또는 Exchange Server 배포를 최신 버전 또는 비즈니스용 Skype Online 또는 Exchange Online으로 마이그레이션하도록 결정할 때 고려해 야 할 사항에 대해 설명 합니다. 마이그레이션할 수 있는 항목, 조직에서 이미 설정한 시간에 따라 달라 집니다. 조직 자동 전화 교환 등의 일부 기능은 일반 가용성 (GA)에는 사용할 수 없지만, 이후 2018에서 제공 될 예정입니다.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype Server 2019의 기능 변경 사항

Exchange 2019 및 비즈니스용 Skype Server 2019을 사용 하면 지원 되는 기능을 몇 가지 변경 하 게 됩니다.

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019의 통합 메시징 지원

UM (통합 메시징)는 Exchange 2019에서 더 이상 사용 되지 않습니다. 즉, Exchange 2019에서 더 이상 다음과 같은 기능을 제공 하지 않습니다.

- 보이스 메일
- 자동 전화 교환

Exchange 2013 또는 Exchange 2016의 UM 서비스에 UM 역할을 배포한 경우 Exchange 2019으로 업그레이드 하려면 음성 메일을 Office 365의 Microsoft 클라우드 보이스 메일 서비스로 마이그레이션해야 합니다. 보이스 메일을 클라우드 음성 메일로 마이그레이션하려면 아래에 있는 [exchange 2013/Exchange 2016 및 비즈니스용 skype 2015을 exchange 2019 및 skype For business 2019 섹션을](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) 참조 하세요.
> [!IMPORTANT]
> Exchange 2013 또는 Exchange 2016 서버의 사용자에 게 UM 사용 가능 사서함이 있는 경우 비즈니스용 Skype 서버를 비즈니스용 Skype 2019 Server 용으로 업그레이드 하기 전에 Exchange 2019로 이동 하지 말고 사용자를 이동 하 여 음성 메시징 중단을 방지 해야 합니다.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 및 비즈니스용 Skype Server 2019의 PBX 지원

클라우드 보이스 메일은 Pbx (개인 브랜치 교환)에 음성 메시지 기능을 제공 하지 않습니다. Pbx에 Exchange Server 통합 메시징을 사용 하는 경우 Exchange Server 2019으로 업그레이드 하려면 [exchange의 세션 경계 컨트롤러에 대 한 지원 중단을 위해 블로그 이후 새 날짜에 나열 된 세 가지 옵션 중 하나를 채택 해야 합니다. ](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) [Exchange 팀 블로그에서](https://blogs.technet.microsoft.com/exchange/)온라인 통합 메시징.

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>비즈니스용 Skype Server 2019의 Exchange Online UM 지원

비즈니스용 Skype 서버 2019에서 Exchange Online UM에서 클라우드 보이스 메일로 이동 하 고 있습니다. 사용자가 비즈니스용 Skype 2019 서버로 이동 하면 호스팅 보이스 메일에 대해 구성 된 경우 자동으로 클라우드 음성 메일을 사용 하기 시작 합니다. 현재 Exchange Online UM을 사용 하 고 있는 경우에는 사용자를 비즈니스용 Skype Server 2019로 이동 하는 것 외에 다른 작업을 수행 하 여 클라우드 보이스 메일 사용을 시작할 필요가 없습니다. 그러나 알아야 할 몇 가지 기능은 다음과 같이 변경 되었습니다.

- 조직 자동 전화 교환 (Exchange Online UM의 자동 전화 교환에 대 한 대체)은 GA에는 제공 되지 않지만, 나중에 2018에서 사용할 수 있게 됩니다.
- 웹용 Outlook의 사용자 보이스 메일 설정은 클라우드 보이스 메일에 적용 되지 않습니다.

## <a name="on-premises-um-migration-scenarios"></a>온-프레미스 UM 마이그레이션 시나리오

Exchange 2019 및 클라우드 음성 메일로 사용자를 마이그레이션하는 데 사용할 수 있는 다음 시나리오를 지원 합니다. 이후 2018에서는 추가 버전의 Exchange 및 비즈니스용 Skype server에서 마이그레이션할 수 있는 추가 시나리오를 지원 합니다. 또한 조직 자동 전화 교환 등의 추가 기능을 제공 합니다.

- Exchange 2013/Exchange 2016 및 비즈니스용 Skype 서버 2015에서 Exchange 2019 및 비즈니스용 Skype Server 2019
- 비즈니스용 skype 서버 2015에서 Exchange 2013/Exchange 2016을 사용 하는 비즈니스용 Skype 서버 2019

다음 시나리오의 경우 현재 배포의 일부로 PBX 또는 SBC 구성이 존재 하지 않으며 온-프레미스 Exchange 서버에 UM이 구성 되어 있다고 가정 해야 합니다. 또한 이러한 각 솔루션은 사용자가 온-프레미스 비즈니스용 Skype 서버와 Office 365 간에 하이브리드 배포를 구성 하기로 결정 한 것으로 가정 합니다. 비즈니스용 Skype 하이브리드 배포에 대 한 자세한 내용은 [하이브리드 연결 계획](plan-hybrid-connectivity.md)을 참조 하세요.

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 및 비즈니스용 Skype 2015을 Exchange 2019 및 비즈니스용 Skype 2019

이 시나리오에서는 기존 Exchange 2013, Exchange 2016, 비즈니스용 Skype 2015 서버를 Exchange 2019 및 비즈니스용 Skype 2019으로 마이그레이션해야 합니다.

이 항목의 앞부분에서 설명한 것 처럼 Exchange 2019에는 더 이상 UM 서비스가 포함 되지 않습니다. 즉, Exchange 2019로 이동 하려는 모든 사서함에 대해 UM 서비스에서 제공 하는 기능을 바꾸려면 클라우드 보이스 메일을 사용 해야 합니다. 비즈니스용 Skype 서버 2019 및 it와 Office 365 간의 하이브리드 배포를 설정 하면 클라우드 보이스 메일이 이러한 Exchange UM 음성 메일 서비스를 대체 합니다.

모든 사용자가 보이스 메일 기능을 사용할 수 있도록 사용자를 Exchange 2019 및 비즈니스용 Skype 서버 2019로 이동 하는 순서는 매우 중요 합니다. 보이스 메일이 처리 되는 위치는 또한 Exchange 및 비즈니스용 Skype 사서함과 사용자가 어디에 있는지에 따라 결정 됩니다. 다음 표에서는 지원 되는 Exchange 및 비즈니스용 Skype 서버 조합 및 보이스 메일이 처리 되는 위치를 확인 합니다.

| 사서함 위치:            | 비즈니스용 Skype 서버 2015의 사용자 위치 | 비즈니스용 Skype 서버 2019의 사용자 위치  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 지원 되지 않음                           | 구름 보이스 메일                          |

비즈니스용 Skype 서버 2019 및 Exchange 2019으로 마이그레이션을 시작 하기 전에 다음 사항에 유의 하세요.

- 클라우드 보이스 메일은 GA에서 조직 자동 전화 교환을 지원 하지 않습니다. 자동 전화 교환을 통해 사서함을 클라우드 음성 메일로 이동 하려면 UM 역할 또는 서비스를 실행 하는 하나 이상의 Exchange 2013 또는 Exchange 2016 서버를 유지 해야 합니다.
- 사서함을 Exchange 2019로 이동 하기 전에 적어도 하나의 비즈니스용 Skype 2019 서버를 설정 하 **고** 사용자를 해당 서버로 이동 해야 합니다. 그렇지 않으면 해당 사서함이 보이스 메일 메시지를 수신할 수 없게 됩니다.
- 음성 메일로 전송 되는 통화는 녹음/녹화 될 클라우드 음성 메일로 전송 됩니다. 통화가 종료 된 후에는 온-프레미스 Exchange 2019 서버의 받는 사람 사서함에 보이스 메일 메시지가 전송 됩니다. 인터넷 연결이 클라우드 보이스 메일을 지원 하기에 충분 한지 여부를 결정할 때이 음성 트래픽을 고려해 야 합니다.

이 마이그레이션을 완료 하는 상위 수준의 단계는 다음과 같습니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치 하 고 구성 합니다.
2. 새로운 비즈니스용 Skype 2019 서버를 포함 하도록 하이브리드 배포 구성을 업데이트 합니다.
3. 새 서버에 Exchange Server 2019을 설치 하 고 구성 합니다.
4. Skype for Business 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동 합니다.
5. 클라우드 보이스 메일을 사용 하도록 각 사용자의 호스팅 보이스 메일 정책을 비즈니스용 Skype 서버 2019로 이동 하도록 설정 합니다.
6. Exchange 2013 또는 Exchange 2016 서버에서 Exchange 2019 서버로 사서함을 이동 합니다.
7. 마지막 사용자가 이동한 후에는 비즈니스용 Skype 2015 서버를 서비스 해제 합니다.
8. 사서함을 마지막으로 이동한 후에 Exchange 2013 또는 Exchange 2016 서버를 서비스 해제 합니다.

    > [!IMPORTANT]
    > 자동 전화 교환에 의존 하는 경우 적어도 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행 중이 고 사용 가능 하도록 유지 합니다.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>비즈니스용 skype 서버 2015에서 Exchange 2013/Exchange 2016을 사용 하는 비즈니스용 Skype 서버 2019

이 시나리오에서는 기존 Skype for Business 2015 서버를 비즈니스용 Skype Server 2019에 마이그레이션하고 있지만 Exchange 2013 또는 Exchange 2016에는 남아 있습니다.

비즈니스용 Skype Server 2015 및 비즈니스용 Skype Server 2019이 동일한 조직에 공존 하 고 있는 경우, exchange UM 및 클라우드 보이스 메일과 원활 하 게 연동 하 여 보이스 메일이 Exchange 사서함으로 올바르게 전달 되도록 합니다. Exchange UM 또는 클라우드 보이스 메일이 음성 메일을 처리 하는지 여부는 사용자가 비즈니스용 Skype Server 2015 또는 비즈니스용 Skype Server 2019에 있는지 여부에 따라 달라 집니다.

- 사용자가 비즈니스용 Skype 서버 2015에 있는 경우 Exchange UM은 보이스 메일 메시지를 처리 합니다.
- 사용자가 비즈니스용 Skype 서버 2019에 있는 경우, 클라우드 보이스 메일은 보이스 메일 메시지를 처리 합니다.

Exchange UM 또는 클라우드 보이스 메일이 보이스 메일 메시지를 처리 하는지 여부에 관계 없이 메시지가 사용자의 Exchange 사서함에 저장 됩니다.

비즈니스용 Skype 서버 2019으로 마이그레이션을 시작 하기 전에 다음 사항에 유의 하세요.

- 클라우드 보이스 메일은 GA에서 조직 자동 전화 교환을 지원 하지 않습니다. 자동 전화 교환을 통해 사서함을 클라우드 음성 메일로 이동 하려면 UM 역할 또는 서비스를 실행 하는 하나 이상의 Exchange 2013 또는 Exchange 2016 서버를 유지 해야 합니다.
- 음성 메일로 전송 되는 통화는 녹음/녹화 될 클라우드 음성 메일로 전송 됩니다. 통화가 종료 된 후에는 온-프레미스 Exchange server의 받는 사람 사서함에 보이스 메일 메시지가 전송 됩니다. 인터넷 연결이 클라우드 보이스 메일을 지원 하기에 충분 한지 여부를 결정할 때이 음성 트래픽을 고려해 야 합니다.

이 마이그레이션을 완료 하는 상위 수준의 단계는 다음과 같습니다.

1. 새 서버에 비즈니스용 Skype 서버 2019를 설치 하 고 구성 합니다.
2. 새로운 비즈니스용 Skype 2019 서버를 포함 하도록 하이브리드 배포 구성을 업데이트 합니다.
3. Skype for Business 2015 서버에서 비즈니스용 Skype 2019 서버로 사용자를 이동 합니다.
4. 클라우드 보이스 메일을 사용 하도록 각 사용자의 호스팅 보이스 메일 정책을 비즈니스용 Skype 서버 2019로 이동 하도록 설정 합니다.
5. 마지막 사용자가 이동한 후에는 비즈니스용 Skype 2015 서버를 서비스 해제 합니다.

    > [!IMPORTANT]
    > 자동 전화 교환에 의존 하는 경우 적어도 하나 이상의 Exchange 2013 또는 Exchange 2016을 실행 중이 고 사용 가능 하도록 유지 합니다.
