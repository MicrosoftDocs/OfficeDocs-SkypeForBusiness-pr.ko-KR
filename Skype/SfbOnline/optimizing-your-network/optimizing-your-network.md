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
description: 다음 요구 사항은 조직에 대해 설정하는 모든 비즈니스용 Skype Online 기능의 장기적인 상태와 성공을 보장하는 데 매우 중요합니다. 기술적인 사용자도 있습니다. 이 문서는 사용자에 대한 것이지만 그렇지 않은 사용자도 있습니다. 비즈니스용 Skype Online을 설정하는 데 도움이 필요한 경우 이 문서를 읽고 고려해야 할 내용을 익히는 것이 필요합니다. 또한 Microsoft FastTrack 센터, Microsoft 서비스 및 계정 팀 또는 Microsoft 파트너와 함께 작업할 때 이러한 요구 사항을 충족하는 방법을 알아내기 위해 대화할 사항도 제공합니다.
ms.openlocfilehash: eb8cf69ee7e8ea82d71ea088f5866b03e048a0ac
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164757"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>비즈니스용 Skype Online에 대한 네트워크 최적화

다음 요구 사항은 조직에 대해 설정하는 모든 비즈니스용 Skype Online 기능의 장기적인 상태와 성공을 보장하는 데 매우 중요합니다. 기술적인 사용자도 있습니다. 이 문서는 사용자에 대한 것이지만 그렇지 않은 사용자도 있습니다. 비즈니스용 Skype Online을 설정하는 데 도움이 필요한 경우 이 문서를 읽고 고려해야 할 내용을 익히는 것이 필요합니다. 또한 [Microsoft FastTrack 센터, Microsoft](https://fasttrack.microsoft.com/office)서비스 및 계정 팀 또는 [Microsoft](https://partnercenter.microsoft.com/pcv/search) 파트너와 함께 작업할 때 이러한 요구 사항을 충족하는 방법을 알아내기 위해 대화할 사항도 제공합니다.

## <a name="a-quick-overview"></a>간략한 개요

비즈니스용 Skype를 사용하면 회사 또는 전 세계에 있는 회사 또는 비즈니스 파트너와 연결할 수 있습니다.

비즈니스용 Skype를 사용하여 다음을 할 수 있습니다.

- IM, 음성 또는 영상 통화를 통해 대화를 시작해 100분의 16진수로 대화를 시작할 수 있습니다.

- 온라인, 모임 또는 발표에서 연락처를 사용할 수 있는 경우를 참조하세요.

- 모임에 대한 산업 강도 보안을 설정할 수 있습니다.

- 대규모 대상에게 온라인으로 브로드캐스트합니다.

- 모임 중에 화면을 발표하거나 다른 사용자들에게 제어권 제공

- 다른 Office 프로그램에서 비즈니스용 Skype를 사용하여 클릭 한 번으로 채팅, 통화 또는 모임에 참가할 수 있습니다.

## <a name="why-is-this-all-so-important"></a>이 모든 것이 중요한 이유는 무엇일까요?

IP를 통해 실시간 미디어(오디오, 비디오 및 애플리케이션 공유)의 품질은 종단 내 네트워크 연결의 품질에 크게 영향을 미치고 있습니다. 최적의 비즈니스용 Skype Online 미디어 품질을 위해 회사 네트워크와 비즈니스용 Skype Online 간에 고품질 연결이 있는지 반드시 확인합니다. 이 작업을 수행하기 위한 가장 좋은 방법은 모든 연결에서 비즈니스용 Skype Online의 최대 트래픽 볼륨을 수용할 수 있도록 네트워크 용량에 따라 내부 네트워크 및 클라우드 연결을 설정하는 것입니다.

[Microsoft](https://partnercenter.microsoft.com/pcv/search)파트너와 협력하여 클라우드의 비즈니스용 Skype Online을 비롯한 다양한 Microsoft 365 또는 Office 365 응용 프로그램을 네트워크에 연결할 수 있으며 비즈니스용 Skype의 실시간 음성 및 비디오 통신 기능을 사용하려면 이러한 Microsoft 365 및 Office 365 실시간 워크로드를 지원하도록 네트워크 서비스를 특별히 구성해야 합니다. 여기에는 필요한 트래픽 볼륨을 전달하기에 충분한 대역폭이 있으며 QoS(서비스 품질)를 지원하여 사용자에게 비즈니스 클래스 환경을 제공할 수 있는 네트워크가 포함됩니다.

여기에 있는 정보와 함께 비즈니스용 Skype Online 서비스 및 기능을 성공적으로 계획 및 배포하고 네트워크 서비스가 이러한 요구 사항을 충족하도록 하는 데 도움이 되는 다른 리소스가 있습니다.

- [ExpressRoute를 사용하는 호출 흐름](call-flow-using-expressroute.md)

- [비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)

- [비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>비즈니스용 Skype에 대한 QoS(서비스 품질) 구현

비즈니스용 Skype Online으로 이동하기 전에 오디오, 비디오 및 공유 세션 트래픽을 처리하기 위한 네트워크 용량을 살펴보아야 합니다. 다른 Microsoft 365 및 Office 365 서비스와 함께 Microsoft는 각 회사 사이트에 필요한 네트워크 트래픽을 결정하는 데 사용되는 비즈니스용 [Skype](https://www.microsoft.com/download/details.aspx?id=19011) 대역폭 계산기를 다운로드할 수 있습니다. 실시간 통신 트래픽 미디어 흐름 및 회사 위치당 비즈니스용 Skype 트래픽 양 모델링, 트래픽 볼륨 계산 및 해당 트래픽이 전체 네트워크에 미치는 영향 분석 등 사용 모델링을 수행해야 합니다. 이 작업을 완료한 후 이 데이터를 분석하면 네트워크를 개선해야 하는 위치의 권장 사항을 제공하고 뛰어난 최종 사용자 환경을 제공하기 위해 큐 크기를 권장해야 합니다.

비즈니스용 Skype 실시간 트래픽은 정체된 네트워크에서 자주 발생하는 패킷 손실, 지연 및 지터에 민감합니다. 서비스 클래스라고도 하는 QoS(서비스 품질)는 관리되는 외부 랜, 관리되는 내부 랜 및 엔터프라이즈 기반 WiFi 네트워크에 배포되어야 합니다. 이렇게 하면 로컬 네트워크 및 WAN을 통해 다른 비 실시간 트래픽보다 오디오 및 비디오와 같은 비즈니스용 Skype 실시간 트래픽의 우선 순위를 적절하게 지정하여 최종 사용자에게 더 나은 환경을 만들 수 있습니다.

비즈니스용 Skype 오디오는 EF(Expedited Forwarding - DSCP 46) 큐에 배포되어야 합니다. 비즈니스용 Skype 비디오는 AF41(Assured Forwarding - DSCP 34) 큐에 배포해야 합니다. Microsoft 365 또는 Office 365의 전화 시스템 또는 기타 전화 통신 기능에 관계없이 피어 투 피어 및 회의 트래픽의 경우에도 마찬가지입니다.

기존 QoS 정책이 다른 IP 전화 통신 제품의 LAN 및 WAN에 이미 있을 수 있는 반면 비즈니스용 Skype를 사용하면 사용자가 모바일이 되어 서비스를 사용하는 동안 위치로 이동할 수 있습니다. 이 때문에 모든 비즈니스용 Skype 트래픽이 관리되는 네트워크에서 우선 순위를 지정하는지 확인하려면 QoS 정책이 LAN, WAN 및 무선 네트워크에 표시되어야 합니다.

네트워크의 크기 조정을 지원하려면 비즈니스용 Skype 대역폭 [계산기를 다운로드하세요.](https://www.microsoft.com/download/details.aspx?id=19011)

미디어 품질 및 QoS에 대한 자세한 내용은 비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 [성능을 참조하세요.](media-quality-and-network-connectivity-performance.md)

QoS 설정 및 관리에 대한 자세한 내용은 서비스 품질 관리를 [참조합니다.](https://technet.microsoft.com/library/gg425841.aspx)

## <a name="bypass-proxies-and-wan-optimization-devices"></a>Proxies 및 WAN 최적화 디바이스 우회

비즈니스용 Skype Online을 포함한 모든 Microsoft 365 또는 Office 365는 암호화되며 일반적으로 프록시 장치에서 검사할 수 없습니다. 이러한 이유로 사용자가 Office 365 URL 및 IP 주소 범위에 대한 연결로 정의된 모든 Microsoft 365 및 Office [365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)네트워크 트래픽에 대한 프록시 디바이스를 무시하는 것이 좋습니다. 프록시 디바이스는 실시간 비즈니스용 Skype Online 미디어 스트림에서 지연을 도입할 가능성이 높기 때문에 적어도 프록시 디바이스를 우회하는 것이 좋습니다.

MICROSOFT는 PAC 파일을 사용하여 Microsoft 365 및 Office 365 트래픽을 방화벽으로 보내기 위해 Microsoft 365 및 Office 365 URL을 제외하는 것이 좋습니다.

다음은 도움이 될 수 있는 몇 가지 사용 가능한 리소스입니다.

- [기준 및 성능 기록을 사용하여 Microsoft 365 또는 Office 365 성능 조정](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [Microsoft 365 또는 Office 365에 대한 네트워크 및 마이그레이션 계획](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Office 365 프록시 Pac 생성기](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [Microsoft 365 또는 Office 365에서 WAN 최적화 컨트롤러 또는 트래픽/검사 디바이스 사용](https://aka.ms/kb2690045)

- [Microsoft 365 또는 Office 365용 ExpressRoute를 통해 라우팅](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>이중 암호화 무시

사용자에게 최상의 오디오 및 비디오 환경을 제공하려면 비즈니스용 Skype 미디어(오디오 및 비디오)가 VPN(Virtual Private Network) 터널을 트래버스하지 못하게 하는 솔루션을 구현해야 합니다. 모든 비즈니스용 Skype 트래픽은 TLS(전송 계층 보안)로 암호화되고 미디어 워크로드는 SRTP(Secure Real Time Protocol)로 암호화됩니다. 신호는 TLS로 암호화되고 미디어 워크로드는 SRTP로 암호화됩니다. VPN 터널을 통해 이 트래픽을 전송하면 클라이언트와 Microsoft 365 또는 Office 365 간의 추가 네트워크 홉과 추가 네트워크 홉이 추가됩니다. 이로 인해 지터, 패킷 손실 및 대기 시간이 증가하기 때문에 세션이 저하될 수 있습니다.

비즈니스용 Skype 트래픽이 VPN 터널을 트래버스하지 못하게 하는 한 가지 옵션은 분할 터널링입니다. 분할 터널링을 구현하기 위해 고객은 소프트웨어에서 이 작업을 하는 방법에 대한 구체적인 정보를 VPN 공급업체에 문의해야 합니다.

> [!NOTE]
> 비즈니스용 Skype 미디어 워크로드에만 필요하며 다른 Microsoft 365 또는 Office 365 서비스에는 적용되지 않습니다.

추가 리소스:

- [Lync Media에서 VPN 터널을 우회할 수 있도록 설정](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [직접 액세스, 분할 터널링 및 강제 터널링에 대한 자세한 내용은](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)

- [직접 액세스 사용](https://technet.microsoft.com/library/jj574163.aspx)

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>올바른 포트 및 프로토콜이 열려 있는지 확인

고객은 Microsoft 365 또는 Office 365 서비스에 필요한 URL 및 IP 주소의 연결성을 보장해야 합니다. 비즈니스용 Skype Online의 모든 IP 주소 및 URL에 대한 전체 목록은 [Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)및 IP 주소 범위를 참조하세요.

비즈니스용 Skype 클라이언트는 다양한 포트 및 프로토콜을 사용합니다. 비즈니스용 Skype 세션에 대한 네트워크 트래픽의 방향과 흐름은 상호 작용 유형(피어 투 피어 및 다중파티)의 유형과 콘텐츠 공유 및 음성/비디오의 사용에 따라 달라집니다. 원본 및 대상 포트에 특히 주의하여 포트 및 프로토콜 목록을 검토하고 열 수 있어야 합니다. 예를 들어 오디오 트래픽은 클라이언트 쪽에서 20개 포트(50000-50019 TCP/UDP)만 사용하지만 대상 포트는 서비스 쪽의 10K 포트 범위(50000-59999 TCP/UDP)에 있을 수 있습니다. 여기에는 방화벽에서 TCP 443 및 UDP 3478 열기도 포함됩니다.

비즈니스용 Skype Online을 지원하려면 추가 네트워크 구성이 필요할 수도 있습니다.


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>비즈니스용 Skype에 최적화된 전화 및 장치 사용

실시간 미디어 세션에서 헤드셋 및 웹 캠과 같은 모든 참가자가 사용하는 미디어 디바이스는 전반적인 오디오 및 비디오 품질에 큰 영향을 미치고 있습니다. 잘못된 장치 드라이버가 있는 저품질 장치 또는 디바이스는 오디오에 대한 전반적인 음질을 낮추고 비디오의 이미지 품질을 낮출 수 있습니다. 반면에 인증된 디바이스 또는 고품질 디바이스는 에코 취소, 노이즈 필터링, 비디오 해상도 및 대기 시간을 줄이는 데 도움이 됩니다.

휴대폰과 장치는 최종 사용자의 오디오 및 비디오 품질에 큰 차이를 미치고 있습니다. 비즈니스용 Skype 인증 프로그램은 "Lync 호환" 프로그램의 진화된 프로그램으로, 장치가 오디오 및 비디오에 대한 Microsoft 표준을 충족하는지 확인합니다. Microsoft에서 테스트 및 자격을 갖춘 다양한 IP 전화기, USB 오디오 및 비디오 장치, PC 및 회의실 디바이스가 있습니다. 비즈니스용 Skype에 최적화된 장치 목록을 검토하고 조직의 최종 사용자의 다양한 요구와 개인 선호 사항을 충족하기 위해 다양한 장치를 제공해야 합니다.

지원되는 디바이스 및 인증된 디바이스에 대한 자세한 내용은 다음을 참조하세요.  

- [비즈니스용 Skype Online 휴대폰 받기](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [비즈니스용 Skype용 전화 및 장치](https://technet.microsoft.com/office/dn947482.aspx)

- [개인 주변 장치를 위한 솔루션 카탈로그](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [Microsoft Lync에 대한 자격이 있는 전화 및 장치](https://technet.microsoft.com/office/dn788944.aspx)

사용자가 모임에 참석하고 오디오 및 비디오 장치를 사용하는 환경 및 주변 영역은 오디오 및 비디오 품질에 대한 또 다른 중요한 요소입니다. 시즈음 환경에서 호출하는 사용자는 오디오가 울려 퍼지며 불확실해집니다. 어둡거나 낮은 조명 환경의 사용자는 비디오에 대해 밝고 선명한 이미지 품질을 만들 수 없습니다. 회의실 설정에서 마이크와 비디오 장치의 위치는 참가자가 받을 소리 및 이미지 품질에 직접적인 영향을 미치게 됩니다.

사용자의 오디오 및 비디오 환경을 더 명확하게 확인하려면 비즈니스용 Skype 앱 도구 옵션 오디오 장치 또는 비디오 장치를 사용하여 사용 중 장치를 변경하고 설정을 사용자  >    >   지정합니다.  통화 품질 확인을 클릭하여 통화의 음질을 **확인할 수 있습니다.** 통화 품질 **확인을** 클릭하면 테스트 호출에서 찾은 품질 및 문제를 보고할 수 있습니다.

![비즈니스용 Skype 클라이언트에서 오디오 테스트](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)
