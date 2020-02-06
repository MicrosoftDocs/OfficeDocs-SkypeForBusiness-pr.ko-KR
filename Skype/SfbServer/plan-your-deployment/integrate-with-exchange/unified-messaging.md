---
title: 비즈니스용 Skype에서 Exchange 통합 메시징 통합 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버와 Exchange 2013 또는 2016을 통합 하기 위해 계획 하는 동안이 항목을 검토 하세요.'
ms.openlocfilehash: 1ae6ad10f1e817b9ace0240c79d09251a23dd61c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815866"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>비즈니스용 Skype에서 Exchange 통합 메시징 통합 계획

**요약:** 비즈니스용 Skype 서버와 Exchange 2013 또는 2016을 통합 하기 위해 계획 하는 동안이 항목을 검토 하세요.

비즈니스용 Skype 서버는 음성 메시지 및 전자 메일 메시지를 단일 메시징 인프라로 결합 하기 위해 UM (Exchange 통합 메시징)과의 통합을 지원 합니다. Exchange에서 exchange UM (통합 메시징)은 설치 및 구성할 수 있는 여러 Exchange server 역할 중 하나입니다.

Microsoft Exchange Server 2013 및 2016에서는 Exchange UM을 Exchange 사서함 서버에서 서비스로 실행 합니다. 비즈니스용 Skype Server Enterprise Voice 배포의 경우, 통합 메시징은 사용자가 전화 (Outlook Voice Access) 또는 컴퓨터에서 액세스할 수 있는 단일 상점으로 음성 메시지 및 전자 메일 메시지를 결합 합니다. 통합 메시징 및 비즈니스용 Skype 서버를 함께 사용 하 여 엔터프라이즈 음성 사용자에 게 전화 접속, Outlook Voice Access, 자동 전화 교환 서비스를 제공 합니다.

> [!NOTE]
> Exchange UM은 비즈니스용 Skype 2019을 Exchange 2013 또는 Exchange 2016와 통합할 때 비즈니스용 Skype 서버 2019에서 계속 사용할 수 있습니다. Exchange 2019에서 지원 되는 변경 사항으로 인해 클라우드 보이스 메일과 클라우드 자동 전화 교환 기능 때문에 Exchange UM 통합이 더욱 강조 됩니다.  자세한 내용은 [클라우드 보이스 메일 서비스](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 및 [비즈니스용 Skype 서버 및 Exchange server 마이그레이션](../../../sfbhybrid/hybrid/plan-um-migration.md) 계획을 참조 하세요.


온-프레미스 Exchange UM 배포에서 이러한 기능을 지원 하려면 다음 중 하나를 실행 해야 합니다.

- Microsoft Exchange Server 2010 또는 최신 서비스 팩 (비즈니스용 Skype Server 2015에만 해당)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> 이전에는 알려진 대로 Exchange 통합 메시징을 사용할 수 없습니다. 휴대폰 시스템을 사용 하 여 보이스 메일 메시지를 기록한 다음 사용자의 Exchange 사서함에 녹음/녹화를 종료 하는 비즈니스용 Skype 서버 2019에 더 이상 제공 되지 않습니다. 자세한 내용은 [클라우드 보이스 메일 서비스 계획](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 을 참조 하세요.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>통합 통합 메시징의 기능 및 비즈니스용 Skype 서버

비즈니스용 Skype Server, Enterprise Voice는 Exchange UM (통합 메시징) 인프라를 사용 하 여 전화 응답, 통화 알림, 음성 액세스 (음성 메일 포함) 및 자동 전화 교환 서비스를 제공 합니다.

- **통화 응답** 통화 응답은 통화가 응답 하지 않거나 다른 사용자를 대신 하 여 음성 메시지를 받는 것을 말합니다. 여기에는 개인 인사말 재생, 메시지 기록, Exchange 사서함 서버에 저장 된 사용자의 사서함에 배달을 위해 대기 중인 메시지 제출 등이 포함 됩니다.

    발신자가 메시지를 떠나면 해당 메시지가 사용자의 받은 편지 함으로 라우팅됩니다. 발신자가 메시지를 남기지 않도록 선택 하면 부재 중 전화 알림이 사용자의 사서함에 저장 됩니다. 그러면 사용자가 Microsoft Outlook 메시지 및 공동 작업 클라이언트, Outlook Web Access, Exchange ActiveSync 기술 또는 Outlook Voice Access를 사용 하 여 받은 편지함에 액세스할 수 있습니다. 통화의 제목과 우선 순위는 전자 메일과 비슷한 방식으로 표시 될 수 있습니다.

- **Outlook Voice Access** Enterprise 음성 사용자는 Outlook Voice Access를 통해 음성 메일 뿐만 아니라 전화 통신 인터페이스의 전자 메일, 일정, 연락처를 비롯 한 Exchange 받은 편지함에 액세스할 수 있습니다. 구독자 액세스 번호는 Exchange UM 관리자가 할당 합니다.

- **자동 전화 교환** 자동 전화 교환은 외부 사용자가 회사 대표자에 게 전화를 걸 수 있도록 전화 번호를 구성 하는 데 사용할 수 있는 Exchange UM 기능입니다. 특히 외부 호출자가 메뉴 시스템 탐색에 도움을 주는 일련의 음성 메시지를 제공 합니다. 사용할 수 있는 옵션 목록은 Exchange um 관리자가 Exchange UM 서버에서 구성 합니다.

- **팩스 서비스** Exchange UM에는 사용자가 Exchange 사서함에서 수신 팩스를 받을 수 있도록 하는 팩스 기능이 포함 되어 있습니다. 자세한 내용은 Microsoft Exchange Server 설명서의 [통합 메시징을](https://go.microsoft.com/fwlink/p/?linkId=135652) 참조 하세요.

    > [!NOTE]
    > Exchange UM 서버에서 제공 하는 팩스 서비스는 최신 서비스 팩, Exchange 2013 또는 Exchange 2016을 사용 하 여 Microsoft Exchange Server 2010, Exchange 2010와 통합 된 비즈니스용 Skype 서버 배포에서 사용할 수 없습니다.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 온-프레미스 통합 메시징의 구성 요소 및 토폴로지

### <a name="exchange-server-components"></a>Exchange Server 구성 요소

[통합 메시징 및 비즈니스용 Skype Server의 기능](#features-of-integrated-unified-messaging-and-skype-for-business-server) 에 설명 된 Exchange UM 기능을 조직의 음성 사용자에 게 제공 하려면 사용자 사서함을 호스트 하 고 전자 메일 및 음성 메일에 대 한 단일 저장소 위치를 제공 하는 Microsoft Exchange 사서함 서버 및 클라이언트 액세스 서버를 배포 해야 합니다. Exchange UM은 Exchange 사서함 및 클라이언트 액세스 서버에서 서비스로 실행 됩니다.

Microsoft Exchange Server 2010의 Exchange UM 구성 요소에 대 한 자세한 내용은 온 [-프레미스 EXCHANGE Um 배포를 참조 하 여 Lync Server 2013 미리 보기 음성 메일을 제공](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) 하세요.

### <a name="supported-topologies"></a>지원 되는 토폴로지

동일한 포리스트나 여러 포리스트에 비즈니스용 Skype 서버와 UM (통합 메시징)을 배포할 수 있습니다. 구축이 여러 포리스트에 걸쳐 있는 경우 각 Exchange UM 포리스트에 대해 Exchange 통합 단계를 수행 해야 합니다. 또한 각 Exchange UM 포리스트를 신뢰 하도록 비즈니스용 skype 서버 포리스트와 비즈니스용 Skype 서버 포리스트를 신뢰 하도록 각 Microsoft Exchange 포리스트를 구성 해야 합니다. 이 포리스트 트러스트 외에도, 모든 사용자에 대 한 Exchange UM 설정은 비즈니스용 Skype 서버 포리스트의 사용자 개체에 설정 되어 있어야 합니다.

비즈니스용 Skype 서버는 Exchange UM 통합에 대해 다음 토폴로지를 지원 합니다.

- 단일 포리스트

- 단일 도메인 (즉 단일 도메인이 있는 단일 포리스트) 비즈니스용 Skype 서버, Microsoft Exchange 및 사용자는 모두 동일한 도메인에 있습니다.

- 여러 도메인 (즉, 하나 이상의 자식 도메인이 있는 루트 도메인) 비즈니스용 Skype 서버와 Microsoft Exchange server는 사용자를 만드는 도메인과 다른 도메인에 배포 됩니다. Exchange UM 서버는 지원 되는 비즈니스용 Skype 서버 풀의 다른 도메인에 배포할 수 있습니다.

- 다중 포리스트 (즉, 리소스 포리스트). 비즈니스용 Skype 서버는 단일 포리스트에 배포 되 고 사용자는 여러 포리스트에 걸쳐 분산 됩니다. 사용자의 Exchange UM 특성을 비즈니스용 Skype 서버 포리스트에 복제 해야 합니다.

    > [!NOTE]
    > Exchange는 여러 포리스트에 배포 될 수 있습니다. 각 Exchange 조직은 사용자에 게 Exchange UM을 제공 하거나 비즈니스용 Skype 서버와 동일한 포리스트에 Exchange UM을 배포할 수 있습니다.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>온-프레미스 통합 메시징과 비즈니스용 Skype 서버 통합에 대 한 지침

엔터프라이즈 음성을 구축할 때 고려해 야 할 지침 및 모범 사례는 다음과 같습니다.

> [!IMPORTANT]
> UM (통합 메시징)는 사용자가 참조 MA 4를 사용 하는 경우에만 IPv6을 지원 합니다.

- 비즈니스용 Skype Server Standard Edition server 또는 프런트 엔드 풀을 배포 합니다.

- Exchange 관리자와 협력 하 여 원활한 통합을 위해 각 사용자가 수행할 작업을 확인 합니다.

- Exchange UM에 대 한 사용자를 사용할 수 있도록 각 UM (통합 메시징) 포리스트에 Exchange 사서함 서버 역할을 배포 합니다. Exchange server 역할을 설치 하는 방법에 대 한 자세한 내용은 Microsoft Exchange Server 설명서를 참조 하세요.

    > [!IMPORTANT]
    > Exchange UM (통합 메시징)이 설치 되어 있으면 자체 서명 된 인증서를 사용 하도록 구성 됩니다. 자체 서명 된 인증서는 비즈니스용 Skype 서버와 Exchange UM을 서로 신뢰 하지 않으므로 두 서버에서 신뢰 하는 인증 기관에서 별도의 인증서를 요청 해야 합니다.

- 비즈니스용 Skype 서버와 Exchange UM이 다른 포리스트에 설치 되어 있는 경우 비즈니스용 skype Server 포리스트 및 비즈니스용 Skype 서버 포리스트를 신뢰 하도록 각 Exchange 포리스트를 구성 하 여 각 Exchange 포리스트를 신뢰 합니다. 또한 일반적으로 스크립트나 다중 포리스트 도구 (예: ILM (Id 수명 주기 관리자))를 사용 하 여 비즈니스용 Skype 서버 포리스트의 사용자 개체에 대 한 사용자의 Exchange UM 설정을 설정 합니다.

- 필요한 경우 Exchange 관리 콘솔을 설치 하 여 통합 메시징 서버를 관리 합니다.

- Outlook Voice Access 및 자동 전화 교환에 유효한 전화 번호를 얻으십시오.

- Microsoft Exchange Server 2010 SP1(서비스 팩 1) 이전 버전의 Exchange UM을 사용 하는 경우 Exchange UM SIP URI 다이얼 플랜 및 Enterprise Voice dial 요금제의 좌표 이름입니다.

### <a name="deploying-redundant-exchange-um-servers"></a>중복 Exchange UM 서버 배포

> [!IMPORTANT]
> 조직에 맞게 구성한 각 Exchange UM SIP URI 다이얼 플랜에 대해 Exchange UM 서비스가 실행 되는 최소 두 대의 서버를 배포 하는 것이 좋습니다. 확장 된 용량을 제공 하는 것 외에도 중복 서버를 배포 하면 가용성을 높일 수 있습니다. 서버 장애가 발생 하는 경우 비즈니스용 Skype 서버를 다른 서버로 장애 조치 하도록 구성할 수 있습니다.

다음 예제 구성은 Exchange UM 복원 력을 제공 합니다.

**예제 1: Exchange UM 복원**

![Exchange UM 탄성 다이어그램](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

예제 1에서 Exchange UM 서버 1 및 2는 Tukwila 데이터 센터에서 사용 하도록 설정 되 고 Exchange UM 서버 3 및 4는 더블린 데이터 센터에서 사용 하도록 설정 됩니다. Tukwila에서 Exchange UM이 중단 되는 경우 DNS (Domain Name System)에서 서버 1 및 2에 대 한 레코드가 각각 서버 3과 4를 가리키도록 구성 되어야 합니다. 더블린에 Exchange UM이 중단 되는 경우 서버 3 및 4에 대 한 DNS A 레코드는 각각 서버 1과 2를 가리키도록 구성 되어야 합니다.

> [!NOTE]
> 예를 들어, 각 Exchange UM 서버에 와일드 카드와 함께 인증서를 사용 하거나 san의 각 4 개 Exchange UM 서버에 대 한 FQDN (정규화 된 도메인 이름)을 지정 해야 합니다.

**예제 2: Exchange UM 복원**

![Exchange UM 탄성 다이어그램](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

예제 2의 일반 작동 조건에서 Exchange UM 서버 1 및 2는 Tukwila 데이터 센터에서 사용 하도록 설정 되며 Exchange UM 서버 3 및 4는 더블린 데이터 센터에서 사용 하도록 설정 됩니다. 4 대의 모든 서버가 Tukwila 사용자의 SIP URI 다이얼 플랜에 포함 되어 있습니다. 그러나 서버 3 및 4는 사용할 수 없습니다. 예를 들어 Tukwila에서 Exchange UM을 중단 하는 경우 exchange UM 서버 1 및 2를 사용 하지 않도록 설정 하 고 Exchange um 서버 3 및 4를 사용 하 여 Tukwila Exchange UM 트래픽이 더블린의 서버로 라우팅되도록 해야 합니다.

Exchange 2013에서 통합 메시징을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [exchange 2013 UM과 Lync 서버 통합](https://go.microsoft.com/fwlink/p/?LinkId=265372)을 참조 하세요. 제공 되는 정보는 비즈니스용 Skype 서버에 동일 하 게 적용 됩니다.

Microsoft Exchange Server 2010에서 통합 메시징을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

- [Exchange 2010에서 통합 메시징 사용](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Exchange 2010에서 통합 메시징 사용 안 함](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange 통합 메시징은 exchange 2019에 더 이상 존재 하지 않으며 Exchange 2019이 있는 경우 해당 기능을 사용 하려면 [클라우드 보이스 메일 서비스 계획](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)에서 설명 하는 클라우드 보이스 메일 서비스를 사용 해야 합니다.


## <a name="see-also"></a>참고 항목

[온-프레미스 통합 메시징과 비즈니스용 Skype 통합에 대 한 배포 프로세스 개요](deployment-overview.md)
