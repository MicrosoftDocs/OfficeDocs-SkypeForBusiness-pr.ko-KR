---
title: 'Lync Server 2013: Lync Server 2013에 대한 페더링 및 외부 액세스 비즈니스용 Skype 서버'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 지원되는 외부 사용자가 내부 사용자와 공동 작업할 수 있는지 여부를 제어하기 위해 외부 사용자 액세스를 비즈니스용 Skype 서버 있습니다.
ms.openlocfilehash: aab0a4c5a3613f285b47a886819d524e37480341
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590142"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>페더링 및 외부 액세스 비즈니스용 Skype 서버

에지 서버 또는 에지 풀을 배포하는 것은 외부 사용자를 지원하기 위한 첫 번째 단계입니다. 에지 서버 배포에 대한 자세한 내용은 [Deploy Edge Server in 비즈니스용 Skype 서버.](../../deploy/deploy-edge-server/deploy-edge-server.md)

조직의 내부 사용자는 비즈니스용 Skype 서버 배포를 설치 및 구성한 후 AD DS(Active Directory 도메인 서비스)에 SIP 계정이 있는 다른 내부 사용자와 공동 작업을 할 수 있습니다. 공동 작업으로는 인스턴트 메시지 보내기 및 수신, 현재 상태 업데이트 및 회의 참가("모임"이라고도도 알려지기)가 포함됩니다. 지원되는 외부 사용자가 내부 사용자와 공동 작업할 수 있는지 여부를 제어하기 위해 외부 사용자 액세스를 비즈니스용 Skype 서버 있습니다. 외부 사용자에게는 배포의 원격 사용자, 페더러드 사용자(공용 IM(인스턴트 메시징) 서비스 공급자의 지원되는 사용자 포함) 및 회의의 익명 참가자가 포함됩니다.

배포에 비즈니스용 Skype 서버 에지 서버 또는 에지 풀의 설치가 포함된 경우 가능한 통신 유형의 범위가 크게 확장되어 외부 사용자 액세스에 대한 다양한 옵션, 다른 SIP 페더러티 도메인의 구성원과의 통신 및 SIP 페더러티드 공급자와의 통신이 가능합니다. 에지 서버 또는 에지 풀을 설정한 후 제공할 외부 사용자 액세스 유형을 사용하도록 설정하고 외부 액세스에 대해 제어하도록 정책을 구성합니다. 비즈니스용 Skype 서버 작업 요구 사항에 따라 비즈니스용 Skype 서버 제어판, 비즈니스용 Skype 서버 관리 셸 또는 [](../management-shell.md)둘 다를 사용하여 외부 사용자 액세스 및 정책을 사용하도록 설정하고 구성합니다. 



> [!IMPORTANT]  
> 외부 사용자 액세스에 대한 구성 및 정책을 디자인할 때 정책의 우선 순위와 정책이 적용되는 방법을 이해해야 합니다. 비즈니스용 Skype 서버 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.


조직에서 외부 사용자 액세스를 이미 지원하도록 설정한 경우에도 기본적으로 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯한 외부 사용자 액세스를 지원하는 정책은 구성되지 않습니다. 외부 사용자 액세스 사용을 제어하려면 하나 이상의 정책을 구성하고 각 정책에 대해 지원되는 외부 사용자 액세스 유형을 지정해야 합니다. 여기에는 다음 외부 액세스 정책이 포함됩니다.

  - **글로벌 정책**   글로벌 정책은 에지 서버를 배포할 때 작성됩니다. 기본적으로 글로벌 정책에서는 외부 사용자 액세스 옵션이 사용하도록 설정되지 않습니다. 글로벌 수준에서 외부 사용자 액세스를 지원하려면 외부 사용자 액세스 옵션 유형을 하나 이상 지원하도록 글로벌 정책을 구성합니다. 글로벌 정책은 조직의 모든 사용자에게 적용되지만, 사이트 정책과 사용자 정책이 글로벌 정책을 다시 정의합니다. 삭제한 글로벌 정책은 제거되는 것이 아니라 기본 설정으로 다시 설정됩니다.

  - **사이트 정책**   하나 이상의 사이트 정책을 만들고 구성하여 특정 사이트에 대한 외부 사용자 액세스 지원을 제한할 수 있습니다. 사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다. 예를 들어 글로벌 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 특정 사이트에 대해서는 원격 사용자 액세스를 사용하지 않도록 설정하는 사이트 정책을 지정할 수 있습니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에게 적용되지만, 사용자에게 사용자 정책을 할당하여 사이트 정책 설정을 다시 정의할 수 있습니다.

  - **사용자 정책**   하나 이상의 사용자 정책을 만들고 구성하여 특정 사용자에 대한 원격 사용자 액세스 지원을 제한할 수 있습니다. 사용자 정책의 구성은 사용자 정책이 할당된 특정 사용자에 한해 글로벌 정책 및 사이트 정책을 다시 정의합니다. 예를 들어 글로벌 정책 및 사이트 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자 액세스를 사용하지 않도록 설정하는 사용자 정책을 지정한 다음 특정 사용자에게 해당 사용자 정책을 할당할 수 있습니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에게 정책을 적용해야 정책이 효력을 발휘합니다.

구성 설정 및 만들거나 편집해야 하는 정책을 확인하려면 다음 결정 지점을 참조하세요.

**도메인의 내부 및 외부 사용자가 인스턴트 메시징, 웹 회의 및 오디오/비디오를 사용하여 공동 작업을 할 수 있도록 하려는 경우**

Configure policies to control remote [user acces](external-access-policies/configure-policies-to-control-remote-user-access.md)및 [Enable or disable federation and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)항목에 자세히 설명된 설정을 구성합니다.

**익명 사용자가 배포의 사용자가 호스팅하는 회의에 참가하고 초대를 하도록 허용할지 여부**

익명 사용자를 지원하도록 회의 [](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) 정책 할당 및 회의 정책 만들기 항목에 자세히 설명된 설정을 [구성합니다.](../conferencing/create-policies.md)

**사용자가 SIP 페더리트 도메인 연락처와 통신할 수 있도록 허용할지 여부**

Configure [policies to control federated user access,](external-access-policies/configure-policies-to-control-federated-user-access.md) [Enable or disable federation and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)및 [Manage SIP federated domains for your organization](sip-domains/manage-sip-federated-domains-for-your-organization.md)항목에 자세히 설명된 설정을 구성합니다.


**SIP 페더ation 도메인과의 통신을 사용하도록 설정한 경우 SIP 페더ation 자동 검색을 사용하도록 설정하고 싶습니까?**

Enable or [disable discovery of federation partners](access-edge/enable-or-disable-discovery-of-federation-partners.md)항목에 자세히 설명된 설정을 구성합니다.

**SIP 페더링 도메인과의 통신을 사용하도록 설정한 경우 보관을 사용하며 통신이 보관될 수 있습니다.**

Enable [or disable sending an Archiving disclaimer to federated partners in](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)(에서 보관 고지 사항 보내기 사용 또는 사용 안 하도록 설정) 항목에 자세히 설명된 설정을 구성합니다.

**사용자가 공용 공급자와 통신할 수 있도록 하는 SIP 페더리트 공급자와 통신할 수 있도록 허용할지 여부**

Configure policies to control public [user access,](external-access-policies/configure-policies-to-control-public-user-access.md) [Enable or disable federation and public IM connectivity,](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)and [Create or edit public SIP federated providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server) 항목에서 자세히 설명한 설정을 구성합니다.


**사용자가 온라인 또는 Microsoft 365 또는 Office 365 호스팅된 공급자인 SIP 페더 비즈니스용 Skype 통신할 수 있도록 비즈니스용 Skype?**

연결 및 공용 [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 연결 사용 또는 사용 안 하도록 설정 및 [호스팅된 SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)페더러티 공급자 만들기 또는 편집 항목에 자세히 설명된 설정을 구성합니다.

**배포가 분할(하이브리드라고도 하는) 도메인으로 구성되어 있으며, 일부 사용자에게는 홈 서버가 있으며, 다른 사용자는 온라인 환경에서 홈 서버를 통해 구성합니까?**

Configure [policies to control federated user access,](external-access-policies/configure-policies-to-control-federated-user-access.md) [Enable or disable federation and public IM connectivity,](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)and [Create or edit hosted SIP federated providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)항목에서 자세히 설명한 설정을 구성합니다.


조직에서 외부 사용자 액세스를 지원하도록 설정하지 않은 경우에도 외부 사용자 액세스를 제어하는 데 사용할 정책을 포함하여 외부 사용자 액세스 설정을 구성할 수 있습니다. 그러나 구성한 정책 및 기타 설정은 조직에서 외부 사용자 액세스를 사용하도록 설정한 경우에만 적용됩니다. 외부 사용자 액세스가 해제되어 있거나 지원하는 외부 사용자 액세스 정책이 구성되어 있지 않은 경우에는 외부 사용자가 조직의 사용자와 통신할 수 없습니다.

에지 배포에서는 에지 지원을 구성한 방법에 따라 외부 사용자 유형(전화 회의를 만들고 참가자를 초대할 때 익명 참가자에게 보낸 암호 키와 전화 회의 ID로 인증된 익명 사용자 제외)을 인증하고 액세스를 제어합니다. 통신을 제어하기 위해 하나 이상의 정책을 구성하고 배포 내부 사용자와 외부 사용자가 서로 통신하는 방법을 정의하는 설정을 구성할 수 있습니다. 이러한 정책과 설정에는 외부 사용자 액세스에 대한 기본 글로벌 정책과 특정 사이트 또는 사용자에 대해 하나 이상의 외부 사용자 액세스 유형을 사용하도록 설정하기 위해 만들고 구성할 수 있는 사이트 및 사용자 정책이 포함됩니다.

