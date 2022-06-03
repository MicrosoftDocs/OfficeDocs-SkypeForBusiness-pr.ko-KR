---
title: 비즈니스용 Skype 서버 파일 공유 만들기
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '요약: 비즈니스용 Skype 서버 설치의 일부로 Windows Server 파일 공유를 만드는 방법을 알아봅니다.'
ms.openlocfilehash: 12ea75a11470d5730c891b1c738a3337ccb28ac8
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860729"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>비즈니스용 Skype 서버 파일 공유 만들기
 
**요약:** 비즈니스용 Skype 서버 설치의 일부로 Windows Server 파일 공유를 만드는 방법을 알아봅니다.
  
비즈니스용 Skype 서버 토폴로지 전체의 컴퓨터에서 파일을 교환할 수 있도록 파일 공유가 필요합니다. 파일 공유 만들기는 비즈니스용 Skype 서버 설치 프로세스의 2/8단계입니다. 1~5단계는 순서대로 수행할 수 있습니다. 그러나 다이어그램에 설명된 대로 6단계, 7단계 및 8단계를 순서대로 수행하고 1~5단계 후에 수행해야 합니다. 파일 공유에 대한 계획 세부 정보는 비즈니스용 Skype 서버 [2019에 대한 비즈니스용 Skype 서버 또는 서버 요구 사항에 대한](../../../SfBServer2019/plan/system-requirements.md) [환경 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 참조하세요.
  
![개요 다이어그램.](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>기본 파일 공유 만들기

이 섹션에서는 기본 Windows 서버 파일 공유를 만드는 방법에 대해 설명합니다. 기본 Windows 서버 파일 공유는 비즈니스용 Skype 서버 지원됩니다. 그러나 고가용성을 명시적으로 제공하지는 않습니다. 고가용성 환경의 경우 DFS(분산 파일 시스템) 파일 공유를 사용하는 것이 좋습니다. 고가용성 파일 공유 및 DFS에 대한 자세한 내용은 [비즈니스용 Skype 서버 고가용성 및 재해 복구 계획을](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 참조하세요.
  
> [!NOTE]
> Windows Server 2012 R2는 Windows Server 플랫폼을 사용하여 SAN(Storage Area Network)과 유사한 파일 공유 솔루션을 제공하는 데 큰 진전을 이루었습니다. 기존 SAN 기반 어플라이언스와 비교할 때 Windows Server 2012 R2 스토리지 솔루션은 성능에 미치는 영향을 최소화하면서 비용을 절반으로 줄일 수 있습니다. Windows Server 2012 R2의 파일 공유 옵션에 대한 자세한 내용은 다운로드 가능한 백서 [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf) 참조하세요. 
  
**파일 공유를 만들기** 위한 비디오 단계를 시청하세요.
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>기본 파일 공유 만들기

1. 파일 공유를 호스트할 컴퓨터에 로그온합니다.
    
2. 공유하려는 폴더를 마우스 오른쪽 단추로 클릭하고 **속성을** 선택합니다.
    
3. **공유** 탭을 선택하고 **고급 공유** 를 클릭합니다.
    
4. **이 폴더 공유** 를 클릭합니다.
    
5. **권한** 을 클릭합니다.
    
6. 파일 공유를 호스팅하는 서버의 로컬 **관리자** 그룹을 추가하고 **허용: 모든 권한, 변경 및 읽기** 권한을 부여한 다음 **확인을** 클릭합니다.
    
7. **확인을** 다시 클릭하고 네트워크 경로를 기록해 둡다.
    
8. **완료** 를 클릭하여 마법사를 닫습니다.
    
     ![폴더 공유를 위한 공유 탭입니다.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>파일 저장소가 DFS 공유에서 호스트되는 경우 다음 경고가 수신됩니다.

`Warning: Unable to access share permissions for "\\<domain>\<share>".`

>이는 파일 서버의 관리자가 아니거나 DFS(분산 파일 시스템) 공유인 경우 필요합니다. 공유 권한이 이미 구성된 경우 이 경고를 무시할 수 있습니다. 새 공유인 경우 공유 권한을 수동으로 구성하는 방법에 대한 자세한 내용은 설명서를 참조하세요.

>DFS 공유에 대한 공유 권한에 액세스할 수 없기 때문에 비즈니스용 Skype 서버 파일 공유에 대한 그룹을 명시적으로 설정할 수 없습니다. 비즈니스용 Skype 서버 구성 요소가 적절한 권한으로 파일 공유에 액세스할 수 있도록 하려면 모든 권한 공유 권한이 있는 로컬 관리자 외에도 읽기 및 변경 수준 공유 권한으로 다음 RTC 그룹이 추가되었는지 확인합니다.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
