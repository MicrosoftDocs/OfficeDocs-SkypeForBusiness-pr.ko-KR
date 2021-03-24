---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 성능 시나리오
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 스트레스 및 성능 도구를 사용하여 성능 및 부하 테스트를 수행하도록 비즈니스용 Skype 서버 2015를 구성하는 데 필요한 작업입니다.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105374"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 성능 시나리오
 
스트레스 및 성능 도구를 사용하여 성능 및 부하 테스트를 수행하도록 비즈니스용 Skype 서버 2015를 구성하는 데 필요한 작업입니다.
  
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구(LyncPerfTool)를 실행하려면 먼저 비즈니스용 Skype 서버 2015 토폴로지가 사용자와 관련된 시나리오에 맞게 구성되어야 합니다. 비즈니스용 Skype 서버 2015가 구성되지 않거나 잘못 구성된 경우 부하 시뮬레이션이 실패할 가능성이 매우 높습니다. 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 사용하여 도구 다운로드의 일부로 예제 비즈니스용 Skype 서버 관리 셸 스크립트 및 기본 리소스 [파일을 제공합니다.](https://www.microsoft.com/download/details.aspx?id=50367) 이러한 구성은 비즈니스용 Skype 서버 배포를 구성하기 위한 시작 지점으로 사용할 수 있습니다. 이 문서에서는 제공된 Windows PowerShell 설명합니다.
  
> [!NOTE]
> 이 항목은 일반적으로 비즈니스용 Skype 서버 2015를 구성하는 방법을 설명하는 데 도움이되지 않습니다. 이에 대한 다른 계획 및 배포 항목도 있습니다. 비즈니스용 Skype 서버 2015에서 Windows PowerShell 대한 자세한 내용은 Insert introduction HERE에서 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>비즈니스용 Skype 서버 관리 셸 스크립트 실행

부하 시뮬레이션을 준비하는 데 사용할 수 있는 샘플 PowerShell 스크립트를 제공합니다. 이러한 스크립트는 로드 시뮬레이션을 위한 것이기 때문에 간단하고 쉽게 사용할 수 있습니다. 이는 프로덕션 환경에 적합하지 않을 수 있습니다. 다시 한 번 이러한 스크립트는 샘플이며, 이를 검토해야 함을 강조하고, 대부분의 경우 실제적으로 사용하기 전에 사용자 환경과 관련된 변경을 적용해야 합니다. 최소한 토폴로지와 함께 RSG(응답 서비스 그룹) 스크립트를 수정해야 합니다(에이전트 그룹에 할당된 에이전트를 지정). 그러나 필요하지 않은 경우 실행할 필요가 있습니다.
  
> [!CAUTION]
> 이러한 샘플을 검토하고 이해하시기 바랍니다. 스크립트는 실행 시 토폴로지의 기존 설정을 덮어 덮어 덮어 작성합니다. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>스트레스 및 성능 도구 클라이언트 버전 이름

이전에 설정을 기본값에서 변경한 경우 클라이언트 버전 확인 정책을 구성해야 할 수 있습니다. 이 문제가 없는 경우 클라이언트 버전 확인 [설명서를 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)
  
스트레스 및 성능 도구는 비즈니스용 Skype 서버 2015와 통신할 때 기본적으로 다음 사용자 에이전트 버전을 사용합니다.
  
- LSPT/15.0.0.0(비즈니스용 Skype 서버 2015 스트레스 및 성능 도구)
    
- OCPHONE/.0.522
    
LyncPerfTool의 UCWA(Mobility) 클라이언트의 경우:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
