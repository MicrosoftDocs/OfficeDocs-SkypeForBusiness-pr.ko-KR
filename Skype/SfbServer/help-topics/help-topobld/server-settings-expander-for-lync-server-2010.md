---
title: Lync Server 2010에 대한 서버 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 이 컴퓨터의 속성을 편집하려면 다음을 수행합니다.
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215699"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Lync Server 2010에 대한 서버 설정 확장기
 
이 컴퓨터의 속성을 편집하려면 다음을 수행합니다.
  
- 이 컴퓨터의 **FQDN(정규화된 도메인 이름)** 을 편집합니다. 이 항목은 이 컴퓨터와 연결된 인증서의 SAN(주체 대체 이름) 또는 SN(주체 이름)과 DNS(Domain Name System)에 정의된 컴퓨터 이름과 일치해야 합니다.
    
- 다음 중 하나를 선택합니다.
    
    **구성된 모든 IP 주소 사용**: 컴퓨터에서 구성된 모든 IP 주소를 사용하려면 이 옵션을 선택합니다.
    
    > [!IMPORTANT]
    > 컴퓨터의 IP 주소가 여러 개인 경우에는 이 컴퓨터와 연결된 서비스에서 모든 서비스에 대해 모든 IP 주소를 사용한다는 점을 염두에 두어야 합니다. 수신 대기 서버 또는 서비스에서 특정 IP 주소 및 포트의 통신을 수행할 것으로 예상되는 경우 해당 서비스는 수신 대기할 최적의 IP 주소를 선택하지 못할 수도 있습니다. 
  
    **선택한 IP 주소로 서비스 사용 제한**: 이 컴퓨터가 배포에 포함된 다른 컴퓨터 및 풀로부터의 통신을 위해 수신 대기할 **기본 IP 주소**에 해당하는 특정 IP 주소를 정의하려면 이 옵션을 선택합니다. 컴퓨터와 서비스가 통신을 위해 수신 대기하고 정의된 PSTN 게이트웨이 또는 IP-PBX로 통신 내용을 보내는 특정 IP 주소에 대해 **PSTN IP 주소**를 정의합니다.
    

