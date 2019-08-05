---
title: 여러 사용자를 시험 운용 풀로 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 skype server 2019 제어판 또는 비즈니스용 Skype Server 2019 Management Shell을 사용 하 여 레거시 풀의 여러 사용자를 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다.
ms.openlocfilehash: 3798525145776c61eed6b1dabebe657538d7c9db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189486"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>여러 사용자를 시험 운용 풀로 이동

비즈니스용 skype server 2019 제어판 또는 비즈니스용 Skype Server 2019 Management Shell을 사용 하 여 레거시 풀의 여러 사용자를 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다.

 **이 문서의 내용**
  
[비즈니스용 Skype Server 2019 제어판을 사용 하 여 여러 사용자를 이동 하려면](#sectionSection0)
  
[비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 여러 사용자를 이동 하려면](#sectionSection1)
  
[비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 모든 사용자를 동시에 이동 하려면](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype Server 2019 제어판을 사용 하 여 여러 사용자를 이동 하려면
<a name="sectionSection0"> </a>

1. 비즈니스용 Skype Server 제어판을 엽니다.
    
2. **사용자**를 클릭 하 고 **검색**을 클릭 한 다음 **찾기를**클릭 합니다.
    
3. 비즈니스용 Skype Server 2019 풀로 이동 하려는 두 명의 사용자를 선택 합니다. 이 예제에서는 사용자 Yang 및 Claus Hansen를 이동 합니다.
    
     ![사용자를 특정 등록 풀로 이동](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. **작업** 메뉴에서 **선택한 사용자 이동을 선택 하 여 그룹으로 이동**합니다.
    
5. 드롭다운 목록에서 비즈니스용 Skype 서버 2019 풀을 선택 합니다.
    
6. **작업**을 클릭 한 다음 **선택한 사용자 이동을 클릭 하 여 그룹을 선택**합니다. **확인**을 클릭합니다.
    
     ![사용자 이동, 대상 등록자 풀 대화 상자](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 사용자의 **등록자 풀** 열에 사용자가 성공적으로 이동 했음을 나타내는 비즈니스용 Skype 서버 2019 풀이 포함 되어 있는지 확인 합니다. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 여러 사용자를 이동 하려면
<a name="sectionSection1"> </a>

1. 비즈니스용 Skype 서버 2019 관리 셸을 엽니다. 
    
2. 명령줄에 다음을 입력 하 고 **User1** 과 사용자 이름을 이동 **** 하려는 특정 사용자 이름으로 바꾼 다음 **pool_FQDN** 를 대상 풀의 이름으로 바꿉니다. 이 예제에서는 사용자 Hao 및 Katie를 이동 합니다. 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-CsUser cmdlet의 예제](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 명령줄에 다음을 입력 합니다. 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. 이제 **등록자 풀** id는 이전 단계에서 **pool_FQDN** 으로 지정한 풀을 가리킵니다. 이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다. 단계를 반복 하 여 **** ' 없음 '이 이동 되었는지 확인 합니다. 
    
     ![PowerShell Get-UsUser -Identity cmdlet의 출력](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 모든 사용자를 동시에 이동 하려면
<a name="sectionSection2"> </a>

이 예제에서는 모든 사용자가 레거시 풀 (pool01.contoso.net)에 반환 되었습니다. 비즈니스용 Skype Server 2019 관리 셸을 사용 하 여 모든 사용자를 비즈니스용 Skype Server 2019 풀 (pool02.contoso.net)으로 이동할 수 있습니다.
  
1. 비즈니스용 Skype 서버 2019 관리 셸을 엽니다.
    
2. 명령줄에 다음을 입력 합니다. 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 및 관리 셸의 결과](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 파일럿 사용자 중 한 명에 대해 **Get-CsUser** 를 실행 합니다. 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. 각 사용자의 **등록자 풀** id는 이제 이전 단계에서 **pool_FQDN** 로 지정한 풀을 가리킵니다. 이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다. 
    
5. 또한 비즈니스용 Skype Server 2019 제어판에서 사용자 목록을 보고 등록자 그룹 값이 이제 비즈니스용 Skype Server 2019 풀을 가리키는지 확인할 수 있습니다.
    
     ![비즈니스용 Skype 서버 2019 제어판 사용자 목록](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

