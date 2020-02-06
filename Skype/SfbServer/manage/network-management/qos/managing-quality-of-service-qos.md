---
title: QoS (서비스 품질) 관리
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: QoS (서비스 품질)는 일부 조직에서 오디오 및 비디오 통신을 위한 최적의 최종 사용자 환경을 제공 하는 데 사용 되는 네트워킹 기술입니다.
ms.openlocfilehash: 821ebb1cd6a101856f4fbc4fb3428ecba7674245
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817364"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 QoS (서비스 품질) 관리


QoS (서비스 품질)는 일부 조직에서 오디오 및 비디오 통신을 위한 최적의 최종 사용자 환경을 제공 하는 데 사용 되는 네트워킹 기술입니다. QoS는 대역폭이 제한 되는 네트워크에서 가장 일반적으로 사용 됩니다. 사용 가능한 대역폭에 대해 많은 수의 네트워크 패킷이 경쟁 됨에 따라 관리자가 패킷에 더 높은 우선 순위를 지정할 수 있는 방법을 제공 하는 서비스 품질 오디오 또는 비디오 데이터 운반. 이러한 패킷에 보다 높은 우선 순위를 부여 함으로써 오디오 및 비디오 통신은 파일 전송, 웹 검색 또는 데이터베이스 백업과 관련 된 네트워크 세션 보다 더 빠르게 완료 될 수 있습니다. 이는 파일 전송 또는 데이터베이스 백업에 사용 되는 네트워크 패킷에 "최상 작업량" 우선 순위를 할당 하기 때문입니다.


> [!NOTE]  
> 일반적인 규칙에 따라 서비스 품질은 내부 네트워크의 통신 세션에만 적용 됩니다. QoS를 구현할 때 패킷 표시를 지원 하도록 서버와 라우터를 구성 합니다. 그러나 이러한 장치를 구성 하 여 특정 방식으로 패킷 표시를 지원 하도록 할 수 있습니다. 인터넷 이나 다른 네트워크에서 서비스 품질이 지원 되는 것으로 간주할 수는 없습니다. 다른 네트워크에서 서비스를 지 원하는 경우에도 QoS는 네트워크에서 서비스를 구성한 방법과 동일 하 게 구성 된다는 보장이 없습니다.

비즈니스용 Skype 서버에는 서비스 품질이 필요 하지 않습니다. 현재 QoS를 사용 하지 않는 경우 비즈니스용 Skype 서버를 설치 하기 전에 서비스를 설치할 필요가 없습니다. 네트워크에서 상당한 양의 패킷 손실이 발생 하는 경우이 문제를 해결 하는 데 권장 되는 방법은 대역폭을 더 추가 하는 것입니다. 더 이상 대역폭을 추가할 수 없는 경우 서비스 품질을 대신 구현할 수 있습니다.

비즈니스용 skype Server는 서비스 품질을 완전 하 게 지원 하며,이는 이미 QoS를 사용 하 고 있는 조직이 비즈니스용 Skype 서버를 기존 네트워크 인프라에 쉽게 통합할 수 있다는 것을 의미 합니다. 이를 위해서는 다음 작업을 수행 해야 합니다.

  - [Windows를 기반으로 하지 않는 장치에 대해 QoS를 사용 하도록 설정](enabling-qos-for-devices-that-are-not-based-on-windows.md)합니다. 기본적으로 다른 운영 체제를 실행 하는 컴퓨터 및 기타 장치 (예: Iphone)에 QoS를 사용할 수 없습니다. 비즈니스용 Skype 서버를 사용 하 여 디바이스의 서비스 품질을 사용 하거나 사용 하지 않도록 설정할 수 있지만 일반적으로 제품을 사용 하 여 이러한 장치에서 사용 하는 DSCP 코드를 수정할 수는 없습니다.

  - [회의, 응용 프로그램, 중재 서버에 대 한 포트 범위 및 서비스 품질 정책을 구성](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)합니다. 오디오 및 비디오 등의 다른 패킷 유형에 대해 고유한 포트 집합을 예약 해야 합니다. 비즈니스용 Skype 서버에서 서비스 품질을 사용 하거나 사용 하지 않도록 설정 하지 않으면 속성 값을 True 또는 False로 설정 합니다. 대신 포트 범위를 구성한 다음 그룹 정책 만들기 및 적용을 통해 서비스 품질을 사용 하도록 설정 합니다. 나중에 QoS를 사용 하지 않기로 결정 한 경우 적절 한 그룹 정책 개체를 제거 하 여 서비스 품질을 "사용 안 함"으로 설정할 수 있습니다.

  - [Edge 서버의 포트 범위 및 서비스 품질 정책 구성](configuring-port-ranges-for-your-edge-servers.md) 필요 하지는 않지만 다른 서버와 동일한 포트 범위를 사용 하도록 Edge 서버를 구성할 수 있습니다. 서비스 품질 정책 구성은 Edge 서버의 내부 측면 에서만 수행 해야 합니다. 서비스 품질은 인터넷이 아닌 내부 네트워크에서 사용 하도록 설계 되었기 때문입니다.

- [비즈니스용 Skype 서버에서 클라이언트에 대 한 포트 범위 및 서비스 품질 정책 구성](configuring-port-ranges-for-your-skype-clients.md)  이러한 포트 범위는 클라이언트 컴퓨터에만 적용 되며 일반적으로 서버에 구성 된 포트 범위와는 다릅니다. 비즈니스용 Skype 서버는 Windows 10이 아닌 Windows 운영 체제에 대 한 QoS를 지원 하지 않는다는 점에 유의 하세요.


