---
title: 서버 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 기존 서버 풀에 새 서버를 추가 하려면 풀이 다음 중 하나입니다.
ms.openlocfilehash: c3593835fa1204b5ed4e74729a7ec369069e04f8
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798505"
---
# <a name="add-server"></a>서버 추가
 
기존 서버 풀에 새 서버를 추가 하려면 풀이 다음 중 하나입니다.
  
- Enterprise Edition 프런트 엔드 서버
    
- 디렉터 서버
    
- 중재 서버
    
- 오디오/비디오 회의 서버
    
- 신뢰할 수 있는 응용 프로그램 서버
    
각각의 새 풀 서버에는 서로 다른 요구 사항이 있습니다. 다음 섹션에서 기존 풀에 추가 하는 서버의 유형을 찾아 각 서버 유형에 대해 정의 된 대로 요청 된 정보를 제공 합니다. 새 풀 서버를 정의 하는 데 필요한 정보를 제공 합니다.
  
 **Enterprise Edition 프런트 엔드 서버**
  
- DNS (Domain Name System)에 정의 되어 있는 새 서버의 FQDN (정규화 된 도메인 이름)
    
- 컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있음을 의미 하는 **구성 된 모든 ip 주소 사용**을 선택 합니다. 또는 **선택한 IP 주소로 서비스 사용량 제한을** 선택 하 고 새 서버에 특정 주소를 입력할 수도 있습니다. 입력 된 IP 주소는 호스팅된 서비스에 대해 응답 하는 유일한 IP 주소입니다.
    
- 중재 서버가 프런트 엔드 서버에서 collocated 경우 **PSTN IP 주소** 를 정의 합니다.
    
- **Ipv6 사용** 을 선택 하 여이 서버에 ipv6을 사용 하도록 설정 합니다.
    
  **디렉터 서버**
  
- DNS에 정의 된 새 서버의 FQDN입니다.
    
- **구성 된 모든 ip 주소 사용**을 선택 하면 컴퓨터에 정의 된 모든 ip 주소가 사용 됩니다. 또는 **선택한 IP 주소로 서비스 사용량 제한을** 선택 하 고 새 서버에 특정 IP 주소를 입력 합니다. 입력 된 IP 주소는 호스팅된 서비스에 대해 응답 하는 유일한 IP 주소입니다.
    
  **중재 서버**
  
- DNS에 정의 된 새 서버의 FQDN입니다.
    
- 컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있음을 의미 하는 **구성 된 모든 ip 주소 사용**을 선택 합니다. 또는 **서비스 사용량을 선택한 IP 주소로 제한** 을 선택 하 고 새 서버의 특정 ip 주소를 기본 ip 주소로 입력 하 고 PSTN (공개 통신 네트워크) IP 주소의 ip 주소를 입력 합니다. 입력 한 IP 주소만 지정 된 서비스에 대해 응답 합니다.
    
    > [!NOTE]
    > 중재 서버의 경우 기본 IP 주소 및 PSTN IP 주소에 대해 입력 된 IP 주소가 기본적으로 동일 합니다. 전용 네트워크 인터페이스 또는 동일한 네트워크 인터페이스에서 별도의 IP 주소를 사용 하는 경우 IP 주소를 별도로 정의할 수 있습니다. 두 개의 네트워크 인터페이스가 있는데, 하나는 로컬 네트워크 연결을 위한 것이 고, 하나는 PSTN 연결에 사용 하는 경우 다른 IP 주소를 할당 해야 합니다. 
  
  **오디오/비디오 회의 서버**
  
- DNS에 정의 된 새 서버의 FQDN입니다.
    
- 컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있음을 의미 하는 **구성 된 모든 ip 주소 사용**을 선택 합니다. 또는 **선택한 IP 주소로 서비스 사용량 제한을** 선택 하 고 새 서버에 특정 주소를 입력할 수도 있습니다. 입력 된 IP 주소는 호스팅된 서비스에 대해 응답 하는 유일한 IP 주소입니다.
    
  **신뢰할 수 있는 응용 프로그램 서버**
  
- DNS에 정의 된 새 서버의 FQDN입니다.
    

