---
title: 통화 제어 배포에 대한 통화 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: CAC(통화 제어)를 배포하기 위한 최종 검사 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 70fadce643fa21d9551a6a6ba26a2883579eee1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594146"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>통화 입장 제어 배포: 통화를 위한 최종 비즈니스용 Skype 서버
 
CAC(통화 제어)를 배포하기 위한 최종 검사 비즈니스용 Skype 서버 Enterprise Voice. 
  
다음 검사 목록을 사용하여 CAC(통화 입력 제어)를 배포하는 데 필요한 모든 구성 작업을 완료한지 확인할 수 있습니다.
  
- 하나 이상의 에지 서버가 배포된 경우 각 외부 인터페이스 IP 주소는 비트 마스크가 32인 네트워크 구성 설정의 서브넷 목록에 추가되어야 합니다. 또한 이 서브넷(IP 주소)을 A/V 에지 서비스가 배포된 지리적 위치의 네트워크 사이트 ID와 연결해야 합니다.
    
    > [!NOTE]
    > CAC를 구현하는 데 에지 서버가 필요하지 않습니다. 
  
- CAC가 사용하도록 설정되어 있는지 확인합니다(에 지정된 경우 [에서](enable-call-admission-control.md)통화 비즈니스용 Skype 서버.
    
- CAC가 모든 중앙 사이트에서 사용하도록 설정되었는지 확인합니다. 이 수행은 토폴로지 작성기에서 수행될 수 있습니다. 게시할 때 경고가 생성되는 경우  *무시하지*  마십시오.
    
- 엔터프라이즈 네트워크에서 관리된 모든 서브넷이 네트워크 구성 설정에서 구성되었는지 확인합니다. 또한 에서 네트워크 지역, 사이트 및 서브넷 배포에 설명된 모든 서브넷을 네트워크 사이트에 연결해야 [비즈니스용 Skype.](deploy-network.md)
    
- 모든 프런트 엔드 서버, SBA(Survivable Branch Appliance), 오디오/비디오 회의 서버(별도의 풀에 있는 경우), 중재 서버의 서브넷이나 IP 주소가 네트워크 구성 설정에서 구성되었는지 확인합니다.
    

