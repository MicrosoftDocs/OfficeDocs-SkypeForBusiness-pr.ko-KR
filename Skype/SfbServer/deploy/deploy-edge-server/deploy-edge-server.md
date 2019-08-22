---
title: 비즈니스용 Skype 서버에서 Edge 서버 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: '요약: Edge 서버 또는 Edge 풀을 비즈니스용 Skype 서버 환경에 배포 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 03cb3f1bc4a938a698c28332b4781d08434bc52f
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493106"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 Edge 서버 배포
 
**요약:** 비즈니스용 Skype 서버 환경에 Edge 서버나 Edge 풀을 배포 하는 방법에 대해 알아봅니다.
  
Edge 서버나 Edge 풀을 비즈니스용 Skype 서버 환경에 배포 하는 이유는 무엇 인가요? 내부 사용자와 상호 작용할 수 있으려면 조직의 내부 네트워크에 로그인 하지 않은 외부 사용자가 필요한 경우 필요 합니다. 이러한 외부 사용자는 인증 되 고 익명의 원격 사용자, 페더레이션 파트너 또는 기타 모바일 클라이언트가 될 수 있습니다.
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a>Edge에 대 한 배포 검사 목록 (비즈니스용 Skype 서버용)

위에서 언급 한 것 처럼 비즈니스용 Skype 서버에 대 한 Edge 서버 배포에 많은 시간이 들어갑니다. 이 검사 목록에서는 수행 해야 하는 작업에 대 한 개요를 제공 하 고 보다 자세한 단계를 안내 합니다.
  
[비즈니스용 Skype 서버에서 Edge 서버 배포 계획](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) 섹션을 시작 했을 바랍니다. 그렇지 않은 경우에는 대부분 참조 하는 항목이 여기에 자세히 설명 되어 있습니다. 배포 섹션에는 프로시저만 포함 되어 있으므로 이러한 단계를 수행 하는 이유를 알고 싶으면 계획 수립이 시작 되는 곳입니다.
  
이 문서에서는 또한 비즈니스용 Skype Server의 기본 배포를 이미 완료 했다고 가정 합니다. 해당 배포를 Edge와 나란히 표시할 수 있지만 먼저 해당 단계를 수행 해야 하는 경우에는 여기에서 설명 하는 가장자리에 대 한 토폴로지 변경을 수행할 수 있게 됩니다.
  
다음은 따라야 할 상위 수준 단계와 이러한 단계를 찾는 위치입니다.
  
- [비즈니스용 Skype 서버의 Edge 서버 시스템 요구 사항](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [비즈니스용 Skype 서버의 Edge 서버 환경 요구 사항](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [비즈니스용 Skype 서버에 대 한 Edge 토폴로지 만들기](create-your-edge-topology.md)
    
- [비즈니스용 Skype 서버에 Edge 서버 배포](deploy-edge-servers.md)
    
- [비즈니스용 Skype 서버에서 Edge 배포의 유효성 검사](validate-edge-deployment.md)
    

