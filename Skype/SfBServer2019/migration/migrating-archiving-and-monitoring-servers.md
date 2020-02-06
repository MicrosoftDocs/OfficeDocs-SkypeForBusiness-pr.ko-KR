---
title: 보관 및 모니터링 서버 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 레거시 환경에서 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 비즈니스용 Skype 서버 2019 환경에서 이러한 서버를 배포할 수 있습니다. 그러나 보관 및 모니터링 기능이 조직에 중요 한 경우 마이그레이션을 시작 하기 전에 비즈니스용 Skype Server 2019 파일럿 풀에 보관 및 모니터링을 추가 하 여 마이그레이션 프로세스 동안 기능을 사용할 수 있도록 해야 합니다.
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813456"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>보관 및 모니터링 서버 마이그레이션

레거시 환경에서 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 비즈니스용 Skype 서버 2019 환경에서 이러한 서버를 배포할 수 있습니다. 그러나 보관 및 모니터링 기능이 조직에 중요 한 경우 마이그레이션을 시작 하기 전에 비즈니스용 Skype Server 2019 파일럿 풀에 보관 및 모니터링을 추가 하 여 마이그레이션 프로세스 동안 기능을 사용할 수 있도록 해야 합니다. 
  
마이그레이션 프로세스 중 보관 및 모니터링 기능을 원하는 경우 다음 고려 사항을 염두에 두어야 합니다.
  
- 데이터 보관 및 모니터링 데이터는 비즈니스용 Skype 서버 2019 배포로 이동 되지 않습니다. 레거시 환경을 서비스 해제 하기 전에 백업 하는 데이터는 레거시 환경의 활동 기록이 됩니다.
    
- 레거시 버전의 보관 서버와 모니터링 서버는 레거시 프런트 엔드 풀에만 연결할 수 있습니다. 비즈니스용 Skype 서버 2019에서 보관 및 모니터링은 더 이상 서버 역할이 아니지만 비즈니스용 Skype Server 2019 프런트 엔드 풀에 통합 된 서비스입니다.
    
- 레거시 및 비즈니스용 Skype Server 2019 배포가 공존 하는 동안 레거시 버전의 보관 서버 및 모니터링 서버는 레거시 풀에 속한 사용자에 대 한 데이터를 수집 합니다. 비즈니스용 Skype Server 2019에서 보관 및 모니터링 비즈니스용 Skype Server 2019 풀에 속한 사용자에 게 데이터를 수집 합니다.
    
    > [!NOTE]
    > 새로운 비즈니스용 Skype Server 2019 파일럿 풀에 레거시 Edge 서버를 사용 하는 경우 이전 버전의 보관 서버는 레거시 풀에 있고 비즈니스용 Skype에서 보관 하는 사용자에 대 한 데이터를 계속 수집 합니다. 서버 2019는 비즈니스용 Skype Server 2019 풀에 속한 사용자에 대 한 데이터를 수집 합니다. 
  
- 비즈니스용 Skype 서버 2019에서 보관 및 모니터링과 함께 타사 보관 및 모니터링 솔루션을 사용 하는 경우, 타사 솔루션을 비즈니스용 Skype Server 2019와 통합 해야 하는 경우와 관련 하 여 공급 업체에 문의 하세요.
    

