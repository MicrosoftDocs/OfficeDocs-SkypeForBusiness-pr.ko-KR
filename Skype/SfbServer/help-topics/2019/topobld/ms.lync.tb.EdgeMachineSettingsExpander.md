---
title: Edge 기계 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: Edge 서버 풀의 서버에 대 한 속성을 편집 하려면 다음을 수행 합니다.
ms.openlocfilehash: a6683766ddbfd11cd38d2d50b80a25c057b302bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188976"
---
# <a name="edge-machine-settings-expander"></a>Edge 기계 설정 확장기
 
Edge 서버 풀의 서버에 대 한 속성을 편집 하려면 다음을 수행 합니다.
  
정규화 된 도메인 이름 (FQDN)을 편집 하 여 **내부 이름 또는 fqdn** 을 변경할 수 있습니다. FQDN은 DNS (Domain Name System) 호스트 (A) 레코드와 내부에 지 네트워크 인터페이스에 대해 서버에 할당 된 인증서의 주체 이름과 일치 해야 합니다. **내부 IP 주소의** 값은 경계 네트워크 디자인을 기준으로 내부 네트워크로 정의 되는 네트워크 인터페이스에 할당 된 IP 주소를 정의 합니다.
  
다음 세 개의 대화 상자 섹션에서는이 Edge 서버의 외부 구성에 대 한 IP 주소를 정의 합니다. IP 주소를 변경 하는 기능은 **웹 회의에 별도의 FQDN과 IP 주소를 사용 하도록** 설정 하 고 Edge 서버 풀 수준의 속성 설정에서 A/V에 영향을 받습니다.
  
## <a name="sip-access"></a>SIP 액세스

SIP (세션 시작 프로토콜) 액세스를 위해 네트워크 인터페이스에 할당 된 외부 IP 주소를 편집 합니다. 이 IP 주소는 공용 IP 주소 이거나 개인 IP 주소 범위의 주소 일 수 있습니다.
  
> [!NOTE]
> 그룹 설정 페이지에 대 한 **별도의 FQDN과 IP 주소를 사용 하도록 설정 하** 는 경우 SIP 액세스에 대 한 ip 주소만 편집할 수 있습니다.
  
## <a name="web-conferencing"></a>웹 회의

웹 회의를 위해 네트워크 인터페이스에 할당 된 외부 IP 주소를 편집 합니다. 이 IP 주소는 공용 IP 주소 이거나 개인 IP 주소 범위의 주소 일 수 있습니다.
  
## <a name="audiovideo"></a>오디오/비디오

오디오/비디오 (A/V) 용 네트워크 인터페이스에 할당 된 외부 IP 주소를 편집 합니다. 이 IP 주소는 공용 IP 주소 이거나 개인 IP 주소 범위의 주소 일 수 있습니다.
  
**NAT 사용 공용 IP 주소** 에 대 한 설정은 A/V 네트워크 인터페이스 또는 일반 서버에 대 한 외부 인터페이스에 사용 되는 공용 주소입니다. **별도의 FQDN과 웹 회의에 대 한 IP 주소를 설정 하 고 A/V** 를 사용 하는 경우이 공용 IP 주소는 세 개의 외부 인터페이스 모두에 사용 됩니다.
  

