---
title: 호출 허용 컨트롤 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다. CAC용 네트워크를 구성한 후 대역폭 제한을 적용하려면 CAC를 사용하도록 설정해야 합니다.
ms.openlocfilehash: 23a881bf502a161a5a81e17a23a889ff1324f6c4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582772"
---
# <a name="call-admission-control-settings-expander"></a>호출 허용 컨트롤 설정 확장기
 
CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다. CAC용 네트워크를 구성한 후 대역폭 제한을 적용하려면 CAC를 사용하도록 설정해야 합니다. 
  
> [!NOTE]
> 제어판 또는 관리 셸 cmdlet을 사용하여 CAC를 사용하도록 설정할 수도 있습니다. 
  
사이트의 **속성 편집** 대화 상자의 **통화 허용 제어 설정** 섹션에서 다음 설정을 변경할 수 있습니다.
  
- **통화 가능 제어 사용** CAC를 사용하도록 설정하려면 이 설정을 선택합니다. 전체 네트워크에 대해 CAC를 사용하지 않도록 설정하려면 이 설정을 선택 취소합니다. CAC를 사용하도록 설정하려면 CAC용 네트워크를 구성해야 합니다. 자세한 내용은 배포 설명서에서 [Deploy call admission control in 비즈니스용 Skype 서버 2015를](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 참조하십시오.
    
- **통화 입장 제어를 실행할** 프런트 엔드 풀 CAC를 사용하도록 설정한 경우 CAC를 실행한 풀을 변경할 수 있습니다. 드롭다운 목록에서 풀을 선택합니다.
    

