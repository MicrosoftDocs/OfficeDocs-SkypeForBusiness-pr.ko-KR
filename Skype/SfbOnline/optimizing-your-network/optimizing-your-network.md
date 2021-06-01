---
title: 네트워크 최적화
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 조직에 대해 설정한 모든 온라인 기능에 대해 장기적인 상태와 성공을 보장하기 위해 비즈니스용 Skype 요구 사항이 매우 중요합니다. 일부 사용자들은 매우 기술적인 것을 알고 있습니다. 이 문서는 사용자에 대한 것이지만 그렇지 않은 사용자도 있습니다. 온라인 비즈니스용 Skype 설정하는 데 도움이 필요한 경우 이 문서를 읽고 고려해야 할 내용을 잘 알고 있습니다. 또한 Microsoft FastTrack Center, Microsoft Services 및 계정 팀 또는 Microsoft 파트너와 함께 작업할 때 이러한 요구 사항을 충족할 수 있는 방법을 알아내기 위해 대화할 사항도 제공합니다.
ms.openlocfilehash: a32e7864a15945fc9bad64c12466aa376cb924f9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240228"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>온라인용 네트워크 비즈니스용 Skype 최적화

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

조직에 대해 설정한 모든 온라인 기능에 대해 장기적인 상태와 성공을 보장하기 위해 비즈니스용 Skype 요구 사항이 매우 중요합니다. 일부 사용자들은 매우 기술적인 것을 알고 있습니다. 이 문서는 사용자에 대한 것이지만 그렇지 않은 사용자도 있습니다. 온라인 비즈니스용 Skype 설정하는 데 도움이 필요한 경우 이 문서를 읽고 고려해야 할 내용을 잘 알고 있습니다. 또한 [Microsoft FastTrack Center,](https://fasttrack.microsoft.com/office)Microsoft Services 및 계정 팀 또는 [Microsoft](https://partnercenter.microsoft.com/pcv/search) 파트너와 함께 작업할 때 이러한 요구 사항을 충족할 수 있는 방법을 알아내기 위해 대화할 사항도 제공합니다.

## <a name="a-quick-overview"></a>간략한 개요

비즈니스용 Skype 회사 또는 전 세계의 동업자 또는 비즈니스 파트너와 연결할 수 있습니다.

비즈니스용 Skype 다음을 할 수 있습니다.

- IM, 음성 또는 화상 통화로 대화를 시작합니다.

- 온라인, 모임 또는 발표에서 연락처를 사용할 수 있는 경우를 참조하세요.

- 모임에 대한 산업 강도 보안을 설정합니다.

- 대규모 대상에게 온라인으로 브로드캐스트합니다.

- 모임 중에 화면을 표시하거나 다른 사용자에 대한 제어를 제공합니다.

- 다른 비즈니스용 Skype 프로그램에서 Office 클릭으로 모임을 채팅, 통화 또는 참가할 수 있습니다.

## <a name="why-is-this-all-so-important"></a>이 모든 것이 중요한 이유는 무엇입니까?

IP를 통해 실시간 미디어(오디오, 비디오 및 애플리케이션 공유)의 품질은 종단-종단 네트워크 연결의 품질에 크게 영향을 미치게 됩니다. 최적의 비즈니스용 Skype 온라인 미디어 품질을 위해 회사 네트워크와 온라인 간에 고품질의 연결이 있는지 비즈니스용 Skype 중요합니다. 이 작업을 수행하기 위한 가장 좋은 방법은 모든 연결에서 온라인에서 최대 트래픽 볼륨을 수용할 수 있도록 네트워크의 용량에 따라 내부 네트워크 및 클라우드 비즈니스용 Skype 설정하는 것입니다.

[Microsoft](https://partnercenter.microsoft.com/pcv/search)파트너와 함께 작업하는 경우 클라우드의 Microsoft 365 Office 365 온라인을 포함하여 다양한 애플리케이션을 네트워크에 연결할 수 비즈니스용 Skype 실시간 음성 및 비디오 통신 기능을 비즈니스용 Skype 네트워크 서비스가 이러한 작업 및 실시간 워크로드를 지원하도록 Microsoft 365 Office 365 필요합니다. 여기에는 필요한 트래픽 볼륨을 전달하기에 충분한 대역폭을 가지며 QoS(품질 서비스)를 지원하여 사용자에게 비즈니스 클래스 환경을 제공할 수 있는 네트워크가 포함됩니다.

여기에 있는 정보와 함께 온라인 서비스 및 기능을 성공적으로 계획하고 배포하고 네트워크 서비스가 이러한 요구 사항을 충족하도록 비즈니스용 Skype 수 있는 다른 리소스가 있습니다.

- [ExpressRoute를 사용하는 호출 흐름](call-flow-using-expressroute.md)

- [비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)

- [온라인에서 미디어 품질 및 비즈니스용 Skype 성능](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>QoS(서비스 품질)를 구현합니다비즈니스용 Skype

온라인 비즈니스용 Skype 이동하기 전에 오디오, 비디오 및 세션 트래픽 공유를 처리하는 네트워크의 용량을 살펴보아야 합니다. 다른 Microsoft 365 Office 365 서비스와 함께 Microsoft는 각 회사 사이트에 필요한 네트워크 [트래픽을](https://www.microsoft.com/download/details.aspx?id=19011) 확인하는 데 비즈니스용 Skype 대역폭 계산기를 다운로드할 수 있습니다. 실시간 통신 트래픽 미디어 흐름 및 회사 위치당 트래픽의 양을 모델링하고, 트래픽 비즈니스용 Skype 계산하고, 트래픽이 전체 네트워크에 미치는 영향을 분석하는 등의 사용법 모델링을 수행해야 합니다. 이 데이터를 분석하면 네트워크가 개선해야 하는 위치의 권장 사항을 제공하고, 우수한 최종 사용자 환경을 제공하기 위해 큐 크기를 권장해야 합니다.

비즈니스용 Skype 트래픽은 정체된 네트워크에서 자주 발생하는 패킷 손실, 지연 및 지터에 민감합니다. 서비스 클래스라고도 하는 QoS(서비스 품질)는 관리되는 외부 WA, 관리되는 내부 랜 및 엔터프라이즈 기반 WiFi 네트워크에 배포해야 합니다. 이렇게 하면 로컬 네트워크의 비즈니스용 Skype WAN을 통해 오디오 및 비디오와 같은 실시간 트래픽의 우선 순위를 적절하게 지정하여 최종 사용자에게 더 나은 환경을 만드는 데 도움이 됩니다.

비즈니스용 Skype 오디오는 EF(Expedited Forwarding - DSCP 46) 큐에 배포되어야 비즈니스용 Skype 비디오는 AF41(보장 전달 - DSCP 34) 큐에 배포되어야 합니다. 이는 피어 투 피어 및 회의 트래픽의 경우도 마찬가지입니다. 전화 시스템 또는 Microsoft 365 Office 365 전화 통신 기능이 배포되고 있는지 여부에 관계없이 마찬가지입니다.

기존 QoS 정책이 다른 IP 전화 통신 제품에 대한 LAN 및 WAN에 이미 있을 수 비즈니스용 Skype 서비스를 사용하는 동안 사용자가 모바일로 이동하고 위치로 이동할 수 있습니다. 이 때문에 관리되는 네트워크에서 모든 트래픽의 우선 순위를 비즈니스용 Skype LAN, WAN 및 무선 네트워크에 QoS 정책을 표시해야 합니다.

네트워크를 크기 조정하는 데 도움이 하려면 대역폭 [계산기 비즈니스용 Skype 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=19011)

미디어 품질 및 QoS에 대한 자세한 내용은 온라인에서 미디어 [품질 및 네트워크 연결 성능을 비즈니스용 Skype 참조하세요.](media-quality-and-network-connectivity-performance.md)

QoS 설정 및 관리에 대한 자세한 내용은 서비스 품질 관리를 [참조합니다.](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)

## <a name="bypass-proxies-and-wan-optimization-devices"></a>Proxies 및 WAN 최적화 디바이스를 무시합니다.

Microsoft 365 Office 365 비롯한 모든 비즈니스용 Skype 온라인은 암호화되며 일반적으로 프록시 디바이스에서 검사할 수 없습니다. 이러한 이유로 사용자가 URL 및 IP 주소 범위에 대한 연결로 정의된 Microsoft 365 및 Office 365 네트워크 트래픽에 대해 프록시 디바이스를 Office 365 [것이 좋습니다.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 프록시 디바이스는 온라인 비즈니스용 Skype 실시간으로 지연을 도입할 가능성이 높기 때문에 이러한 트래픽에 대해 프록시 디바이스를 최소한으로 우회하는 것이 좋습니다.

방화벽에 트래픽을 Microsoft 365 Office 365 PAC 파일을 사용하여 URL 및 Microsoft 365 Office 365 제외하는 것이 좋습니다.

다음은 도움이 될 수 있는 몇 가지 사용 가능한 리소스입니다.

- [Microsoft 365 및 성능 Office 365 사용하여 성능 튜닝을 조정하거나 조정합니다.](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [네트워크 및 마이그레이션 계획에 Microsoft 365 또는 Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Office 365 프록시 Pac 생성기](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [WAN 최적화 컨트롤러 또는 트래픽/검사 디바이스를 Microsoft 365 또는 Office 365](/office365/troubleshoot/miscellaneous/office-365-third-party-network-devices)

- [또는 Microsoft 365 ExpressRoute를 Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>이중 암호화를 무시합니다.

사용자에게 최상의 오디오 및 비디오 환경을 제공하려면 VPN(가상 사설망) 터널을 비즈니스용 Skype 미디어(오디오 및 비디오)를 트래버스하지 못하게 하는 솔루션을 구현해야 합니다. 모든 비즈니스용 Skype TLS(전송 계층 보안)로 암호화되고 미디어 워크로드는 SRTP(Secure Real Time Protocol)로 암호화됩니다. 신호는 TLS로 암호화되고 미디어 워크로드는 SRTP로 암호화됩니다. VPN 터널을 통해 이 트래픽을 전송하면 추가 암호화 계층이 추가되고 클라이언트와 Microsoft 365 또는 Office 365 네트워크 홉이 추가됩니다. 이 둘 다 지터, 패킷 손실 및 대기 시간이 증가하기 때문에 세션이 저하될 수 있습니다.

VPN 터널을 비즈니스용 Skype 트래픽을 방지하는 한 가지 옵션은 분할 터널링입니다. 분할 터널링을 구현하기 위해 고객은 해당 소프트웨어에서 이 작업을 하는 방법에 대해 해당 VPN 공급업체와 상의해야 합니다.

> [!NOTE]
> 이 작업은 미디어 워크로드에 비즈니스용 Skype 필요하며 다른 서비스 또는 Microsoft 365 Office 365 없습니다.

추가 리소스:

- [Lync Media가 VPN 데이터를 무시할 수 Tunnel](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [직접 액세스, 분할 터널링 및 힘 터널링에 대한 자세한 내용은](/archive/blogs/tomshinder/more-on-directaccess-split-tunneling-and-force-tunneling)

- [직접 액세스 사용](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>올바른 포트 및 프로토콜이 열려 있는지 확인

고객은 서비스 또는 서비스에 필요한 URL 및 IP 주소의 Microsoft 365 Office 365 보장해야 합니다. 온라인용 모든 IP 주소 및 URL을 비즈니스용 Skype URL 및 IP 주소 범위에 Office 365 [참조하세요.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

비즈니스용 Skype 클라이언트는 다양한 포트 및 프로토콜을 사용합니다. 세션에 대한 네트워크 트래픽의 방향과 비즈니스용 Skype 상호 작용 유형(피어 투 피어 및 다파티)에 따라 콘텐츠 공유 및 음성/비디오 사용에 따라 달라집니다. 원본 및 대상 포트에 특별한 주의를 기울여 포트 및 프로토콜 목록을 검토하고 열어야 합니다. 예를 들어 오디오 트래픽은 클라이언트 쪽에서 20개 포트(50000-50019 TCP/UDP)를 사용하지만 대상 포트는 서비스 쪽의 10K 포트 범위(50000-59999 TCP/UDP)에 있을 수 있습니다. 여기에는 방화벽에서 TCP 443 및 UDP 3478 열기도 포함됩니다.

또한 온라인을 지원하기 위해 추가 네트워크 구성이 비즈니스용 Skype 있습니다.


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>휴대폰 및 디바이스에 최적화된 비즈니스용 Skype

실시간 미디어 세션에서 헤드셋 및 웹 캠과 같은 모든 참가자가 사용하는 미디어 디바이스는 전체 오디오 및 비디오 품질에 큰 영향을 미치고 있습니다. 잘못된 디바이스 드라이버가 있는 낮은 품질의 디바이스 또는 디바이스는 오디오의 전반적인 음질이 낮고 비디오의 이미지 품질이 낮아질 수 있습니다. 반면 인증된 디바이스 또는 양질의 디바이스는 에코 취소, 노이즈 필터링, 비디오 해상도를 지원하고 대기 시간을 줄일 수 있습니다.

휴대폰 및 디바이스는 최종 사용자에 대한 오디오 및 비디오 품질에 큰 차이를 제공합니다. 비즈니스용 Skype 인증 프로그램은 "Lync 호환" 프로그램의 발전으로, 디바이스가 오디오 및 비디오에 대한 Microsoft 표준을 충족하는지 확인합니다. Microsoft에서 테스트하고 자격을 갖춘 여러 IP 전화, USB 오디오 및 비디오 디바이스, PC 및 회의실 디바이스가 있습니다. 조직에 최적화된 디바이스 목록을 검토하고 조직의 비즈니스용 Skype 사용자의 다양한 요구 및 개인 기본 설정을 충족하기 위해 다양한 디바이스를 제공해야 합니다.

지원되는 디바이스 및 인증된 디바이스에 대한 자세한 내용은 다음을 참조하세요.  

- [비즈니스용 Skype Online 휴대폰 받기](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [휴대폰 및 비즈니스용 Skype](../../SfbPartnerCertification/certification/devices-ip-phones.md)

- [개인 주변 장치를 위한 솔루션 카탈로그](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [Microsoft Lync에 대해 자격을 갖춘 휴대폰 및 디바이스](../../SfbPartnerCertification/lync-cert/ip-phones.md)

사용자가 모임하고 오디오 및 비디오 디바이스를 사용하는 환경 및 주변 영역은 오디오 및 비디오 품질에 대한 또 다른 중요한 요소입니다. 시음이 많은 환경에서 호출하는 사용자는 오디오가 울려 퍼지며 음소수로 울려 퍼집니다. 어둡거나 낮은 조명 환경의 사용자는 비디오에 대해 밝고 선명한 이미지 품질을 만들 수 없습니다. 회의실 설정에서 마이크 및 비디오 디바이스의 위치는 참가자가 받을 소리 및 이미지 품질에 직접적인 영향을 미치게 됩니다.

사용자의 오디오 및 비디오 환경의 명확한 그림을 얻기 위해 비즈니스용 Skype **도구** 옵션 오디오 디바이스 또는 비디오 디바이스를 사용하여 사용 중 디바이스를 변경하고 설정을 사용자  >    >   지정합니다.  통화 품질 확인 을 클릭하여 통화의 오디오 품질을 **확인할 수 있습니다.** 통화 **품질** 확인을 클릭하면 테스트 호출에서 찾은 품질 및 문제를 보고할 수 있습니다.

![클라이언트에서 비즈니스용 Skype 테스트합니다.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)
