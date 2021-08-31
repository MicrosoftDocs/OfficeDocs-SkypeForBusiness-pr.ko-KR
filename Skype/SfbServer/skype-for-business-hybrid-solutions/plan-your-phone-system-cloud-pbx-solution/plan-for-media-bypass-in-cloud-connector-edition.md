---
title: 클라우드 커넥터 버전에서 미디어 바이패스 계획
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 이 항목을 읽고 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 구현하기 위한 계획 고려 사항을 검토합니다. 미디어 우회 배포에 대한 자세한 내용은 Deploy media bypass in Cloud Connector Edition를 참조하세요.
ms.openlocfilehash: 182defd3d1fb7acf1fb2ba6fcc4e15e88e24a82c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729747"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>클라우드 커넥터 버전에서 미디어 바이패스 계획
 
이 항목을 읽고 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 구현하기 위한 계획 고려 사항을 검토합니다. 미디어 우회 배포에 대한 자세한 내용은 [Cloud Connector Edition에서 미디어 우회 배포를 참조하세요.](deploy-media-bypass-in-cloud-connector.md)
  
미디어 우회를 통해 클라이언트는 PSTN(Public Switched Telephone Network) 다음 홉(게이트웨이 또는 SBC(Session Border Controller))으로 직접 미디어를 보내고 미디어 경로에서 Cloud Connector Edition 구성 요소를 제거할 수 있습니다.
  
미디어 우회는 대기 시간, 패킷 손실 가능성 및 잠재적인 오류 지점 수를 줄여 음성 품질을 향상시킬 수 있습니다. 우회된 통화에 대한 미디어 처리를 제거하면 클라우드 커넥터의 부하가 감소하여 동시 통화 수가 증가하고 확장성이 향상될 수 있습니다. 
  
 미디어 처리 작업에서 클라우드 커넥터를 비우면 인프라에 필요한 Cloud Connector 어플라이언스 수가 줄어들 수 있으므로 가능하면 미디어 우회를 사용하도록 설정해야 합니다.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>미디어 우회가 미디어 및 신호 경로에 미치는 영향

신호는 미디어 우회와 동일한 경로를 사용하나 미디어 흐름은 서로 다릅니다. 다음 다이어그램은 미디어 우회가 있는 경우와 없는 토폴로지의 미디어 및 신호 경로를 보여 주며, 
  
예를 들어 미디어 우회를 적용하지 않는 다음 토폴로지에서 비즈니스용 Skype 클라이언트는 외부 번호로 PSTN 통화를 걸면 SIP 신호가 최종 사용자 음성 정책에 따라 신호 트래픽을 Microsoft 365 Office 365 또는 외부 번호로 전달됩니다. 클라우드 커넥터 사용자의 경우 음성 정책은 신호 트래픽을 클라우드 커넥터 에지 서버로 전달한 다음 신호 트래픽을 클라우드 커넥터 중재 서버를 통해 PSTN SBC(Session Border Controller) 또는 게이트웨이로 라우팅합니다. 미디어는 비즈니스용 Skype 클라이언트에서 클라우드 커넥터 중재 서버로 흐르고 다음 다이어그램과 같이 SBC 또는 게이트웨이로 흐름됩니다.
  
**미디어 우회 없이 미디어 및 신호 경로**

![신호 미디어 우회 없이](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
PSTN의 인바운드 통화는 역방향의 동일한 신호 경로를 사용 합니다. 내부 사용자의 경우 미디어는 최종적으로 비즈니스용 Skype 클라이언트와 클라우드 커넥터 중재 서버, SBC 또는 게이트웨이 간에 흐름됩니다.
  
미디어 우회를 사용하는 다음 토폴로지에서는 신호가 동일한 경로를 사용하지만 다음 다이어그램과 같이 미디어는 비즈니스용 Skype 클라이언트와 SBC 또는 게이트웨이 간에 직접 흐르게 됩니다.
  
**미디어 우회를 통해 미디어 및 신호 경로**

![signaling 미디어 우회를 통해.](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>다중 사이트 시나리오 및 미디어 우회

미디어 우회는 단일 Cloud Connector 어플라이언스를 사용하여 여러 사이트에 전화 통신 서비스를 제공하려는 경우도 유용합니다. 클라우드 커넥터는 원본 또는 대상 번호를 기준으로 통화를 라우팅할 수 없습니다. 대부분의 기업은 라우팅 결정을 내리기 위해 클라우드 커넥터 뒤에 SBC 또는 게이트웨이를 배포합니다. 이 시나리오의 미디어 우회는 다음 다이어그램과 같이 클라이언트와 중앙 SBC 또는 게이트웨이 간의 홉을 제거합니다.
  
**다중 사이트 응용 프로그램**

![클라우드 커넥터 멀티사이트 예제입니다.](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP 트래픽은 취리히의 사용자로부터 Microsoft 365 또는 Office 365.
    
2. 그런 다음 트래픽은 사용자 음성 라우팅 정책에 지정된 암스테르담의 클라우드 커넥터 어플라이언스로 라우팅됩니다.
    
3. 암스테르담의 클라우드 커넥터 어플라이언스가 암스테르담의 중앙 게이트웨이로 SIP 트래픽을 전송합니다.
    
4. 암스테르담의 중앙 게이트웨이는 적절한 라우팅 결정을 내렸다가 취리히의 SBC 또는 게이트웨이로 트래픽을 보내고, 미디어는 암스테르담의 비즈니스용 Skype 클라이언트와 SBC 또는 게이트웨이 간에 직접 흐르게 됩니다.
    
   이 방법을 사용하면 클라우드 커넥터가 중앙 집중화된 클라우드 커넥터 배포당 더 많은 사용자를 지원할 수 있습니다. 클라우드 커넥터가 미디어 경로에서 제거된 경우에도 중앙 집중식 다중 사이트 시나리오 미디어에서 중앙 SBC 또는 게이트웨이를 통과하는 데 필요한 경우 WAN을 두 번 트래버스할 수 있습니다.
  
클라이언트가 아웃바운드 통화를 걸고 회사 네트워크 외부에 있는 경우 미디어 트래픽은 다음 다이어그램과 같이 클라우드 커넥터의 Edge 및 중재 서버와 취리히와 암스테르담 간의 WAN 링크를 통해 전달됩니다.
  
![클라우드 커넥터 멀티사이트 예제 2.](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>미디어 우회에 지원되는 클라이언트

미디어 우회의 첫 번째 릴리스에서는 비즈니스용 Skype 16.0.7870.2020 이상에 엔터프라이즈용 Microsoft 365 앱 클라이언트에 있는 Windows 2016 Windows Client만 지원됩니다. 고객은 현재, 지연 또는 첫 번째 릴리스 지연 채널을 사용할 수 있습니다. 
  
> [!NOTE]
> 클라이언트 VPN 솔루션을 비즈니스용 Skype 클라이언트를 사용하는 경우 미디어 우회는 VPN 분할 터널 구성에서만 지원됩니다. 
  
릴리스 채널에 대한 자세한 내용은 에 대한 업데이트 채널 [개요를 엔터프라이즈용 Microsoft 365 앱.](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)
  
다른 채널에 있는 클라이언트의 현재 릴리스 버전은 에 대한 업데이트에 대한 릴리스 [정보를 엔터프라이즈용 Microsoft 365 앱.](/officeupdates/release-notes-office365-proplus) 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>미디어 우회를 사용하여 클라우드 커넥터 용량 고려 사항

미디어 우회 없이 하드웨어에 따라 클라우드 커넥터 어플라이언스에서 미디어가 중재 서버를 통과해야 하는 동시 통화를 50~500개까지 처리할 수 있습니다. 자세한 내용은 [Plan for 비즈니스용 Skype 클라우드 커넥터 버전.](./plan-skype-for-business-cloud-connector-edition.md) 
  
미디어 우회를 사용하도록 설정하면 지원되는 버전의 내부 클라이언트가 중재 서버를 사용하지 않습니다. 따라서 내부 클라이언트 수가 크게 증가할 수 있습니다. 
  
위에서 설명한 대로 외부 클라이언트 또는 지원되지 않는 클라이언트는 미디어에 클라우드 커넥터 Edge 및 중재 서버를 사용하게 됩니다. 사이트에 배치해야 하는 클라우드 커넥터 어플라이언스 수를 계산할 때 지원되지 않는 클라이언트의 외부 사용자 및 사용자의 트래픽을 고려해야 합니다.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>클라우드 커넥터에서 항상 우회 모드를 지원

클라우드 커넥터는 항상 우회 모드만 지원됩니다. In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.
  
항상 우회는 내부 클라이언트가 있는 모든 PSTN 통화에 대해 원본 또는 대상 지점으로 미디어 우회가 시도됩니다. 클라이언트가 내부인지 외부인지 확인하기 위해 중재 서버 가상 컴퓨터의 웹 사이트가 사용됩니다. 클라이언트가 사이트에 도달할 수 있는 경우 내부 및 미디어 우회가 사용됩니다. 클라이언트가 사이트에 도달할 수 없는 경우(예: 클라이언트가 홈 네트워크에 있는 경우) 미디어 우회가 사용되지 않습니다. 
  
항상 우회를 사용하려면 PSTN 사이트 내의 PSTN 게이트웨이와 사용자 간의 방해되지 않은 연결이 필요합니다. 
  
자세한 내용은 [Plan for 비즈니스용 Skype 클라우드 커넥터 버전.](./plan-skype-for-business-cloud-connector-edition.md) 
  
예를 들어 아래 다이어그램에서 유럽 사용자는 암스테르담의 세 SC(Session Border Controller)에 잘 연결되어 있어야 하지만 미국 서부 사용자는 시애틀의 두 SBC에 잘 연결되어 있어야 합니다. 잘 연결되면 SBC 또는 게이트웨이와 동일한 네트워크 사이트에 위치하거나 적절한 대역폭을 사용하는 WAN 링크를 통해 연결됩니다.
  
![클라우드 커넥터 용량.](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 취리히의 사용자가 시애틀 사무실로 출장하는 경우 내부 네트워크를 사용하여 유럽에서 이동하는 사용자와 게이트웨이 간의 미디어 트래픽을 전달하려는 경우(인터넷을 사용하는 것이 아니라) 유럽 SBC 또는 게이트웨이가 있는 암스테르담 사무실과 시애틀 사무실이 연결되어 있는지도 확인해야 합니다. 
  
## <a name="codecs-used-in-media-bypass"></a>미디어 우회에 사용되는 코덱

미디어 우회를 사용하도록 설정하면 클라이언트와 SBC 또는 게이트웨이 간의 미디어 트래픽이 G.711 코덱을 사용하게 됩니다. 
  
## <a name="see-also"></a>기타 참고 항목

[클라우드 커넥터 버전에서 미디어 우회 배포](deploy-media-bypass-in-cloud-connector.md)