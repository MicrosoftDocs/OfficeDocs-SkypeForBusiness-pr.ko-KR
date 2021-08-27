---
title: 모니터링 서버 연결 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 모니터링 서버를 제거하려면 연결된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server에 대한 종속성 변경 또는 선택을 취소해야 합니다. 종속성 제거를 위해 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server의 속성을 편집합니다. 토폴로지 작성기에서 종속성의 선택을 취소하고 서버를 삭제하면 토폴로지 작성기에서 연결된 데이터베이스 저장소 개체도 삭제될 것임이 통보됩니다.
ms.openlocfilehash: 703fbfa68fe75d4e8c4a297c81eae27b0f5118c5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590592"
---
# <a name="remove-the-monitoring-server-association"></a>모니터링 서버 연결 제거

모니터링 서버를 제거하려면 연결된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server에 대한 종속성의 선택을 변경하거나 지워야 합니다. 종속성 제거를 위해 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch Appliance 및 Survivable Branch Server의 속성을 편집합니다. 토폴로지 작성기에서 종속성의 선택을 취소하고 서버를 삭제하면 토폴로지 작성기에서 연결된 데이터베이스 저장소 개체도 삭제될 것임이 통보됩니다.
  
### <a name="to-remove-the-monitoring-server-association"></a>모니터링 서버 연결을 제거하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기 를 여는 경우
    
2. 레거시 설치 노드로 이동합니다.
    
3.   **토폴로지** 작성기에서 모니터링 Enterprise Edition 정의한 Standard Edition 프런트 엔드 서버 또는 분기 사이트와 같은 프런트 엔드 풀을 확장합니다.
    
4. Survivable Branch Server가 연결된 경우 분기 사이트, 분기 사이트 이름을 확장한 다음 **Survivable Branch Appliances를 확장합니다.**
    
    > [!NOTE]
    > **사용자 인터페이스의 Survivable Branch Appliance는** Survivable Branch Server 및 Survivable Branch Appliance에 모두 적용됩니다. 
  
5. 모니터링 서버와 연결된 풀, 서버 또는 장치를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 클릭합니다.**
    
6. 속성 **편집의** **일반** 연결에서 모니터링 서버 연결 확인란의 선택을  >  취소한 다음 확인을 **클릭합니다.** 
    
7. 모니터링 서버와 연결된 다른 풀, 서버 또는 장치에 대해 이전 단계를 반복합니다.
    
8. 모니터링 서버를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.** 
    
9. **종속 저장소 삭제** 에서 **확인** 을 클릭합니다.
    
10. 토폴로지 게시, 복제 상태 확인 및 비즈니스용 Skype 서버 배포 마법사를 실행합니다. 
    

