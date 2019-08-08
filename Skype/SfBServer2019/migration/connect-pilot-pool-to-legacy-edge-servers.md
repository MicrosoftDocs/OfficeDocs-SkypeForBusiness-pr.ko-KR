---
title: 레거시 Edge 서버에 파일럿 풀 연결
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019을 배포한 후에는 사이트에 대 한 페더레이션 경로를 구성 해야 합니다. 레거시 설치에 사용 되는 페더레이션 경로를 사용 하기 위해서는이 경로를 사용 하도록 비즈니스용 Skype 서버 2019를 구성 해야 합니다.
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239555"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>레거시 Edge 서버에 파일럿 풀 연결

비즈니스용 Skype 서버 2019을 배포한 후에는 사이트에 대 한 페더레이션 경로를 구성 해야 합니다. 레거시 설치에 사용 되는 페더레이션 경로를 사용 하기 위해서는이 경로를 사용 하도록 비즈니스용 Skype 서버 2019를 구성 해야 합니다. 
  
비즈니스용 Skype Server 2019 사이트에서 레거시 배포의 디렉터 및 Edge 서버를 사용 하도록 설정 하려면 토폴로지 작성기를 사용 하 여 레거시 Edge 풀을 연결 합니다.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 레거시 Edge 풀을 연결 하려면

1. 토폴로지 작성기를 엽니다. 
    
2. **비즈니스용 Skype 서버** 노드 바로 아래에 있는 사이트를 선택 합니다. 
    
3. **작업** 메뉴에서 **속성 편집**을 클릭 합니다.
    
4. 왼쪽 창에서 **페더레이션 경로**를 선택 합니다.
    
5. **사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택 하 고, 레거시 감독을 선택 하거나, 디렉터가 나열 되지 않으면 레거시에 지 서버를 선택 합니다.
  
6. **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다. 
    
7. 토폴로지 작성기의 비즈니스용 Skype 서버 2019 노드에서 **Standard edition server** 또는 **Enterprise Edition 프런트 엔드 풀**로 이동 하 여 해당 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    
8. **연결**에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 옆에 있는 확인란을 선택 합니다. 
    
9. 목록에서 레거시에 지 서버를 선택 합니다. 
  
10. **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다. 
    
11. **토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.
    
12. **작업** 메뉴에서 **토폴로지 게시**를 클릭 하 고 **다음**을 클릭 합니다.
    
13. **게시 마법사** 가 완료 되 면 **마침을**클릭 합니다.
    

