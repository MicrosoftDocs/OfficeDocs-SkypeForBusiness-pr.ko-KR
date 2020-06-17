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
localization_priority: Normal
description: 모니터링 서버를 제거 하려면 연결 된 프런트 엔드 풀, 프런트 엔드 서버, Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 대 한 종속성을 변경 하거나 지워야 합니다. 프런트 엔드 풀, 프런트 엔드 서버, Sba (survivable Branch 기기 및 Sba (survivable 분기 서버의 속성을 편집 하 여 종속성을 제거할 수 있습니다. 종속성을 지우고 토폴로지 작성기에서 서버를 삭제 한 후에는 토폴로지 작성기의 연결 된 데이터베이스 저장소 개체도 삭제 된다는 메시지가 표시 됩니다.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753420"
---
# <a name="remove-the-monitoring-server-association"></a>모니터링 서버 연결 제거

모니터링 서버를 제거 하려면 연결 된 프런트 엔드 풀, 프런트 엔드 서버, Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 대 한 종속성을 변경 하거나 지워야 합니다. 프런트 엔드 풀, 프런트 엔드 서버, Sba (survivable 분기 어플라이언스 및 Sba (survivable 분기 서버의 속성을 편집 하 여 종속성을 제거할 수 있습니다. 종속성을 지우고 토폴로지 작성기에서 서버를 삭제 한 후에는 토폴로지 작성기의 연결 된 데이터베이스 저장소 개체도 삭제 된다는 메시지가 표시 됩니다.
  
### <a name="to-remove-the-monitoring-server-association"></a>모니터링 서버 연결을 제거하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.
    
2. 레거시 설치 노드로 이동 합니다.
    
3. 토폴로지 작성기에서 모니터링 서버가 정의 된 위치에 따라 **Enterprise Edition 프런트 엔드 풀**, **Standard Edition 프런트 엔드 서버**또는 **분기 사이트**를 확장 합니다.
    
4. Sba (survivable Branch Server가 연결 되어 있는 경우 **분기**사이트를 확장 하 고 분기 사이트 이름을 확장 한 다음 **sba (survivable 분기 기기**를 확장 합니다.
    
    > [!NOTE]
    > 사용자 인터페이스의 **Sba (survivable Branch 기기** 는 Sba (survivable branch Server 및 Sba (survivable branch 기기 둘 다에 적용 됩니다. 
  
5. 모니터링 서버와 연결 된 풀, 서버 또는 장치를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    
6. **속성 편집**의 **일반**  >  **연결**에서 **모니터링 서버 연결** 확인란의 선택을 취소 한 다음 **확인**을 클릭 합니다.
    
7. 모니터링 서버와 연결 된 다른 모든 풀, 서버 또는 장치에 대해 이전 단계를 반복 합니다.
    
8. 모니터링 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다. 
    
9. **종속 저장소 삭제**에서 **확인**을 클릭합니다.
    
10. 토폴로지를 게시 하 고, 복제 상태를 확인 하 고, 필요에 따라 비즈니스용 Skype 서버 배포 마법사를 실행 합니다. 
    

