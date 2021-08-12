---
title: QoS(서비스 품질) 관리
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: QoS(서비스 품질)는 오디오 및 비디오 통신을 위한 최적의 최종 사용자 환경을 제공하기 위해 일부 조직에서 사용되는 네트워킹 기술입니다.
ms.openlocfilehash: bc09ef8368034787201caee8bc077fe11a3f93a0451d2556eb677ceaab632b10
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281811"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>서비스 품질 관리(QoS) 비즈니스용 Skype 서버


QoS(서비스 품질)는 음성 및 화상 통신의 최종 사용자 경험을 최적화하기 위해 일부 조직에서 사용되는 네트워킹 기술입니다. QoS는 대부분 대역폭 제약이 있는 네트워크에서 사용됩니다. 다수의 네트워크 패킷이 비교적 적은 양의 가용 대역폭을 놓고 경합하는 경우 관리자가 QoS를 사용하여 오디오 또는 비디오 데이터를 전송하는 패킷에 보다 높은 우선 순위를 할당할 수 있습니다. 이러한 패킷에 보다 높은 우선 순위를 지정하면 음성 및 화상 통신이 파일 전송, 웹 브라우징, 데이터베이스 백업 등이 포함된 네트워크 세션보다 더욱 빠르게 수행되며 중단이 줄어듭니다. 파일 전송 또는 데이터베이스 백업에 사용되는 네트워크 패킷에 "최상의 노력" 우선 순위가 할당되어 있기 때문입니다.


> [!NOTE]  
> 일반적으로 QoS는 내부 네트워크의 통신 세션에만 적용됩니다. QoS를 구현하는 경우 서버와 라우터가 패킷 표시를 지원하도록 구성하게 됩니다. 인터넷이나 기타 네트워크에서 QoS가 지원될 것이라고 가정할 수 없습니다. 다른 네트워크에서 QoS가 지원되더라도 조직의 네트워크에서 QoS 서비스를 구성한 것과 같은 방식으로 QoS가 구성된다는 보장이 없습니다.

비즈니스용 Skype 서버 서비스 품질이 필요하지 않습니다. 현재 QoS를 사용하지 않는 경우 QoS를 설치하기 전에 서비스를 설치할 필요가 비즈니스용 Skype 서버. 현재 QoS를 사용하지 않는 경우 nm-server-w15-long을 설치하기 전에 QoS 서비스를 설치할 필요가 없습니다. 네트워크에서 상당한 양의 패킷 손실을 경험하는 경우 이 문제를 완화하기 위해 대역폭을 추가하는 것이 좋으며, 대역폭을 추가하는 것이 불가능한 경우에 QoS를 대신 구현할 수 있습니다.

비즈니스용 Skype 서버 서비스 품질에 대한 모든 지원을 제공합니다. 즉, 이미 QoS를 사용하고 있는 조직에서 QoS를 기존 네트워크 인프라에 비즈니스용 Skype 서버 수 있습니다. 이 작업을 수행하려면 다음 작업을 수행해야 합니다.

  - 를 기반으로 하지 않는 장치에 대해 [QoS를 Windows.](enabling-qos-for-devices-that-are-not-based-on-windows.md) 기본적으로 다른 운영 체제를 실행하는 컴퓨터 및 기타 장치(예: iPhone)에 대해서는 QoS를 사용하지 않도록 설정됩니다. 디바이스에 대한 비즈니스용 Skype 서버 및 사용하지 않도록 설정할 수는 있습니다. 그러나 일반적으로 제품을 사용하여 이러한 장치에서 사용되는 DSCP 코드를 수정할 수는 없습니다.

  - [회의,](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)응용 프로그램 및 중재 서버에 대한 포트 범위 및 서비스 품질 정책 구성 오디오 및 비디오와 같은 여러 패킷 유형에 대해 고유한 포트 집합을 예약해야 합니다. 이 비즈니스용 Skype 서버 속성 값을 True 또는 False로 설정하여 서비스 품질을 설정하거나 사용하지 않도록 설정하지 않습니다. 대신 포트 범위를 구성한 다음 그룹 정책을 만들고 적용하여 서비스 품질을 사용하도록 설정할 수 있습니다. 나중에 QoS를 사용하지 않도록 결정한 경우 적절한 그룹 정책 개체를 제거하기만 하여 서비스 품질을 "사용하지 않도록 설정"할 수 있습니다.

  - [에지 서버에](configuring-port-ranges-for-your-edge-servers.md)대한 포트 범위 및 서비스 품질 정책 구성 반드시 필요한 것은 아니지만 다른 서버와 동일한 포트 범위를 사용하도록 에지 서버를 구성할 수 있습니다. 서비스 품질 정책 구성은 에지 서버의 내부 측면에만 수행해야 합니다. QoS는 인터넷이 아닌 내부 네트워크에서 사용하도록 설계되어 있기 때문입니다.

- [2013에서](configuring-port-ranges-for-your-skype-clients.md) 클라이언트에 대한 포트 범위 및 서비스 품질 정책 비즈니스용 Skype 서버  이러한 포트 범위는 클라이언트 컴퓨터에만 적용하며 일반적으로 서버에 구성된 포트 범위와 다릅니다. 이 비즈니스용 Skype 서버 다른 운영 체제에 대해 QoS를 Windows 지원하지 Windows 10.


