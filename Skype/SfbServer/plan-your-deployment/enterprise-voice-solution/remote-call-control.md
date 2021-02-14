---
title: 비즈니스용 Skype의 원격 통화 제어 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 원격 통화 제어는 이전 버전의 Lync Server에서 제공된 기능으로, 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있도록 합니다. 비즈니스용 Skype 서버에서는 이 기능이 직장 전화로 대체됩니다. 비즈니스용 Skype 서버 2015 및 앞으로의 클라이언트 버전에서는 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없습니다. 이 경우 사용할 수 있도록 제거되었습니다.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813518"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>비즈니스용 Skype의 원격 통화 제어 계획
 
원격 통화 제어는 이전 버전의 Lync Server에서 제공된 기능으로, 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있도록 합니다. 비즈니스용 Skype 서버에서는 이 기능이 직장 전화로 대체됩니다.  *비즈니스용 Skype 서버 2015 및 앞으로의 클라이언트 버전에서는 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없습니다. 이 경우 사용할 수 있도록 제거되었습니다.* 
  
 Lync Server를 실행하는 프런트 엔드 서버에 있는 조직의 원격 통화 제어 사용자는 비즈니스용 Skype 클라이언트를 사용 중인 경우에도 계속 원격 통화 제어를 사용할 수 있습니다. 그러나 비즈니스용 Skype 서버에 있는 사용자의 경우 원격 통화 제어가 지원되지 않습니다. 서버/클라이언트 조합 및 원격 통화 제어를 지원할 수 있는지 아니면 직장을 통해 전화를 걸 수 있는지에 대한 다음 표를 참조합니다.
  
||**Skype UI가 사용하도록 설정된 비즈니스용 Skype 클라이언트**|**Lync UI가 사용하도록 설정된 비즈니스용 Skype 클라이언트**|**비즈니스용 Skype 2016 클라이언트**|**Lync 2013 클라이언트**|**Lync 2010 클라이언트**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| 비즈니스용 Skype 서버 <br/> |직장을 통한 통화  <br/> |1  <br/> |직장을 통한 통화  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |원격 통화 제어  <br/> |원격 통화 제어  <br/> |1  <br/> |원격 통화 제어  <br/> |원격 통화 제어  <br/> |
| Lync Server 2010 <br/> |원격 통화 제어  <br/> |원격 통화 제어  <br/> |1  <br/> |원격 통화 제어  <br/> |원격 통화 제어  <br/> |
   
1. 두 기능 모두 지원되지 않습니다.
  
자세한 내용은 Lync Server 2013 설명서의 원격 통화 제어를 참조하십시오. [](https://go.microsoft.com/fwlink/p/?LinkId=530208)
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 직장 전화 계획](call-via-work.md)
  
[비즈니스용 Skype에 대한 데스크톱 클라이언트 기능 비교](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[비즈니스용 Skype 통화를 하지만 오디오에 PBX 책상 전화 사용](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

