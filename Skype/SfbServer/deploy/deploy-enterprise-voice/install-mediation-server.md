---
title: 중재 서버에 대한 파일을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
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
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '요약: 중재 서버에 대한 파일을 설치하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: e74c966cc43b9768b107aff559429eb8a639e2cd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397451"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>중재 서버에 대한 파일을 비즈니스용 Skype 서버
 
**요약:** 중재 서버에 대한 파일을 설치하는 방법을 비즈니스용 Skype 서버.
  
이 절차를 성공적으로 완료하려면 최소한 RTCUniversalReadOnlyAdmins 그룹의 구성원 자격이 있는 로컬 관리자 및 도메인 사용자로 서버에 로그온해야 합니다.
  
이 항목의 단계에 따라 비즈니스용 Skype 서버 배포 마법사를 실행하여 토폴로지 작성기에서 풀을 정의하고 게시한 후 중재 서버 풀에 추가한 컴퓨터에 중재 서버용 파일을 설치합니다. 중재 서버를 설치할 때 중재 서버 풀의 각 컴퓨터에 필요한 인증서도 설치하고 할당합니다. 
  
> [!NOTE]
> 이 항목에서는 [Deploy a Mediation Server in Topology Builder in 비즈니스용 Skype 서버](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>독립 실행형 중재 서버 풀에 대한 파일을 설치하려면

1. 설치 미디어에서 를  _\<installation media\>_ 마우스 **오른쪽**\Setup\amd64\Setup.exe클릭한 다음 **관리자 권한으로 실행을 클릭합니다**.
    
2. 설치 **위치 페이지에서** 확인을 **클릭합니다**.
    
3. 최종 **사용자 사용권 계약** 페이지에서 동의를 **클릭한 다음** 확인을 **클릭합니다**. (계속하려면 필수)
    
4. 배포 **비즈니스용 Skype 서버 페이지에서** 시스템 설치 또는 비즈니스용 Skype 서버 **클릭합니다**.
    
5. 1단계 **: 로컬 구성 저장소 설치 옆에** 있는 실행을 **클릭한 다음** 화면의 지침을 따릅니다.
    
6. 중앙 관리 **저장소의 로컬 복제본 구성 페이지에서** 기본 검색을 중앙 관리 저장소에서 직접 적용하고 다음을 **클릭합니다**.
    
7. 명령 **실행** 페이지에서 작업 상태가 완료로 표시 **되면** 마친을 **클릭합니다**.
    
8. **2단계:** 구성 요소 비즈니스용 Skype 서버 설치 또는 제거 옆에 있는 **실행을 클릭** 한 후 다음을 **클릭합니다**.
    
9. 명령 **실행** 페이지에서 작업 상태가 완료로 표시 **되면** 마친을 **클릭합니다**.
    
10. **3단계: 인증서 요청, 설치** 또는 할당 옆에 있는 실행을 **클릭합니다**. 기본 설정을 수락하여 화면의 지침을 따릅니다. 중재 서버에는 하나의 인증서가 필요하기 때문에 **3** 단계를 두 번 실행합니다. 한 번은 필수 인증서를 발급하고 한 번 더 할당합니다.
    
11. 인증서가 발급되고 올바르게 할당되면 **4단계:** 서비스 시작 옆에 있는 실행을 클릭한 다음 화면의 지침을 따릅니다.
    
12. **4단계** 가 성공적으로 완료되면 서버를 다시 시작하고 DomainAdmins 그룹의 구성원으로 서버에 로그온합니다.
    
13. 비즈니스용 Skype 서버 제어판을 실행하는 컴퓨터에서 비즈니스용 Skype 서버 제어판의 토폴로지 페이지에서 중재 서버  의 서비스 상태가 녹색 확인 표시로 표시되는지 확인합니다. 대신 빨간색 X가 나타나면 중재 서버를 선택합니다. 작업 **메뉴에서** 모든 **서비스 시작을 클릭합니다**. 
    
중재 서버 풀에 컴퓨터를 여러 대 추가한 경우 중재 서버 풀의 다른 모든 컴퓨터에서 이 절차의 단계를 수행합니다. 다른 컴퓨터의 중재 서버에 대한 파일을 설치할 필요가 없는 경우 이 중재 서버 풀[(또는 사이트의 모든 중재 서버)과](configure-trunks.md) 피어 간의 트렁크 연결에 대한 설정을 구성하려면 비즈니스용 Skype 서버에서 트렁크 구성의 절차에 따라 구성합니다.

