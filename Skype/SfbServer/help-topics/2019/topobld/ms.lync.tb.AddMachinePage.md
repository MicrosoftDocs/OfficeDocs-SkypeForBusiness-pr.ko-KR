---
title: 서버 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 기존 서버 풀(풀이 다음 중 하나에 해당)에 새 서버를 추가하려면
ms.openlocfilehash: 12a8e65f85120bea9d6e9a466bbca4f7d1d070b6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857805"
---
# <a name="add-server"></a>서버 추가
 
기존 서버 풀(풀이 다음 중 하나에 해당)에 새 서버를 추가하려면
  
- Enterprise Edition 프런트 엔드 서버
    
- 디렉터 서버
    
- 중재 서버
    
- 오디오/비디오 회의 서버
    
- 신뢰할 수 있는 응용 프로그램 서버
    
각 새 풀 서버의 요구 사항은 서로 다릅니다. 다음 섹션에서 기존 풀에 추가할 서버 유형을 찾아 각 서버 유형에 대해 정의된 대로 요청된 정보를 제공합니다. 새 풀 서버를 정의하려면 요청된 정보를 제공합니다.
  
 **Enterprise Edition 프런트 엔드 서버**
  
- DNS(Domain Name System)에 정의된 대로 새 서버의 FQDN(정규화된 도메인 이름)
    
- 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있음을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 새 서버에 대한 특정 주소를 입력할 수 있습니다. 입력한 IP 주소는 호스팅된 서비스에 응답하는 유일한 IP 주소입니다.
    
- 프런트 엔드 서버에 중재 서버가 배치된 경우 **PSTN IP 주소** 를 정의합니다.
    
- 이 서버에 대해 IPv6을 사용하도록 설정하려면 **IPv6 사용** 을 선택합니다.
    
  **디렉터 서버**
  
- DNS에 정의된 대로 새 서버의 FQDN
    
- 컴퓨터에 정의되어 있는 모든 IP 주소가 사용됨을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 새 서버에 대한 특정 IP 주소를 입력합니다. 입력한 IP 주소는 호스팅된 서비스에 응답하는 유일한 IP 주소입니다.
    
  **중재 서버**
  
- DNS에 정의된 대로 새 서버의 FQDN
    
- 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있음을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 기본 IP 주소로 새 서버에 대한 특정 IP 주소를 입력하고 PSTN(공중 전화망) IP 주소에 대한 IP 주소를 입력합니다. 입력한 IP 주소는 지정된 서비스에 응답하는 유일한 IP 주소입니다.
    
    > [!NOTE]
    > 중재 서버의 경우 기본적으로 기본 IP 주소로 입력한 IP 주소와 PSTN IP 주소가 동일합니다. 전용 네트워크 인터페이스를 사용하거나 동일한 네트워크 인터페이스에서 서로 다른 IP 주소를 사용하는 경우 IP 주소를 서로 다르게 정의할 수 있습니다. 네트워크 인터페이스가 두 개이고 이 중 하나는 로컬 네트워크 연결용이고 다른 하나는 PSTN 연결용인 경우 서로 다른 IP 주소를 할당해야 합니다. 
  
  **A/V 회의 서버**
  
- DNS에 정의된 대로 새 서버의 FQDN
    
- 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있음을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 새 서버에 대한 특정 주소를 입력할 수 있습니다. 입력한 IP 주소는 호스팅된 서비스에 응답하는 유일한 IP 주소입니다.
    
  **신뢰할 수 있는 응용 프로그램 서버**
  
- DNS에 정의된 새 서버의 FQDN
    

