---
title: 사용자에 대한 음성 사용량 및 트래픽 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 다음 메트릭을 사용하여 각 사이트의 사용자 트래픽과 해당 트래픽을 지원하는 데 필요한 포트 수를 예측할 수 있습니다.
ms.openlocfilehash: 8661bf6c0222228ec22f582ebae0167cd23242a8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629550"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>사용자에 대한 음성 사용량 및 트래픽 비즈니스용 Skype 서버
 
다음 메트릭을 사용하여 각 사이트의 사용자 트래픽과 해당 트래픽을 지원하는 데 필요한 포트 수를 예측할 수 있습니다.
  
> **경량 트래픽**(매시간 사용자당 PSTN 호출 하나)의 경우 포트당 사용자 15명
> 
> **중간 정도의 트래픽**(매시간 사용자당 PSTN 호출 두 개)의 경우 포트당 사용자 10명
> 
> **높은 트래픽**(매시간 사용자당 PSTN 호출 세 개 이상)의 경우 포트당 사용자 5명
    
포트 수에 따라 필요한 중재 서버 및 게이트웨이의 수가 결정됩니다. 대부분의 조직에서 배포를 고려하는 PSTN(공중 전화망) 게이트웨이의 크기는 포트 2개에서 포트 960개까지 다양합니다. 훨씬 더 큰 게이트웨이도 있지만 이러한 게이트웨이는 주로 전화 서비스 공급자가 사용합니다.
  
예를 들어 사용자 수가 1만 명이고 트래픽은 중간 정도인 조직의 경우 1,000개의 포트가 필요합니다. 필요한 게이트웨이 수는 총 게이트웨이 용량에 따라 결정되는 필요한 총 포트 수와 같습니다.
  

