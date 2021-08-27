---
title: 에지 컴퓨터 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 에지 서버 풀에 있는 서버의 속성을 편집하려면 다음을 수행합니다.
ms.openlocfilehash: d297de5e4e503932387c1ba207959261cd19024c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579192"
---
# <a name="edge-machine-settings-expander"></a>에지 컴퓨터 설정 확장기
 
에지 서버 풀에 있는 서버의 속성을 편집하려면 다음을 수행합니다.
  
**내부 이름 또는 FQDN** 은 FQDN(정규화된 도메인 이름)을 편집하여 변경할 수 있습니다. FQDN은 내부 에지 네트워크 인터페이스에 대한 DNS(Domain Name System) 호스트(A) 레코드 및 서버에 할당된 인증서의 주체 이름과 일치해야 합니다. **내부 IP 주소** 값은 경계 네트워크 디자인을 기준으로 내부 네트워크로 정의된 네트워크 인터페이스에 할당되는 IP 주소를 정의합니다.
  
대화 상자의 다음 세 섹션에서는 이 에지 서버의 외부 구성에 대한 IP 주소를 정의합니다. IP 주소를 변경하는 기능은 에지 서버 풀 수준에서 속성 설정의 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 설정의 영향을 받습니다.
  
## <a name="sip-access"></a>SIP 액세스

SIP(Session Initiation Protocol) 액세스에 대한 네트워크 인터페이스에 할당된 외부 IP 주소를 편집합니다. 이 IP 주소는 공용 IP 주소이거나 개인 IP 주소 범위의 주소일 수 있습니다.
  
> [!NOTE]
> 풀 설정 페이지에서 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 설정이 사용하도록 설정되면 SIP 액세스에 대한 IP 주소만 편집할 수 있습니다.
  
## <a name="web-conferencing"></a>웹 회의

웹 회의에 대한 네트워크 인터페이스에 할당된 외부 IP 주소를 편집합니다. 이 IP 주소는 공용 IP 주소이거나 개인 IP 주소 범위의 주소일 수 있습니다.
  
## <a name="audiovideo"></a>오디오/비디오

A/V(오디오/비디오)에 대한 네트워크 인터페이스에 할당된 외부 IP 주소를 편집합니다. 이 IP 주소는 공용 IP 주소이거나 개인 IP 주소 범위의 주소일 수 있습니다.
  
**NAT 사용 공용 IP 주소가 사용됨** 에 대한 설정은 일반적으로 A/V 네트워크 인터페이스 또는 에지 서버에 대한 외부 인터페이스에 사용되는 공용 주소입니다. **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 설정을 사용하도록 설정하면 이 공용 IP 주소가 세 가지 외부 인터페이스 모두에 사용됩니다.
  

