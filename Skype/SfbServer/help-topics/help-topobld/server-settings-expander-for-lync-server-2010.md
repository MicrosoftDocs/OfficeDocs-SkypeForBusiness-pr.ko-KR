---
title: Lync Server 2010용 서버 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 이 컴퓨터의 속성을 편집 하려면 다음을 수행 합니다.
ms.openlocfilehash: 0f8a1a31c593c792ff4872d0e104c6aadabcd819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819300"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Lync Server 2010용 서버 설정 확장기
 
이 컴퓨터의 속성을 편집 하려면 다음을 수행 합니다.
  
- 이 컴퓨터의 **FQDN (정규화 된 도메인 이름)** 을 편집 합니다. 이 항목은 DNS (domain name system)에 정의 된 컴퓨터 이름과이 컴퓨터에 연결 된 인증서의 주체 대체 이름 (SAN) 또는 주체 이름 (SN)과 일치 해야 합니다.
    
- 다음 중 하나를 선택 합니다.
    
    **구성 된 모든 ip 주소 사용**: 컴퓨터에서 구성 된 모든 ip 주소를 사용 하려면 선택 합니다.
    
    > [!IMPORTANT]
    > 컴퓨터에 여러 IP 주소가 있는 경우이 컴퓨터와 연결 된 서비스가 모든 서비스에 대해 모든 IP 주소를 사용 한다는 것을 알아야 합니다. 수신 서버나 서비스에 특정 IP 주소 및 포트의 통신이 필요한 경우 서비스에서 수신 대기할 IP 주소를 선택 하지 못할 수 있습니다. 
  
    **선택한 IP 주소로 서비스 사용 제한**:이 컴퓨터가 배포의 다른 컴퓨터 및 풀에서 통신을 위해 수신 대기할 **기본 ip 주소** 에 대 한 특정 ip 주소를 정의 하려면이 옵션을 선택 합니다. 컴퓨터와 서비스가 통신을 수신 대기 하 고 정의 된 PSTN 게이트웨이 또는 IP-PBX에 게 통신을 보내는 특정 IP 주소에 대 한 **PSTN IP 주소** 를 정의 합니다.
    

