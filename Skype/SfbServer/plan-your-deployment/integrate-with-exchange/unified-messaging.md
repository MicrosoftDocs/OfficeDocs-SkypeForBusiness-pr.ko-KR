---
title: 비즈니스용 Skype의 Exchange 통합 메시징 통합 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: '요약: 비즈니스용 Skype 서버와 Exchange 2013 또는 2016의 통합을 계획하는 동안 이 항목을 검토합니다.'
ms.openlocfilehash: 1ae93ebeda07fccf6c9019d5bb78c63f7c722192
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810118"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>비즈니스용 Skype의 Exchange 통합 메시징 통합 계획

**요약:** 비즈니스용 Skype 서버와 Exchange 2013 또는 2016의 통합을 계획하는 동안 이 항목을 검토하세요.

비즈니스용 Skype 서버는 음성 메시징 및 전자 메일 메시징을 단일 메시징 인프라로 결합하기 위해 Exchange UM(통합 메시징)과의 통합을 지원합니다. Exchange에서 Exchange UM(통합 메시징)은 설치 및 구성할 수 있는 여러 Exchange 서버 역할 중 하나입니다.

Microsoft Exchange Server 2013 및 2016에서 Exchange UM은 Exchange 사서함 서버에서 서비스로 실행됩니다. 비즈니스용 Skype 서버 Enterprise Voice 배포의 경우 통합 메시징은 음성 메시징과 전자 메일 메시징을 사용자가 전화(Outlook Voice Access) 또는 컴퓨터에서 액세스할 수 있는 단일 저장소에 결합합니다. 통합 메시징 및 비즈니스용 Skype 서버는 함께 작동하여 전화 응답, Outlook Voice Access 및 자동 전화 Enterprise Voice.

> [!NOTE]
> Exchange UM은 비즈니스용 Skype 2019와 Exchange 2013 또는 Exchange 2016을 통합할 때 비즈니스용 Skype 서버에서 계속 사용할 수 있습니다. Exchange 2019의 지원이 변경되어 Exchange UM 통합이 클라우드 음성메일 및 클라우드 서비스 자동 전화 교환 강조되지 않습니다.  자세한 [내용은 클라우드 음성메일](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 서비스 계획 및 비즈니스용 Skype Exchange Server [마이그레이션을](../../../sfbhybrid/hybrid/plan-um-migration.md) 참조하세요.


이러한 기능을 On-premises Exchange UM 배포에서 지원하려면 다음 중 하나를 실행해야 합니다.

- Microsoft Exchange Server 2010 또는 최신 서비스 팩(비즈니스용 Skype 서버 2015만 해당)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> 이전에 알려진 Exchange 통합 메시징은 전화 시스템을 사용하여 음성 메일 메시지를 녹음한 다음 사용자의 Exchange 사서함에 그대로 두는 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 자세한 [내용은 클라우드 음성메일 서비스](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 계획을 참조하세요.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>통합 메시징 및 비즈니스용 Skype 서버의 기능

비즈니스용 Skype 서버는 Enterprise Voice UM(통합 메시징) 인프라를 사용하여 전화 응답, 전화 알림, 음성 액세스(음성 메일 포함) 및 자동 전화 교환 서비스를 제공합니다.

- **전화 응답** 전화 응답은 전화를 받지 못하거나 통화 중이던 사용자를 대신하여 음성 메시지를 수신하는 것입니다. 여기에는 개인 인사말을 재생하고, 메시지를 녹음하고, Exchange 사서함 서버에 저장된 사용자의 사서함으로 배달하기 위해 대기할 메시지를 전송하는 작업이 포함됩니다.

    발신자가 남긴 메시지는 사용자의 받은 편지함으로 라우팅됩니다. 발신자가 메시지를 남기지 않으면 부재 중 전화 알림이 사용자의 사서함에 저장됩니다. 그러면 사용자는 Microsoft Outlook 메시징 및 공동 작업 클라이언트, Outlook Web Access, Exchange ActiveSync 기술 또는 Outlook Voice Access를 사용하여 받은 편지함에 액세스할 수 있습니다. 통화의 제목과 우선 순위는 전자 메일과 유사한 방식으로 표시할 수 있습니다.

- **Outlook Voice Access** Outlook Voice Access 사용하면 Enterprise Voice 메일 뿐만 아니라 전화 통신 인터페이스에서 전자 메일, 일정 및 연락처를 비롯한 Exchange 받은 편지함에도 액세스할 수 있습니다. 구독자 액세스 번호는 Exchange UM 관리자가 할당합니다.

- **자동 회의** 자동 전화 교환은 외부 사용자가 회사 대표에게 연결하기 위해 전화를 걸 수 있는 전화 번호를 구성하는 데 사용할 수 있는 Exchange UM 기능입니다. 특히 이 기능은 외부 발신자가 메뉴 시스템을 탐색하는 데 도움이 되는 일련의 음성 안내 메시지를 제공합니다. 사용 가능한 옵션 목록은 Exchange UM 관리자가 Exchange UM 서버에서 구성합니다.

- **팩스 서비스** Exchange UM에는 사용자가 Exchange 사서함에서 수신 팩스를 받을 수 있도록 하는 팩스 기능이 포함되어 있습니다. 자세한 내용은 [통합](https://go.microsoft.com/fwlink/p/?linkId=135652) 메시징 설명서에서 Microsoft Exchange Server 참조하십시오.

    > [!NOTE]
    > Exchange UM 서버에서 제공하는 팩스 서비스는 Microsoft Exchange Server 2010, Exchange 2010 및 최신 서비스 팩, Exchange 2013 또는 Exchange 2016과 통합된 비즈니스용 Skype 서버 배포에서는 사용할 수 없습니다.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 구성 요소 및 토폴로지

### <a name="exchange-server-components"></a>Exchange Server 구성 요소

통합 메시징 및 비즈니스용 [Skype](#features-of-integrated-unified-messaging-and-skype-for-business-server) 서버의 기능에 설명된 Exchange UM 기능을 조직의 Enterprise Voice 사용자에게 제공하려면 사용자 사서함을 호스트하고 전자 메일 및 음성 메일에 대한 단일 저장소 위치를 제공하는 Microsoft Exchange 사서함 서버 및 클라이언트 액세스 서버를 배포해야 합니다. Exchange UM은 Exchange 사서함 및 클라이언트 액세스 서버에서 서비스로 실행됩니다.

Microsoft Exchange Server 2010의 Exchange UM 구성 요소에 대한 자세한 내용은 온-프레미스 Exchange UM 배포를 참조하여 [Lync Server 2013 Preview 음성 메일을 제공합니다.](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)

### <a name="supported-topologies"></a>지원되는 토폴로지

비즈니스용 Skype 서버 및 Exchange UM(통합 메시징)을 동일한 포리스트 또는 여러 포리스트에 배포할 수 있습니다. 배포가 여러 포리스트에 걸쳐 있는 경우 각 Exchange UM 포리스트에 대해 Exchange 통합 단계를 수행해야 합니다. 또한 각 Microsoft Exchange 포리스트가 각 Exchange UM 포리스트를 신뢰하도록 비즈니스용 Skype 서버 포리스트 및 비즈니스용 Skype 서버 포리스트를 신뢰하도록 구성해야 합니다. 이 포리스트 트러스트 외에도 모든 사용자에 대한 Exchange UM 설정을 비즈니스용 Skype 서버 포리스트의 사용자 개체에 대해 설정해야 합니다.

비즈니스용 Skype 서버는 Exchange UM 통합을 위해 다음과 같은 토폴로지가 지원됩니다.

- 단일 포리스트

- 단일 도메인(즉, 도메인이 하나인 단일 포리스트)입니다. 비즈니스용 Skype 서버, Microsoft Exchange 및 사용자는 모두 동일한 도메인에 있습니다.

- 여러 도메인(즉, 하나 이상의 하위 도메인이 있는 루트 도메인) 비즈니스용 Skype 서버 및 Microsoft Exchange 서버는 사용자를 만드는 도메인과 다른 도메인에 배포됩니다. Exchange UM 서버는 지원하는 비즈니스용 Skype 서버 풀의 다른 도메인에 배포할 수 있습니다.

- 다중 포리스트(즉, 리소스 포리스트) 비즈니스용 Skype 서버는 단일 포리스트에 배포된 다음 여러 포리스트에 분산됩니다. 사용자의 Exchange UM 특성을 비즈니스용 Skype 서버 포리스트로 복제해야 합니다.

    > [!NOTE]
    > Exchange는 여러 포리스트에 배포할 수 있습니다. 각 Exchange 조직은 사용자에게 Exchange UM을 제공하거나 Exchange UM을 비즈니스용 Skype 서버와 동일한 포리스트에 배포할 수 있습니다.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>프레미스 통합 메시징 및 비즈니스용 Skype 서버 통합에 대한 지침

다음은 배포할 때 고려해야 할 지침 및 모범 사례 Enterprise Voice.

> [!IMPORTANT]
> Exchange UM(통합 메시징)은 UCMA 4를 사용하는 경우 IPv6만 지원됩니다.

- 비즈니스용 Skype 서버 Standard Edition 서버 또는 프런트 엔드 풀을 배포합니다.

- Exchange 관리자와 함께 원활하고 성공적인 통합을 위해 각자가 수행할 작업을 확인합니다.

- 사용자가 Exchange UM을 사용할 수 있도록 설정할 각 Exchange UM(통합 메시징) 포리스트에 Exchange 사서함 서버 역할을 배포합니다. Exchange 서버 역할을 설치하는 데 대한 자세한 내용은 다음 Microsoft Exchange Server 참조하십시오.

    > [!IMPORTANT]
    > Exchange UM(통합 메시징)이 설치되면 자체 서명된 인증서를 사용하도록 구성됩니다. 자체 서명된 인증서를 사용하면 비즈니스용 Skype 서버와 Exchange UM이 서로 신뢰할 수 없습니다. 이 때문에 두 서버가 신뢰하는 인증 기관에 별도의 인증서를 요청해야 합니다.

- 비즈니스용 Skype 서버 및 Exchange UM이 서로 다른 포리스트에 설치되어 있는 경우 각 Exchange 포리스트가 각 Exchange 포리스트를 신뢰하도록 비즈니스용 Skype 서버 포리스트 및 비즈니스용 Skype 서버 포리스트를 신뢰하도록 구성합니다. 또한 일반적으로 스크립트 또는 ILM(Identity Lifecycle Manager)을 사용하는 크로스 포리스트 도구를 사용하여 비즈니스용 Skype 서버 포리스트의 사용자 개체에 대해 사용자의 Exchange UM 설정을 합니다.

- 필요한 경우 통합 메시징 서버를 관리할 Exchange 관리 콘솔을 설치합니다.

- Outlook Voice Access 및 자동 전화 교환을 위한 유효한 전화 번호를 받습니다.

- Microsoft Exchange Server 2010 SP1(서비스 팩 1) 이전 버전의 Exchange UM을 사용하는 경우 Exchange UM SIP URI 다이얼 플랜 및 다이얼 플랜의 Enterprise Voice 조정합니다.

### <a name="deploying-redundant-exchange-um-servers"></a>중복 Exchange UM 서버 배포

> [!IMPORTANT]
> 조직에 대해 구성한 각 Exchange UM SIP URI 다이얼 플랜에 대해 Exchange UM 서비스가 실행되는 서버를 두 개 이상 배포하는 것이 좋습니다. 확장된 용량을 제공하는 것 외에도 중복 서버를 배포하면 고가용성을 제공합니다. 서버 오류가 발생하면 비즈니스용 Skype 서버를 다른 서버로 장애 조치(fail over)하도록 구성할 수 있습니다.

다음 구성 예에서는 Exchange UM 복구를 제공합니다.

**예 1: Exchange UM 복구**

![Exchange UM 탄력성 다이어그램](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

예 1에서 Exchange UM 서버 1과 2는 Tukwila 데이터 센터에서 사용되고, Exchange UM 서버 3과 4는 Dublin 데이터 센터에서 사용됩니다. Tukwila에서 Exchange UM이 정전되는 경우 서버 1과 2에 대한 DNS(Domain Name System) A 레코드가 각각 서버 3과 4를 지정하도록 구성해야 합니다. Dublin에서 Exchange UM이 사용되지 않으면 서버 3과 4에 대한 DNS A 레코드가 각각 서버 1과 2를 지점으로 하도록 구성해야 합니다.

> [!NOTE]
> 예제 1에서는 각 Exchange UM 서버에 다음 인증서 중 하나를 할당해야 합니다. SAN(주체 대체 이름)에 와일드카드가 있는 인증서를 사용하거나 SAN에 있는 네 개의 Exchange UM 서버 각각에 대해 FQDN(정규화된 도메인 이름)을 넣습니다.

**예 2: Exchange UM 복구**

![Exchange UM 탄력성 다이어그램](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

예 2의 경우 정상 작동 조건에서 Exchange UM 서버 1과 2는 Tukwila 데이터 센터에서 사용되고, Exchange UM 서버 3과 4는 Dublin 데이터 센터에서 사용됩니다. 네 서버 모두 Tukwila 사용자의 SIP URI 다이얼 플랜에 포함되어 있지만 서버 3과 4는 사용하지 않도록 설정되어 있습니다. Tukwila에서 Exchange UM의 작동이 중단된 경우 예를 들어 Exchange UM 서버 1과 2가 사용할 수 없게 되고, Exchange UM 서버 3과 4를 사용할 수 있으므로 Tukwila Exchange UM 트래픽이 Dublin의 서버로 라우팅됩니다.

Exchange 2013에서 통합 메시징을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법에 대한 자세한 내용은  [Exchange 2013 UM과 Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372)통합을 참조합니다. 제공된 정보는 비즈니스용 Skype 서버에 동일하게 적용됩니다.

2010에서 통합 메시징을 사용하도록 설정하거나 사용하지 않도록 설정하는 Microsoft Exchange Server 자세한 내용은 다음을 참조합니다.

- [Exchange 2010에서 통합 메시징 사용](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Exchange 2010에서 통합 메시징을 사용하지 않도록 설정](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange 2019에 Exchange 통합 메시징이 더 이상 존재하지 않습니다. Exchange 2019가 있으며 이와 동등한 기능을 사용하려면 클라우드 음성 메시지 계획 서비스에 설명된 클라우드 음성메일 서비스를 사용해야 [합니다.](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)


## <a name="see-also"></a>참고 항목

[배포 프로세스 개요-프레미스 통합 메시징 및 비즈니스용 Skype 통합](deployment-overview.md)
