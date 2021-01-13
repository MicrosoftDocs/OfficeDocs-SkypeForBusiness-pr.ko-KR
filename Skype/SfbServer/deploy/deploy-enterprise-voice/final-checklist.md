---
title: 비즈니스용 Skype 서버에 대한 통화 제어 배포 최종 검사 목록
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 비즈니스용 Skype 서버 2013에서 CAC(통화 제어)를 배포하기 위한 최종 Enterprise Voice.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830838"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>통화 제어 배포: 비즈니스용 Skype 서버의 최종 검사 목록
 
비즈니스용 Skype 서버 2013에서 CAC(통화 제어)를 배포하기 위한 최종 Enterprise Voice. 
  
다음 검사 목록을 사용하여 CAC(통화 제어)를 배포하는 데 필요한 모든 구성 작업을 완료한지 확인할 수 있습니다.
  
- 하나 이상의 에지 서버가 배포된 경우 각 외부 인터페이스 IP 주소는 비트 마스크가 32인 네트워크 구성 설정의 서브넷 목록에 추가되어야 합니다. 또한 이 서브넷(IP 주소)을 A/V 에지 서비스가 배포된 지리적 위치의 네트워크 사이트 ID와 연결해야 합니다.
    
    > [!NOTE]
    > CAC를 구현하는 데 에지 서버가 필요하지 않습니다. 
  
- CAC가 사용하도록 설정되어 있는지 확인합니다.(비즈니스용 Skype 서버에서 통화 [입장](enable-call-admission-control.md)제어 사용에 지정된 경우).
    
- CAC가 모든 중앙 사이트에서 사용하도록 설정되었는지 확인합니다. 이 수행은 토폴로지 작성기에서 수행될 수 있습니다. 게시할 때 경고가 생성되는 경우  *무시하지*  마십시오.
    
- 엔터프라이즈 네트워크에서 관리된 모든 서브넷이 네트워크 구성 설정에서 구성되었는지 확인합니다. 또한 비즈니스용 Skype의 네트워크 지역, 사이트 및 서브넷 배포에 설명된 모든 서브넷을 네트워크 사이트에 [연결해야 합니다.](deploy-network.md)
    
- 모든 프런트 엔드 서버, SBA(Survivable Branch Appliance), 오디오/비디오 회의 서버(별도의 풀에 있는 경우), 중재 서버의 서브넷이나 IP 주소가 네트워크 구성 설정에서 구성되었는지 확인합니다.
    

