---
title: PSTN 게이트웨이 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 공중 전화망(PSTN) 게이트웨이의 설정을 편집하거나 수정하려면 다음 필드를 수정합니다.
ms.openlocfilehash: 7b0d823a21f2e0e9eb1e75a37365095877885cac
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794176"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN 게이트웨이 설정 확장기
 
공중 전화망(PSTN) 게이트웨이의 설정을 편집하거나 수정하려면 다음 필드를 수정합니다.
  
게이트웨이 FQDN 또는 IP 주소는 필수 항목이며 DNS(Domain Name System) 호스트(A) 레코드, 정적 HOSTS 파일 항목 또는 PSTN 게이트웨이의 IP 주소에 의해 정의된 대로 PSTN 게이트웨이의 **FQDN(정규화된 도메인 이름)** 을 정의합니다.
  
SIP 전송 프로토콜은 TCP(Transmission Control Protocol) 또는 TLS(전송 계층 보안)일 수 있습니다. TLS가 기본값입니다. 게이트웨이가 지원하는 프로토콜에 대해서는 게이트웨이 공급업체 설명서를 참조하세요. 기본값은 TLS이며 게이트웨이에서 TLS를 지원하는 경우 기본값이 보다 안전한 선택으로 간주되어야 합니다.
  
게이트웨이에 대해 IPv4 및 IPv6을 사용하도록 설정할지를 선택합니다.
  
**대체 미디어 IP 주소** 는 배포 된 PSTN 게이트웨이에 대해 일반적으로 SIP 트래픽용으로 전용으로 설정 된 기본 구성 ip 주소 보다 미디어 트래픽에 대 한 다른 IP 주소를 갖는 조정 서버에 대 한 정의입니다. 이 매개 변수를 정의하면 PSTN 게이트웨이에서 미디어에 대해 다른 네트워크 인터페이스 또는 경로를 지원합니다. 이 주소를 비워 두면 PSTN 게이트웨이에서 미디어에 대해 대체 경로를 지원하지 않습니다.
  

