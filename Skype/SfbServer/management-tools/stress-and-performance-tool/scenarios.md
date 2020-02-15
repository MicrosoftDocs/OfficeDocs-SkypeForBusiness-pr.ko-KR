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
description: 작업 스트레스 및 성능 도구를 사용 하 여 성능 및 부하 테스트를 수행 하기 위해 비즈니스용 Skype 서버 2015을 구성 해야 합니다.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983853"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 성능 시나리오
 
작업 스트레스 및 성능 도구를 사용 하 여 성능 및 부하 테스트를 수행 하기 위해 비즈니스용 Skype 서버 2015을 구성 해야 합니다.
  
LyncPerfTool를 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 실행 하려면 먼저 비즈니스용 Skype 서버 2015 토폴로지를 구성 해야 합니다. 비즈니스용 Skype 서버 2015이 구성 되지 않았거나 잘못 구성 된 경우 부하 시뮬레이션이 실패할 수 있습니다. 비즈니스용 skype 서버 2015 스트레스 및 성능 도구를 사용 하는 경우 [도구 다운로드](https://www.microsoft.com/download/details.aspx?id=50367)의 일부로 비즈니스용 Skype 서버 관리 셸 스크립트와 기본 리소스 파일 예제가 제공 됩니다. 이는 비즈니스용 Skype 서버 배포를 구성 하는 시작 점으로 사용할 수 있습니다. 이 문서에서는 제공 되는 Windows PowerShell 예제에 대해 설명 합니다.
  
> [!NOTE]
> 이 항목에서는 비즈니스용 Skype 서버 2015를 구성 하는 방법을 설명 하는 데 도움이 되지 않으며,이에 대 한 다른 계획 및 배포 항목도 제공 됩니다. 비즈니스용 Skype 서버 2015에서 Windows PowerShell을 사용 하는 방법에 대 한 자세한 내용은 여기에 소개 삽입에서 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>비즈니스용 Skype 서버 관리 셸 스크립트 실행 정보

여기서는 부하 시뮬레이션을 준비 하는 데 사용할 수 있는 샘플 PowerShell 스크립트를 제공 합니다. 이러한 스크립트는 부하 시뮬레이션을 위한 것 이므로 간단 하 고 관대 한 방법으로 찾을 수 있습니다. 이는 프로덕션 환경에 적합 하지 않을 수 있습니다. 다시 말하지만 이러한 스크립트는 샘플 이기 때문에 검토 해야 하며, 대부분의 경우에는 작업을 실제로 사용 하기 전에 해당 환경과 관련 된 변경이 필요 합니다. 최소한 에이전트 그룹에 할당 된 에이전트를 지정 하려면 해당 토폴로지와 함께 RSG (응답 서비스 그룹) 스크립트를 수정 해야 합니다. 그러나 필요 하지 않은 경우에는이를 실행할 필요가 없습니다.
  
> [!CAUTION]
> 이러한 샘플은 주의 해 서 검토 하 고 이해 해야 합니다. 스크립트를 실행 하면 토폴로지의 모든 기존 설정을 덮어쓰게 됩니다. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>스트레스 및 성능 도구 클라이언트 버전 이름

이전에 설정을 기본값에서 변경한 경우에는 클라이언트 버전 검사 정책을 구성 해야 할 수 있습니다. 이에 대 한 자세한 내용은 [클라이언트 버전 검사 설명서](https://msdn.microsoft.com/vsto/jj923060)를 확인 하세요.
  
스트레스 및 성능 도구는 비즈니스용 Skype 서버 2015과 통신할 때 기본적으로 다음 사용자 에이전트 버전을 사용 합니다.
  
- LSPT/15.0.0.0입니다 (비즈니스용 Skype 서버 2015 스트레스 및 성능 도구)
    
- OCPHONE/0.522
    
LyncPerfTool에 있는 Mobility WA (모바일) 클라이언트의 경우:
  
- C 및 WA Perf 도구/웹 회의
    
- C; 및 WA 성능 도구/모바일
    

