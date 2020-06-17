---
title: 여러 사용자를 파일럿 풀로 이동
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
description: 비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 레거시 풀의 여러 사용자를 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753430"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>여러 사용자를 파일럿 풀로 이동

비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 레거시 풀의 여러 사용자를 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다.

 **이 문서의 내용**
  
[비즈니스용 Skype 서버 2019 제어판을 사용 하 여 여러 사용자를 이동 하려면](#sectionSection0)
  
[비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 여러 사용자를 이동 하려면](#sectionSection1)
  
[비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 모든 사용자를 동시에 이동 하려면](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype 서버 2019 제어판을 사용 하 여 여러 사용자를 이동 하려면
<a name="sectionSection0"> </a>

1. 비즈니스용 Skype 서버 제어판을 엽니다.
    
2. **사용자**를 클릭 하 고 **검색**을 클릭 한 다음 **찾기를**클릭 합니다.
    
3. 비즈니스용 Skype 서버 2019 풀로 이동할 두 명의 사용자를 선택 합니다. 이 예에서는 사용자 Chen Yang과 Claus Hansen을 이동하겠습니다.
    
     ![사용자를 특정 등록 풀로 이동](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. **동작** 메뉴에서 **선택한 사용자를 풀로 이동**을 선택합니다.
    
5. 드롭다운 목록에서 비즈니스용 Skype 서버 2019 풀을 선택 합니다.
    
6. **동작**을 클릭하고 **선택한 사용자를 풀로 이동**을 클릭합니다. **확인**을 클릭합니다.
    
     ![사용자 이동, 대상 등록자 풀 대화 상자](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 사용자의 **등록자 풀** 열에 사용자가 성공적으로 이동 되었음을 나타내는 비즈니스용 Skype 서버 2019 풀이 포함 되어 있는지 확인 합니다. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 여러 사용자를 이동 하려면
<a name="sectionSection1"> </a>

1. 비즈니스용 Skype 서버 2019 관리 셸을 엽니다. 
    
2. 명령줄에 다음을 입력 하 고 **User1** **과 사용자 \을 이동할** 특정 사용자 이름으로 바꾸고 **pool_FQDN** 를 대상 풀의 이름으로 바꿉니다. 이 예에서는 Hao Chen과 Katie Jordan을 이동하겠습니다. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get CsUser cmdlet의 예](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. 이제 **등록자 풀** id가 이전 단계에서 **pool_FQDN** 으로 지정한 풀을 가리켜야 합니다. ID는 이제 사용자가 이전 단계에서 pool_FQDN으로 지정한 풀을 가리킵니다.이 ID가 있으면 사용자가 성공적으로 이동된 것입니다. 단계를 반복 하 여 e s e r **2가 이동** 되었는지 확인 합니다. 
    
     ![PowerShell Get-UsUser-Identity cmdlet의 출력](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 모든 사용자를 동시에 이동 하려면
<a name="sectionSection2"> </a>

이 예에서는 모든 사용자가 레거시 풀 (pool01.contoso.net)로 반환 되었습니다. 비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 모든 사용자를 동시에 비즈니스용 Skype 서버 2019 풀 (pool02.contoso.net)로 이동 합니다.
  
1. 비즈니스용 Skype 서버 2019 관리 셸을 엽니다.
    
2. 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![관리 셸에서 PowerShell cmdlet 및 결과](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 파일럿 사용자 중 한 명에 대해 **CsUser** 를 실행 합니다. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 이제 각 사용자의 **등록자 풀** id는 이전 단계에서 **pool_FQDN** 으로 지정한 풀을 가리킵니다. 이 ID가 있으면 사용자가 성공적으로 이동되었음을 나타냅니다. 
    
5. 또한 비즈니스용 Skype 서버 2019 제어판에서 사용자 목록을 볼 수 있으며, 등록자 풀 값이 이제 비즈니스용 Skype 서버 2019 풀을 가리키는지 확인 합니다.
    
     ![비즈니스용 Skype 서버 2019 제어판 사용자 목록](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

