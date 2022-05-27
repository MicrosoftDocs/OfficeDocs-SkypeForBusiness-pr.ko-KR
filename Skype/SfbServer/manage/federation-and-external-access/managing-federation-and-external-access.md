---
title: 'Lync Server 2013: 비즈니스용 Skype 서버 대한 페더레이션 및 외부 액세스 관리'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 지원되는 외부 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어하기 위해 외부 사용자 액세스를 사용하도록 설정하고 구성합니다.
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676220"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 페더레이션 및 외부 액세스 관리

에지 서버 또는 에지 풀을 배포하는 것은 외부 사용자를 지원하기 위한 첫 번째 단계입니다. 에지 서버 배포에 대한 자세한 내용은 [비즈니스용 Skype 서버 에지 서버 배포를](../../deploy/deploy-edge-server/deploy-edge-server.md) 참조하세요.

비즈니스용 Skype 서버 내부 배포를 설치하고 구성한 후 조직의 내부 사용자는 Active Directory Domain Services(AD DS)에 SIP 계정이 있는 다른 내부 사용자와 공동 작업할 수 있습니다. 협업에는 인스턴트 메시지 보내기 및 받기, 현재 상태 업데이트 및 회의 참가("모임"라고도 함)가 포함될 수 있습니다. 지원되는 외부 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어하기 위해 외부 사용자 액세스를 사용하도록 설정하고 구성합니다. 외부 사용자는 배포의 원격 사용자, 페더레이션된 사용자(IM(공용 인스턴트 메시징) 서비스 공급자의 지원되는 사용자 포함) 및 회의에 익명 참가자를 포함할 수 있습니다.

배포에 비즈니스용 Skype 서버 Edge 서버 또는 에지 풀이 포함된 경우 가능한 통신 유형의 범위가 크게 확장됩니다. 외부 사용자 액세스, 다른 SIP 페더레이션 도메인의 멤버와의 통신 및 SIP 페더레이션 공급자에 대한 많은 옵션이 있습니다. Edge Server 또는 Edge 풀을 설정한 후 외부 사용자 액세스 유형을 사용하도록 설정하고 외부 액세스를 제어하는 정책을 구성합니다. 비즈니스용 Skype 서버 비즈니스용 Skype 서버 제어판, 비즈니스용 Skype 서버 [Management Shell](../management-shell.md) 또는 둘 다를 사용하여 외부 사용자 액세스 및 정책을 사용하도록 설정하고 구성합니다.

> [!IMPORTANT]
> 외부 사용자 액세스를 위해 구성 및 정책을 디자인할 때 정책의 우선 순위와 정책이 적용되는 방식을 이해해야 합니다. 한 정책 수준에서 적용되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용되는 설정을 재정의할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.

조직에 대해 외부 사용자 액세스 지원을 이미 사용하도록 설정한 경우에도 기본적으로 외부 사용자 액세스(원격 사용자 액세스 및 페더레이션된 사용자 액세스 포함)를 지원하는 정책은 없습니다. 외부 사용자 액세스의 사용을 제어하려면 하나 이상의 정책을 구성해야 합니다. 다음 정책에서 지원되는 외부 사용자 액세스 유형을 지정합니다.

- **전역 정책**: 전역 정책은 에지 서버를 배포할 때 만들어집니다. 기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다. 전역 수준에서 외부 사용자 액세스를 지원하려면 하나 이상의 외부 사용자 액세스를 지원하도록 전역 정책을 구성합니다. 전역 정책은 조직의 모든 사용자에게 적용되지만 사이트 정책 및 사용자 정책이 전역 정책보다 우선합니다. 전역 정책을 삭제하는 경우에는 제거 하지 않습니다. 대신, 기본 설정으로 다시 설정합니다.

- **사이트 정책**: 하나 이상의 사이트 정책을 만들고 구성하여 특정 사이트에 대한 외부 사용자 액세스를 제한할 수 있습니다. 사이트 정책의 구성은 전역 정책을 재정의하지만 사이트 정책이 적용되는 특정 사이트에 대해서만 재정의합니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에게 적용되지만 사이트 정책 설정을 재정의하는 사용자 정책입니다.

- **사용자 정책**: 하나 이상의 사용자 정책을 만들고 구성하여 특정 사용자에 대한 원격 사용자 액세스에 대한 지원을 제한할 수 있습니다. 사용자 정책의 구성은 전역 및 사이트 정책을 재정의하지만 정책이 할당된 특정 사용자에 대해서만 재정의합니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에게 정책을 적용해야 정책이 효력을 발휘합니다.

구성 설정 및 만들거나 편집해야 하는 정책을 확인하려면 다음 결정 사항을 참조하세요.

**도메인의 내부 및 외부 사용자가 인스턴트 메시징, 웹 회의 및 오디오/비디오를 사용하여 공동 작업할 수 있도록 허용하시겠습니까?**

[원격 사용자 액세스를 제어하도록 정책을 구성](external-access-policies/configure-policies-to-control-remote-user-access.md)하고 [페더레이션 및 공용 IM 연결을 사용하거나 사용하지 않도록 설정하는](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 항목에 자세히 설명된 대로 설정을 구성합니다.

**익명 사용자가 참석하여 배포에서 사용자가 호스트하는 회의에 초대할 수 있도록 허용하시겠습니까?**

[익명 사용자를 지원하도록 회의 정책 할당](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) 및 회의 정책 [만들기](../conferencing/create-policies.md) 항목에 자세히 설명된 대로 설정을 구성합니다.

**사용자가 SIP 페더레이션 도메인 연락처와 통신할 수 있도록 허용하시겠습니까?**

페 [더레이션된 사용자 액세스를 제어하는 정책 구성, 페더레이션](external-access-policies/configure-policies-to-control-federated-user-access.md) [및 공용 IM 연결 사용 또는 사용 안 함](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), [조직에 대한 SIP 페더레이션 도메인 관리](sip-domains/manage-sip-federated-domains-for-your-organization.md) 항목에 자세히 설명된 대로 설정을 구성합니다.

**SIP 페더레이션 도메인과의 통신을 사용하도록 설정한 경우 SIP 페더레이션 자동 검색을 사용하도록 설정하시겠습니까?**

[페더레이션 파트너 검색 사용 또는 사용 안 함 항목에](access-edge/enable-or-disable-discovery-of-federation-partners.md) 설명된 대로 설정을 구성합니다.

**SIP 페더레이션 도메인과의 통신을 사용하도록 설정한 경우 보관을 사용하고 통신이 보관될 수 있음을 알리는 페더레이션된 연락처에 고지 사항을 보낼 수 있도록 설정하시겠습니까?**

페 [더레이션 파트너에게 보관 고지 사항 보내기 사용 또는 사용 안 함 항목에 설명된](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md) 대로 설정을 구성합니다.

**사용자가 공용 공급자와의 통신을 가능하게 하는 SIP 페더레이션 공급자와 통신할 수 있도록 허용하시겠습니까?**

[공용 사용자 액세스를 제어하는 정책 구성](external-access-policies/configure-policies-to-control-public-user-access.md), [페더레이션 및 공용 IM 연결 사용 또는 사용 안 함](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), [공용 SIP 페더레이션 공급자 만들기 또는 편집](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server) 항목에 자세히 설명된 대로 설정 구성

**사용자가 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 실행하는 호스트된 공급자인 SIP 페더레이션 공급자와 통신하도록 허용하시겠습니까?**

[페더레이션 및 공용 메신저 연결을 사용하거나 사용하지 않도록 설정하고](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) [호스트된 SIP 페더레이션 공급자를 만들거나 편집](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)하는 항목에 자세히 설명된 대로 설정을 구성합니다.

**배포가 분할(하이브리드라고도 함) 도메인에서 구성되나요? 여기서 일부 사용자는 온-프레미스 배포에 홈 서버를 사용하고 다른 사용자는 온라인 환경에서 홈 서버로 구성되나요?**

[페더레이션된 사용자 액세스를 제어하는 정책 구성, 페더레이션](external-access-policies/configure-policies-to-control-federated-user-access.md) [및 공용 메신저 연결을 사용하거나 사용하지 않도록 설정하고](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)[, 호스트된 SIP 페더레이션 공급자를 만들거나 편집](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)하는 항목에 자세히 설명된 대로 설정을 구성합니다.

조직에 대한 외부 사용자 액세스를 사용하도록 설정하지 않은 경우에도 외부 사용자 액세스 설정을 구성할 수 있습니다. 그러나 구성한 정책 및 기타 설정은 조직에서 외부 사용자 액세스를 사용하도록 설정한 경우에만 적용됩니다. 외부 사용자 액세스를 사용하지 않도록 설정하거나 외부 사용자 액세스 정책을 지원하도록 구성된 경우 외부 사용자는 사용자와 통신할 수 없습니다.

에지 배포는 외부 사용자 유형을 인증하고 에지 지원을 구성하는 방법에 따라 액세스를 제어합니다. 이 규칙의 예외는 회의 ID 및 회의를 만들고 참가자를 초대할 때 익명 참가자에게 전송되는 암호로 인증되는 익명 사용자입니다. 통신을 제어하기 위해 조직 내부 및 외부 사용자가 서로 통신하는 방법을 정의하는 하나 이상의 정책을 구성할 수 있습니다. 정책 및 설정에는 만들고 구성할 수 있는 기본 전역 정책, 사이트 정책 및 사용자 정책이 포함됩니다.
