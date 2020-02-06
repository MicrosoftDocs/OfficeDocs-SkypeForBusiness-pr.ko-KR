---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 성능 시나리오
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 스트레스 및 성능 도구를 사용 하 여 성능 및 부하 테스트를 수행 하기 위해 비즈니스용 Skype 서버 2015를 구성 하기 위해 수행 해야 하는 작업입니다.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803878"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 성능 시나리오
 
스트레스 및 성능 도구를 사용 하 여 성능 및 부하 테스트를 수행 하기 위해 비즈니스용 Skype 서버 2015를 구성 하기 위해 수행 해야 하는 작업입니다.
  
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 (L보완 Cperftool)를 실행 하려면 비즈니스용 Skype 서버 2015 토폴로지가 사용자와 관련 된 시나리오를 위해 먼저 구성 되어야 합니다. 비즈니스용 Skype 서버 2015이 구성 되지 않았거나 올바르게 구성 되어 있지 않은 경우 부하 시뮬레이션이 실패할 가능성이 큽니다. 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 사용 하는 경우 [도구 다운로드](https://www.microsoft.com/download/details.aspx?id=50367)의 일부로 비즈니스용 Skype 서버 관리 셸 스크립트와 기본 리소스 파일에 대 한 예를 제공 하 고 있습니다. 이는 비즈니스용 Skype 서버 배포를 구성 하는 출발점으로 사용할 수 있습니다. 이 문서에서는 제공 되는 Windows PowerShell 예제에 대해 설명 합니다.
  
> [!NOTE]
> 이 항목에서는 비즈니스용 Skype Server 2015를 구성 하는 방법을 설명 하는 데 도움이 되지 않습니다 .이에 대 한 다른 계획 및 배포 항목이 있습니다. 비즈니스용 Skype 서버 2015에서 Windows PowerShell을 사용 하는 방법에 대 한 자세한 내용은 여기 소개의 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>비즈니스용 Skype 서버 관리 셸 스크립트를 실행 하는 방법

부하 시뮬레이션을 준비 하는 데 사용할 수 있는 샘플 PowerShell 스크립트를 제공 하 고 있습니다. 이러한 스크립트는 부하 시뮬레이션을 위한 것 이므로 간단 하 고 관대 합니다. 이는 프로덕션 환경에 적합 하지 않을 수 있습니다. 이번에도 이러한 스크립트는 샘플 이므로이를 검토 해야 하며, 대부분의 경우 해당 작업을 효율적으로 사용할 수 있도록 하기 전에 사용자의 환경과 관련 된 변경이 필요 합니다. 최소한, 상담원에 게 할당 된 에이전트를 지정 하려면 토폴로지가 염두에 있는 RSG (응답 서비스 그룹) 스크립트를 수정 해야 할 것입니다. 하지만 필요 하지 않은 경우에는이를 실행할 필요가 없습니다.
  
> [!CAUTION]
> 이러한 샘플을 검토 하 고 이해 하는 데 주의 하세요. 스크립트를 실행 하면 토폴로지의 기존 설정이 덮어쓰여집니다. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>스트레스 및 성능 도구 클라이언트 버전 이름

이전에 기본값의 설정을 변경한 경우 클라이언트 버전 검사 정책을 구성 해야 할 수 있습니다. 이에 대해 잘 모르는 경우 [클라이언트 버전 검사 설명서](https://msdn.microsoft.com/en-us/vsto/jj923060)를 참조 하세요.
  
스트레스 및 성능 도구는 비즈니스용 Skype 서버 2015와 통신할 때 기본적으로 다음 사용자 에이전트 버전을 사용 합니다.
  
- LSPT/15.0.0.0 (비즈니스용 Skype Server 2015 스트레스 및 성능 도구)
    
- OCPHONE/0.522
    
L Ccptool의 Mobility (모바일) 클라이언트에 대해 다음을 수행 합니다.
  
- 도구/웹 회의
    
- 도구/모바일
    

