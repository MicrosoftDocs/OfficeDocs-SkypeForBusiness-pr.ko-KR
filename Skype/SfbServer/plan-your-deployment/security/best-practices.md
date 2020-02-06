---
title: 비즈니스용 Skype 서버에서 핵심 인프라에 대 한 모범 사례
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 하드웨어 중복성 보장, 정전 으로부터 보호, 보안 업데이트 및 바이러스 백신 조치, 서버 활동 모니터링 등의 방법을 사용 하 여 시스템에서 내결함성 설계 단계를 이미 수행 했을 수 있습니다. 이러한 방법을 통해 비즈니스용 Skype 서버 인프라 뿐만 아니라 전체 네트워크에 대 한 혜택을 얻을 수 있습니다. 이러한 방법을 구현 하지 않은 경우 비즈니스용 Skype 서버를 배포 하기 전에이를 수행 하는 것이 좋습니다.
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815686"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 핵심 인프라에 대 한 모범 사례
 
하드웨어 중복성 보장, 정전 으로부터 보호, 보안 업데이트 및 바이러스 백신 조치, 서버 활동 모니터링 등의 방법을 사용 하 여 시스템에서 내결함성 설계 단계를 이미 수행 했을 수 있습니다. 이러한 방법을 통해 비즈니스용 Skype 서버 인프라 뿐만 아니라 전체 네트워크에 대 한 혜택을 얻을 수 있습니다. 이러한 방법을 구현 하지 않은 경우 비즈니스용 Skype 서버를 배포 하기 전에이를 수행 하는 것이 좋습니다.
  
비즈니스용 Skype 서버 배포의 서버가 가동 중지 시간이 발생할 수 있는 우발적 이거나 체계적 손상 으로부터 보호 하기 위해 다음과 같은 예방 조치를 취해야 합니다.
  
- 보안 업데이트를 사용 하 여 서버를 최신 상태로 유지 합니다. Microsoft 보안 알림 서비스에 가입 하면 Microsoft 제품에 대 한 보안 공지 릴리스 알림을 즉시 받을 수 있습니다. 구독 하려면 [Microsoft 기술 보안 알림 웹 사이트로](https://go.microsoft.com/fwlink/p/?LinkId=145202)이동 합니다.
    
- 액세스 권한이 올바르게 설정 되어 있는지 확인 합니다.
    
- 무단 액세스를 방지 하는 물리적 환경에서 서버를 유지 합니다. 모든 서버에 적절 한 바이러스 백신 소프트웨어가 설치 되어 있는지 확인 합니다. 최신 바이러스 서명 파일을 사용 하 여 소프트웨어를 최신 상태로 유지 합니다. 바이러스 백신 응용 프로그램의 자동 업데이트 기능을 사용 하 여 바이러스 서명을 최신 상태로 유지 합니다.
    
- 비즈니스용 Skype 서버를 설치 하는 컴퓨터에서는 필요 하지 않은 Windows Server 운영 체제 서비스를 사용 하지 않도록 설정 하는 것이 좋습니다.
    
- 서버를 일관 되 게 제어 하 고 완전 한 격리, 대체 또는 실패 한 디스크의 적절 하 고 안전 하 게 폐기 하지 않는 한, 전체 볼륨 암호화 시스템을 사용 하 여 데이터가 저장 되는 운영 체제와 디스크 드라이브를 암호화 합니다. 드라이브나.
    
- 서버에 대 한 물리적 액세스를 매우 엄격 하 게 제어할 수 있는 경우가 아니면 서버의 모든 외부 직접 메모리 액세스 (DMA) 포트를 사용 하지 않도록 설정 합니다. 비교적 쉽게 초기화할 수 있는 DMA 기반 공격으로, 개인 암호화 키와 같은 중요 한 정보를 제공할 수 있습니다.
    

