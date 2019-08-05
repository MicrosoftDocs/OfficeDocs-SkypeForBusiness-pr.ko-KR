---
title: 사용자 복제가 완료 되었는지 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이동-CsUser cmdlet을 실행할 때 AD DS (Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화 되지 않아 오류가 발생할 수 있습니다. 초기 복제가 완료 되지 않았습니다. 비즈니스용 Skype 서버 2019 사용자 복제기 서비스의 초기 동기화가 완료 되는 데 걸리는 시간은 비즈니스용 Skype를 호스트 하는 Active Directory 포리스트에서 호스팅되는 도메인 컨트롤러 수에 따라 달라 집니다. 서버 2019 풀. 비즈니스용 skype Server 2019 사용자 복제기 서비스 초기 동기화 프로세스가 처음으로 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 시작 하면이 문제가 발생 합니다. 이후 동기화는 사용자 복제기 간격을 기준으로 합니다. 다음 단계를 완료 하 여 CsUser cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 합니다.
ms.openlocfilehash: d5d0462ec2886c73fb7286860eea2c89e0fea9fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189060"
---
# <a name="verify-user-replication-has-completed"></a>사용자 복제가 완료 되었는지 확인

**이동-csuser** cmdlet을 실행할 때 AD DS (Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화 되지 않은 경우, 초기 복제가 완료 되지 않아 오류가 발생할 수 있습니다. 비즈니스용 Skype 서버 2019 사용자 복제기 서비스의 초기 동기화가 완료 되는 데 걸리는 시간은 비즈니스용 Skype를 호스트 하는 Active Directory 포리스트에서 호스팅되는 도메인 컨트롤러 수에 따라 달라 집니다. 서버 2019 풀. 비즈니스용 skype Server 2019 사용자 복제기 서비스 초기 동기화 프로세스가 처음으로 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 시작 하면이 문제가 발생 합니다. 그 이후에는 동기화가 사용자 복제기 간격을 기준으로 합니다. 다음 단계를 완료 하 여 **csuser** cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 합니다. 
  
### <a name="to-verify-that-user-replication-has-completed"></a>사용자 복제가 완료 되었는지 확인 하려면

1. 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.
    
2. **시작** 메뉴를 클릭 한 다음 **실행**을 클릭 합니다. 
    
3. **Eventvwr**을 입력 한 다음 **확인**을 클릭 합니다.
    
4. 이벤트 뷰어에서 **응용 프로그램 및 서비스 로그** 를 클릭 하 여 확장 한 다음 비즈니스용 Skype 서버를 선택 합니다. 
    
5. **작업** 창에서 **현재 로그 필터링**을 클릭 합니다.
    
6. **이벤트 원본** 목록에서 **LS 사용자 복제기**를 클릭 합니다.
    
7. ** \<모든 이벤트 id\>** 에 **30024**를 입력 한 다음 **확인**을 클릭 합니다. 
    
8. 필터링 된 이벤트 목록의 **일반** 탭에서 사용자 복제가 성공적으로 완료 되었다는 항목을 찾습니다. 
    

