---
title: 레거시 에지 서버에 파일럿 풀 연결
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
description: 2019 비즈니스용 Skype 서버 배포한 후 사이트에 대한 페더링 경로를 구성해야 합니다. 레거시 설치에서 사용 중이고 있는 페더니트 경로를 사용하려면 비즈니스용 Skype 서버 2019를 이 경로를 사용하도록 구성해야 합니다.
ms.openlocfilehash: a5f5da34300d993f59d4de5e2eb0b47cc58eff0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607465"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>레거시 에지 서버에 파일럿 풀 연결

2019 비즈니스용 Skype 서버 배포한 후 사이트에 대한 페더링 경로를 구성해야 합니다. 레거시 설치에서 사용 중이고 있는 페더니트 경로를 사용하려면 비즈니스용 Skype 서버 2019를 이 경로를 사용하도록 구성해야 합니다. 
  
비즈니스용 Skype 서버 2019 사이트에서 레거시 배포의 Director 및 에지 서버를 사용하도록 설정하려면 토폴로지 작성기에서 레거시 에지 풀을 연결합니다.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>토폴로지 작성기를 사용하여 레거시 에지 풀을 연결하려면

1. 토폴로지 작성기를 엽니다. 
    
2. 사이트(사이트 노드 바로 **아래에 있는 비즈니스용 Skype 서버** 선택합니다. 
    
3. **동작** 메뉴에서 **속성 편집** 을 클릭합니다.
    
4. 왼쪽 창에서 **페더레이션 경로** 를 선택합니다.
    
5. 사이트 **페더ation** 경로 지정에서 **SIP** 페더ation 사용 을 선택한 다음 레거시 Director 또는 레거시 에지 서버를 선택합니다(Director가 나열되지 않은 경우).
  
6. **확인** 을 클릭하여 **속성 편집** 페이지를 닫습니다. 
    
7. 토폴로지 작성기의 비즈니스용 Skype 서버 2019 노드에서 Standard Edition **서버** 또는 Enterprise Edition 프런트 엔드 풀로 이동하고 풀을 마우스 오른쪽 **단추로** 클릭한 다음 속성 편집을 **클릭합니다.**
    
8. **연결** 에서 **에지 풀 연결(미디어 구성 요소)** 옆의 확인란을 선택합니다. 
    
9. 목록에서 레거시 에지 서버를 선택합니다. 
  
10. **확인** 을 클릭하여 **속성 편집** 페이지를 닫습니다. 
    
11. **토폴로지 작성기에서** 맨 위에 있는 노드를 선택하고 을 **비즈니스용 Skype 서버.**
    
12. **동작** 메뉴에서 **토폴로지 게시** 를 클릭하고 **다음** 을 클릭합니다.
    
13. **게시 마법사** 가 완료되면 **마침** 을 클릭합니다.
    

