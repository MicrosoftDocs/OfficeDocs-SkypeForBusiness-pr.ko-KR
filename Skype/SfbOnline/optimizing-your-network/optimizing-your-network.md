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
description: 다음 요구 사항은 조직에 대해 설정 하는 모든 비즈니스용 Skype Online 기능에 대 한 장기간의 상태와 성공 여부를 확인 하는 데 매우 중요 합니다. 이 문서는 매우 유용한 기술 이지만 몇 가지 기능을 제공 하지는 않습니다. 비즈니스용 Skype Online 설정에 대 한 도움이 필요한 경우이 문서를 읽고 고려해 야 할 사항을 숙지 하세요. 또한 microsoft FastTrack 센터, Microsoft 서비스 및 계정 팀을 사용 하는 경우, microsoft 파트너와 함께 이러한 요구 사항을 충족 하는 방법을 파악 하는 데 도움이 되는 내용을 제공 합니다.
ms.openlocfilehash: 5101b59c4e911f6fbad36ff2c601428a8fa25177
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010951"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>비즈니스용 Skype Online에 맞게 네트워크 최적화

다음 요구 사항은 조직에 대해 설정 하는 모든 비즈니스용 Skype Online 기능에 대 한 장기간의 상태와 성공 여부를 확인 하는 데 매우 중요 합니다. 이 문서는 매우 유용한 기술 이지만 몇 가지 기능을 제공 하지는 않습니다. 비즈니스용 Skype Online 설정에 대 한 도움이 필요한 경우이 문서를 읽고 고려해 야 할 사항을 숙지 하세요. 또한 microsoft [FastTrack 센터](https://fasttrack.microsoft.com/office), microsoft 서비스 및 계정 팀을 사용 하는 경우, microsoft [파트너](https://partnercenter.microsoft.com/pcv/search) 와 함께 이러한 요구 사항을 충족 하는 방법을 파악 하는 데 도움이 되는 내용을 제공 합니다.

## <a name="a-quick-overview"></a>간단한 개요

비즈니스용 Skype를 사용 하 여 회사나 전세계의 공동 작업자 또는 비즈니스 파트너와 연결할 수 있습니다.

비즈니스용 Skype를 사용 하 여 다음을 수행할 수 있습니다.

- 인스턴트 메시지, 음성 또는 영상 통화로 대화를 시작 하세요.

- 온라인, 모임 또는 프레젠테이션 중에 대화 상대를 볼 수 있는 경우를 참조 하세요.

- 모임에 대해 산업용 수준 보안을 설정 합니다.

- 다양 한 청중에 게 온라인으로 브로드캐스트할 수 있습니다.

- 모임 중에 화면을 표시 하거나 다른 사용자에 게 제어권을 제공 합니다.

- 다른 Office 프로그램에서 비즈니스용 Skype를 사용 하 여 클릭을 통해 모임에 채팅 하거나 전화를 걸거나 참가할 수 있습니다.

## <a name="why-is-this-all-so-important"></a>이 사항이 모두 중요 한 이유는 무엇 인가요?

IP를 통한 실시간 미디어 (오디오, 비디오 및 응용 프로그램 공유)의 품질은 종단간 네트워크 연결의 품질에 따라 크게 영향을 받습니다. 비즈니스용 Skype Online media의 품질을 최적화 하려면 회사 네트워크와 비즈니스용 Skype Online 간에 고품질의 연결을 설정 하는 것이 중요 합니다. 이 작업을 수행 하는 가장 좋은 방법은 모든 연결에 걸친 비즈니스용 Skype Online의 최고 트래픽 볼륨에 맞게 네트워크 용량을 기준으로 내부 네트워크 및 클라우드 연결을 설정 하는 것입니다.

[Microsoft 파트너](https://partnercenter.microsoft.com/pcv/search)와 협력 하 여 회사의 비즈니스용 skype Online을 비롯 한 다양 한 Office 365 응용 프로그램을 네트워크에 연결 하 고 비즈니스용 skype에 대 한 실시간 음성 및 영상 통신 기능을 365 지원 하기 위해 네트워크 서비스를 명시적으로 구성 해야 합니다. 여기에는 필요한 트래픽 볼륨을 운반 하기에 충분 한 대역폭을 보유 하 고 있으며 QoS (서비스 품질)를 지원 하 여 사용자에 게 비즈니스 수업 경험을 제공할 수 있는 네트워크가 포함 됩니다.

여기에는 비즈니스용 Skype Online 서비스 및 기능을 성공적으로 계획 하 고 배포 하는 데 도움이 될 수 있는 다른 리소스가 있으며, 네트워크 서비스가 이러한 요구 사항을 충족 하는지 확인 합니다.

- [ExpressRoute를 사용하는 호출 흐름](call-flow-using-expressroute.md)

- [비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)

- [비즈니스용 Skype Online의 미디어 품질과 네트워크 연결 성능](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>비즈니스용 Skype에 대 한 서비스 품질 (QoS) 구현

비즈니스용 Skype Online으로 전환 하기 전에 네트워크 용량을 살펴보고 오디오, 비디오 및 공유 세션 트래픽을 처리 해야 합니다. 다른 Office 365 서비스와 마찬가지로 Microsoft는 각 회사 사이트에 필요한 네트워크 트래픽을 결정 하는 데 사용 되는 비즈니스용 [Skype 대역폭 계산기](https://www.microsoft.com/download/details.aspx?id=19011) 를 다운로드할 수 있습니다. 실시간 통신 트래픽 미디어 흐름과 회사 위치 당 비즈니스용 Skype 트래픽 양, 트래픽 볼륨 계산, 트래픽이 전체 네트워크에 영향을 주는 방식을 분석 하는 등의 사용 현황 모델링을 수행 해야 합니다. 이 작업을 완료 한 후에는이 데이터를 분석 하 여 네트워크를 개선 해야 하는 위치에 대 한 권장 사항을 제공 하 고 최상의 최종 사용자 환경을 제공 하기 위해 대기열 크기를 권장 해야 합니다.

비즈니스용 Skype 실시간 트래픽은 패킷 손실, 지연 및 지터에 대 한 중요 한 것으로, 혼잡 네트워크에서 자주 발생 합니다. QoS (서비스 품질) 라고도 함-서비스 종류는 관리 되는 외부 Wan, 관리 내부 Lan 및 엔터프라이즈 기반 WiFi 네트워크에도 배포 되어야 합니다. 이렇게 하면 로컬 네트워크 및 WAN을 통한 다른 비 실제 시간 트래픽을 통해 오디오 및 비디오와 같은 비즈니스용 Skype 실시간 트래픽을 적절 하 게 우선 순위를 지정 하 여 최종 사용자에 게 더 나은 환경을 만들 수 있습니다.

비즈니스용 skype 오디오는 EF (긴급 전달-DSCP 46) 큐에 배포 해야 하며 비즈니스용 Skype 비디오는 AF41 (보장 된 착신 전환-DSCP 34) 큐에 배포 해야 합니다. 이는 Office 365 또는 다른 전화 통신 기능의 전화 시스템의 배포 여부에 관계 없이 피어 투 피어 및 회의 트래픽에도 해당 됩니다.

기존 QoS 정책은 이미 LAN 및 다른 IP 전화 통신 제품에 대 한 WAN에 위치 해 있을 수 있지만, 비즈니스용 Skype를 통해 사용자는 모바일이 될 수 있으며 서비스를 사용 하는 동안 위치에서 위치로 이동할 수 있습니다. 이 때문에 모든 비즈니스용 Skype 트래픽을 관리 되는 네트워크에서 우선 순위를 유지 하려면 LAN, WAN 및 무선 네트워크에 QoS 정책이 표시 되어야 합니다.

네트워크 크기를 조정 하는 데 도움이 필요 하면 [비즈니스용 Skype 대역폭 계산기](https://www.microsoft.com/download/details.aspx?id=19011)를 다운로드 하세요.

미디어 품질과 QoS에 대 한 자세한 내용은 [비즈니스용 Skype Online의 미디어 품질과 네트워크 연결 성능을](media-quality-and-network-connectivity-performance.md)참조 하세요.

QoS 설정 및 관리에 대 한 자세한 내용은 [서비스 품질 관리](https://technet.microsoft.com/library/gg425841.aspx)를 참조 하세요.

## <a name="bypass-proxies-and-wan-optimization-devices"></a>프록시 및 WAN 최적화 장치 사용 안 함

비즈니스용 Skype Online을 포함 한 모든 Office 365는 암호화 되어 있으며 일반적으로 프록시 장치에서 검사할 수 없습니다. 이러한 이유로 사용자가 [office 365 url 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)에 대 한 연결로 정의 된 모든 Office 365 네트워크 트래픽에 대해 프록시 장치를 우회 하는 것이 좋습니다. 프록시 장치는 실시간 비즈니스용 Skype Online 미디어 스트림을 지연 시킬 수 있으므로 최소한 해당 트래픽에만 프록시 장치를 우회 하는 것이 좋습니다.

Microsoft는 PAC 파일을 사용 하 여 office 365 Url을 제외 하 고 방화벽에 Office 365 트래픽을 보내는 것이 좋습니다.

다음은 사용할 수 있는 몇 가지 리소스입니다.

- [Office 365 초기 계획 및 성능 기록을 사용 하 여 성능 조정](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [Office 365에 대 한 네트워크 및 마이그레이션 계획](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Office 365 프록시 Pac 생성기](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [WAN 최적화 컨트롤러 또는 Office 365에서 트래픽/검사 장치 사용](https://aka.ms/kb2690045)

- [Office 365 용 Express를 사용 하는 라우팅](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>이중 암호화 무시

사용자에 게 최상의 오디오 및 비디오 환경을 제공 하려면 비즈니스용 Skype 미디어 (오디오 및 비디오)가 VPN (가상 사설망) 터널을 통과 하는 것을 막는 솔루션을 구현 해야 합니다. 모든 비즈니스용 Skype 트래픽은 TLS (전송 계층 보안)를 사용 하 여 암호화 되 고, 미디어 워크 로드는 보안 실시간 프로토콜 (SRTP)으로 암호화 됩니다. 신호는 TLS로 암호화 되 고 미디어 작업은 SRTP으로 암호화 됩니다. VPN 터널을 통해이 트래픽을 전송 하면 추가 암호화 계층과 클라이언트와 Office 365 사이에 추가 네트워크 홉이 추가 되므로이 두 가지는 모두 지터와 패킷 손실 및 대기 시간을 증가 시 면 성능이 저하 될 수 있습니다.

비즈니스용 Skype 트래픽이 VPN 터널을 트래버스 하는 것을 방지 하는 한 가지 옵션은 분할 터널링입니다. 분할 터널링을 구현 하기 위해 고객은 해당 소프트웨어에서이 작업을 수행 하는 방법에 대 한 세부 사항을 VPN 공급 업체에 문의 해야 합니다.

> [!NOTE]
> 이는 비즈니스용 Skype 미디어 작업에만 필요 하며 다른 Office 365 서비스에는 적용 되지 않습니다.

추가 리소스:

- [Lync 미디어를 사용 하 여 VPN 터널 우회](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [직접 액세스, 분할 터널링 및 강제 터널링에 대 한 추가 정보](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)

- [직접 액세스 사용](https://technet.microsoft.com/library/jj574163.aspx)

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>적절 한 포트와 프로토콜이 열려 있는지 확인

고객은 O365 서비스에 필요한 Url 및 IP 주소의 연결 가능성을 보장 해야 합니다. 비즈니스용 Skype Online에 대 한 모든 IP 주소 및 Url의 전체 목록은 [Office 365 url 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)를 참조 하세요.

비즈니스용 Skype 클라이언트는 다양 한 포트와 프로토콜을 사용 합니다. 비즈니스용 Skype 세션에 대 한 네트워크 트래픽 방향과 흐름은 조작 유형 (피어 투 피어 vs 단체) 및 콘텐츠 공유 및 음성/비디오 사용에 따라 달라 집니다. 원본 및 대상 포트에 특별 한 주의를 기울이고 포트 및 프로토콜 목록을 검토 하 고 열어야 합니다. 예를 들어 오디오 트래픽은 클라이언트 쪽에서 20 개 포트 (50000-50019 TCP/UDP)만 사용 하지만, 대상 포트는 서비스 측의 10K 포트 범위 (50000-59999 TCP/UDP)에서 어디에 있을 수 있습니다. 여기에는 방화벽에서 TCP 443 및 UDP 3478을 여는 것도 포함 됩니다.

비즈니스용 Skype Online을 지원 하기 위해 추가 네트워크 구성이 필요할 수도 있습니다.


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>비즈니스용 Skype에 최적화 된 전화 및 장치 사용

실시간 미디어 세션에서 헤드셋 및 웹 캠 같은 모든 참가자가 사용 하는 미디어 장치는 전체 오디오 및 비디오 품질에 큰 영향을 미칩니다. 장치 드라이버가 올바르지 않은 저품질 장치 또는 장치는 오디오에 대 한 전체적인 음질을 낮추고 비디오의 이미지 품질을 낮춥니다. 다른 한편, 인증 된 장치 또는 좋은 음질 장치는 에코 취소, 노이즈 필터링, 비디오 해상도 및 대기 시간 줄이기에 대 한 도움말을 표시 합니다.

휴대폰 및 장치는 최종 사용자를 위한 오디오 및 비디오 품질의 큰 차이를 만들어 보세요. 비즈니스용 Skype 인증 프로그램은 "Lync 호환" 프로그램의 발전을 통해 장치가 오디오 및 비디오에 대 한 Microsoft 표준을 충족 하는지 확인 합니다. Microsoft에서 테스트 하 고 검증 한 여러 개의 IP 전화, USB 오디오 및 비디오 장치, Pc 및 회의실 장치가 있습니다. 비즈니스용 Skype에 최적화 된 디바이스 목록을 검토 하 고 조직의 최종 사용자의 다양 한 요구 및 개인 기본 설정을 충족 하기 위해 다양 한 장치를 제공 하는 작업을 수행 해야 합니다.

지원 되는 인증 된 장치에 대 한 자세한 내용은 다음을 참조 하세요.  

- [비즈니스용 Skype Online 휴대폰 받기](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [비즈니스용 Skype 용 전화 및 장치](https://technet.microsoft.com/office/dn947482.aspx)

- [개인 주변 장치를 위한 솔루션 카탈로그](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [Microsoft Lync 용으로 한정 된 전화 및 장치](https://technet.microsoft.com/office/dn788944.aspx)

오디오 및 비디오 장치를 사용 하는 환경과 주변 영역에 오디오 및 비디오 품질로 사용할 수 있는 또 다른 중요 한 요소입니다. 잡음이 있는 환경에서 전화를 거는 사용자는 오디오를 muffled 하 고 명확 하 게 조작할 수 있습니다. 어둡거나 저렴 한 환경에서 사용자는 비디오에 대 한 선명한 이미지 화질을 밝게 만들 수 없습니다. 회의실 설정에서 마이크와 비디오 장치의 위치는 참가자가 수신할 사운드 및 이미지 품질에 직접적인 영향을 미칩니다.

사용자의 오디오 및 비디오 환경에 대 한 자세한 그림을 얻으려면 비즈니스용 Skype 앱 **도구** > **옵션** > **오디오 장치** 또는 **비디오 장치** 를 사용 하 여 장치를 변경 하 고 설정을 사용자 지정 합니다. **통화 품질 확인**을 클릭 하 여 통화의 오디오 음질을 확인할 수도 있습니다. **통화 품질 확인**을 클릭 하면 테스트 호출에 대해 발견 된 품질 및 문제를 보고할 수 있습니다.

![비즈니스용 Skype 클라이언트에서 오디오 테스트](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)
