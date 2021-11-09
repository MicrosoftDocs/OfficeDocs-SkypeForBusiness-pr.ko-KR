---
title: PSTN 게이트웨이 설정 확장기
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 공중 전화망(PSTN) 게이트웨이의 설정을 편집하거나 수정하려면 다음 필드를 수정합니다.
ms.openlocfilehash: ce3b7801182659062f1c623b0266160af8de88c5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832192"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN 게이트웨이 설정 확장기
 
공중 전화망(PSTN) 게이트웨이의 설정을 편집하거나 수정하려면 다음 필드를 수정합니다.
  
게이트웨이 FQDN 또는 IP 주소는 필수 항목이며 DNS(Domain Name System) 호스트(A) 레코드, 정적 HOSTS 파일 항목 또는 PSTN 게이트웨이의 IP 주소에 의해 정의된 대로 PSTN 게이트웨이의 **FQDN(정규화된 도메인 이름)** 을 정의합니다.
  
SIP 전송 프로토콜은 TCP(Transmission Control Protocol) 또는 TLS(전송 계층 보안)일 수 있습니다. TLS가 기본값입니다. 게이트웨이가 지원하는 프로토콜에 대해서는 게이트웨이 공급업체 설명서를 참조하십시오. 기본값은 TLS이며 게이트웨이에서 TLS를 지원하는 경우 기본값이 보다 안전한 선택으로 간주되어야 합니다.
  
게이트웨이에 대해 IPv4 및 IPv6을 사용하도록 설정할지를 선택합니다.
  
**대체 미디어 IP 주소** 는 배포된 PSTN 게이트웨이에서 일반적으로 SIP 트래픽 전용인 기본값으로 구성된 IP 주소와 다른 IP 주소를 미디어 트래픽에 사용하는 중재 서버에 대한 정의입니다. 이 매개 변수를 정의하면 PSTN 게이트웨이에서 미디어에 대해 다른 네트워크 인터페이스 또는 경로를 지원합니다. 이 주소를 비워 두면 PSTN 게이트웨이에서 미디어에 대해 대체 경로를 지원하지 않습니다.
  

