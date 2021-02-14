---
title: 사용자 복제가 완료되었는지 확인
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
description: Move-CsUser cmdlet을 실행하는 경우 초기 복제가 불완전하기 때문에 AD DS(Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화되지 않는 경우 오류가 발생합니다. 비즈니스용 Skype 서버 2019 User Replicator 서비스의 초기 동기화가 성공적으로 완료되는 데 걸리는 시간은 비즈니스용 Skype 서버 2019 풀을 호스트하는 Active Directory 포리스트에서 호스트되는 도메인 컨트롤러의 수에 따라 달라 습니다. 비즈니스용 Skype 서버 2019 User Replicator 서비스 초기 동기화 프로세스는 비즈니스용 Skype 서버 2019 프런트 엔드 서버가 처음 시작될 때 발생합니다. 그런 다음 동기화는 User Replicator 간격을 기준으로 합니다. 사용자 복제가 완료된 후 cmdlet을 실행하기 전에 다음 단계를 Move-CsUser 합니다.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751650"
---
# <a name="verify-user-replication-has-completed"></a>사용자 복제가 완료되었는지 확인

**Move-CsUser** cmdlet을 실행하는 경우 초기 복제가 불완전하기 때문에 AD DS(Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화되지 않는 경우 오류가 발생합니다. 비즈니스용 Skype 서버 2019 User Replicator 서비스의 초기 동기화가 성공적으로 완료되는 데 걸리는 시간은 비즈니스용 Skype 서버 2019 풀을 호스트하는 Active Directory 포리스트에서 호스트되는 도메인 컨트롤러의 수에 따라 달라 습니다. 비즈니스용 Skype 서버 2019 User Replicator 서비스 초기 동기화 프로세스는 비즈니스용 Skype 서버 2019 프런트 엔드 서버가 처음 시작될 때 발생합니다. 그런 다음 동기화는 User Replicator 간격을 기반으로 합니다. **Move-CsUser** cmdlet을 실행하기 전에 다음 단계를 완료하여 사용자 복제가 완료된지 확인해야 합니다. 
  
### <a name="to-verify-that-user-replication-has-completed"></a>사용자 복제가 완료되었는지 확인하려면

1. 토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.
    
2. **시작** 메뉴를 클릭한 후 **실행** 을 클릭합니다. 
    
3. **eventvwr.exe** 를 입력한 후 **확인** 을 클릭합니다.
    
4. 이벤트 뷰어에서 **응용** 프로그램 및 서비스 로그를 클릭하여 확장한 다음 비즈니스용 Skype 서버를 선택합니다. 
    
5. **동작** 창에서 **현재 로그 필터링** 을 클릭합니다.
    
6. **이벤트 원본** 목록에서 **LS User Replicator** 를 클릭합니다.
    
7. In **\<All Event IDs\>** , enter **30024,** and then click **OK.** 
    
8. 필터링된 이벤트 목록의 일반  탭에서 사용자 복제가 성공적으로 완료되었습니다. 
    

