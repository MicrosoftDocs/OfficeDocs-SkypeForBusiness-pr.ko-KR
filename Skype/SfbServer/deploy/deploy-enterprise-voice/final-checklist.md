---
title: 통화 허용 제어 배포 최종 비즈니스용 Skype Server의 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype Server Enterprise Voice에서 호출 허용 제어 (CAC) 배포에 대 한 최종 검사 목록입니다.
ms.openlocfilehash: 5d5e4f6f40143bfec2a215e6bc9a54817d53da1b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767231"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>통화 허용 제어 배포: 비즈니스용 Skype 서버에 대 한 최종 검사 목록
 
비즈니스용 Skype Server Enterprise Voice에서 호출 허용 제어 (CAC) 배포에 대 한 최종 검사 목록입니다. 
  
다음 검사 목록을 사용 하 여 CAC (Call 허용 제어)를 배포 하는 데 필요한 모든 구성 작업을 완료 했는지 확인 합니다.
  
- 하나 이상의 Edge 서버가 배포 된 경우 각 외부 인터페이스 IP 주소를 네트워크 구성 설정의 서브넷 목록에 추가 해야 하며 비트 마스크는 32입니다. 또한이 서브넷 (IP 주소)을 A/V Edge 서비스가 배포 된 지리적 위치에 대 한 네트워크 사이트 ID와 연결 해야 합니다.
    
    > [!NOTE]
    > Edge 서버는 CAC를 구현 하지 않아도 됩니다. 
  
- [비즈니스용 Skype 서버의 통화 허용 제어 사용](enable-call-admission-control.md)에 지정 된 대로 CAC가 사용 하도록 설정 되어 있는지 확인 합니다.
    
- 모든 중앙 사이트에서 CAC가 사용 하도록 설정 되어 있는지 확인 합니다. 토폴로지 작성기를 통해이 작업을 수행할 수 있습니다. 게시할 때 경고가 생성 되 면이를 무시 *하지 마세요* .
    
- 엔터프라이즈 네트워크에서 관리 되는 모든 서브넷이 네트워크 구성 설정에서 구성 되어 있는지 확인 합니다. 또한 [비즈니스용 Skype의 네트워크 지역, 사이트 및 서브넷 배포](deploy-network.md)에 설명 된 대로 모든 서브넷을 네트워크 사이트에 연결 하는 것이 중요 합니다.
    
- 모든 프런트 엔드 서버의 서브넷 또는 IP 주소, Survivable Branch 기기 (SBAs), 오디오/비디오 회의 서버 (별도의 풀에 있는 경우) 및 중재 서버가 네트워크 구성 설정에 구성 되어 있는지 확인 합니다.
    

