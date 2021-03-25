---
title: 비즈니스용 Skype 서버에서 E9-1-1용 SIP 트렁크 디자인
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 비즈니스용 Skype 서버 2013에서 SIP 트렁크 공급자를 사용하는 E9-1-1 배포에 대한 SIP 트렁크 토폴로지 Enterprise Voice.
ms.openlocfilehash: 8685b3263b9e3b6f98bc94e190ac9dd8207348df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112694"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 E9-1-1용 SIP 트렁크 디자인
 
비즈니스용 Skype 서버 2013에서 SIP 트렁크 공급자를 사용하는 E9-1-1 배포에 대한 SIP 트렁크 토폴로지 Enterprise Voice.
  
비즈니스용 Skype 서버는 SIP 트렁크를 사용하여 긴급 통화를 E9-1-1 서비스 공급자에 연결합니다. 하나의 중앙 사이트, 여러 중앙 사이트 또는 각 분기 사이트에서 E9-1-1에 대한 긴급 서비스 SIP 트렁크를 설정할 수 있습니다. 그러나 발신자 사이트와 긴급 서비스 SIP 트렁크를 호스팅하는 사이트 간의 WAN 링크를 사용할 수 없는 경우 연결이 끊어진 사이트에서 사용자가 걸은 통화에는 로컬 PSTN(Public Switched Telephone Network) 게이트웨이를 통해 ECRC로 통화를 라우팅하는 사용자의 음성 정책에 특수한 전화 사용 레코드가 필요합니다. 통화 허용 제어 동시 통화 제한이 적용되는 경우에도 마찬가지입니다.
  
비즈니스용 Skype 서버 환경에서 SIP 트렁크를 구현하는 방법에는 두 가지가 있습니다.
  
- SIP 트렁크 공급자와 통신하기 위해 공개적으로 라우트된 해당 인터페이스를 사용하는 다중homed 중재 서버를 사용합니다.
    
- SBC(On-premises Session Border Controller)를 사용하여 중재 서버와 SIP 트렁크 공급자의 서비스 간에 보안 경계 지점을 제공합니다.
    
두 번째 방법을 사용할 경우 선택한 SBC 작성 및 모델이 인증되었는지 확인하고 PIDF-LO(Presence Information Data Format Location Object) 위치 데이터를 SIP INVITE의 일부로 전달하도록 지원하는지 확인합니다. 그렇지 않으면 해당 위치 정보가 제거된 상태로 통화가 긴급 서비스 제공자에게 도착합니다. 인증된 SBC에 대한 자세한 내용은 ["Microsoft Lync에](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 대해 자격을 갖춘 인프라" 및 "비즈니스용 Skype의 전화 통신 [인프라"를 참조하세요.](../../../SfbPartnerCertification/certification/infra-gateways.md) 
  
E9-1-1 서비스 공급자는 중복을 위해 한 쌍의 SC에 대한 액세스를 제공합니다. 중재 서버 토폴로지 및 통화 라우팅 구성과 관련하여 몇 가지 결정을 내릴 수 있습니다. 두 SBC를 같은 피어로 처리하고 두 SBC 간의 통화에 라운드 로빈 라우팅을 사용할지 아니면 SBC 하나를 기본으로 지정하고 다른 SBC를 보조로 지정합니까?
  
비즈니스용 Skype 서버에서 SIP 트렁크를 배포하는 데 대한 자세한 내용은 [비즈니스용 Skype 서버의 SIP](sip-trunking.md)트렁크를 참조하세요. 다음 질문은 E9-1-1을 위한 SP 트렁크 배포 방법을 결정하는 데 유용합니다.
  
 **SIP 트렁크를 배포할 때 사용할 연결(전용 임대 연결 또는 공유 인터넷 연결)**
  
> 긴급 통화는 항상 연결되어야 합니다. 따라서 전용선을 사용하면 연결이 네트워크의 다른 트래픽에 의해 선취되지 않으며, QoS(서비스 품질)를 구현할 수 있습니다. 공용 인터넷을 통해 긴급 서비스 제공자에 연결할 경우 긴급 통화의 기밀성을 보장해야 하며 IPSec 암호화가 필요합니다. 
    
 **E9-1-1 배포는 내재해성을 위해 설계합니까?**
  
> 이 배포는 긴급 솔루션이므로 복구가 중요합니다. 내재해성 위치에 기본 및 보조 중재 서버 및 SIP 트렁크를 배포합니다. 지원되는 사용자에게 가장 가까운 기본 중재 서버를 배포하고 다른 지리적 위치에 있는 보조 중재 서버를 통해 장애 조치(failover) 통화를 라우팅하는 것이 좋습니다. 
    
 **각 지점에 대해 별도의 SIP 트렁크를 배포할지 여부**
  
> 비즈니스용 Skype 서버는 지점에서 음성 탄력성 처리를 위한 몇 가지 전략을 제공합니다. 예를 들어, 탄력적인 데이터 네트워크가 있는 경우, 각 분기에 SIP 트렁크를 배포하거나, 정전 시 로컬 게이트웨이로 통화를 푸시하는 등의 여러 가지 전략이 있습니다. 자세한 내용은 [비즈니스용 Skype 서버의 SIP 트렁크를 참조하세요.](sip-trunking.md)
    
 **CAC(통화 허용 제어)가 사용하도록 설정되는지 여부**
  
> 비즈니스용 Skype 서버는 일반 통화와 다른 응급 통화를 처리하지 않습니다. 따라서 대역폭 관리 또는 CAC(통화 허용 제어)가 E9-1-1 구성에 좋지 않은 영향을 줄 수 있습니다. CAC가 사용하도록 설정되어 있으며 긴급 통화를 라우팅하는 링크에서 구성된 제한을 초과한 경우, 긴급 통화가 차단되거나 로컬 PSTN 게이트웨이로 라우팅될 수 있습니다. 이 항목의 앞 부분에 표시된 것처럼 이러한 통화는 위치 데이터를 포함하지 않으며 수동으로 ECRC로 라우팅해야 합니다.
