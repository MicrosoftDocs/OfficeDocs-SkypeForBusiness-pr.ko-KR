---
title: 파일럿 풀로 여러 사용자 이동
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
description: 비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용하여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 여러 사용자를 이동할 수 있습니다.
ms.openlocfilehash: fc4d14d26a76ff4dbfc690fc7517aba77afd253f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726317"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>파일럿 풀로 여러 사용자 이동

비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용하여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 여러 사용자를 이동할 수 있습니다.

 **이 문서의**
  
[비즈니스용 Skype 서버 2019 제어판을 사용하여 여러 사용자를 이동](#sectionSection0)
  
[2019 관리 셸을 사용하여 여러 비즈니스용 Skype 서버 이동](#sectionSection1)
  
[2019 2019 관리 셸을 사용하여 모든 비즈니스용 Skype 서버 이동](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype 서버 2019 제어판을 사용하여 여러 사용자를 이동
<a name="sectionSection0"> </a>

1. 제어판을 비즈니스용 Skype 서버 를 니다.
    
2. **사용자,** **검색을 클릭한** 다음 찾기를 **클릭합니다.**
    
3. 2019 풀로 이동하려는 두 사용자를 비즈니스용 Skype 서버 선택합니다. 이 예에서는 사용자 Chen Yang과 Claus Hansen을 이동하겠습니다.
    
     ![사용자를 특정 등록 풀로 이동](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. **동작** 메뉴에서 **선택한 사용자를 풀로 이동** 을 선택합니다.
    
5. 드롭다운 목록에서 2019 비즈니스용 Skype 서버 선택합니다.
    
6. **동작** 을 클릭하고 **선택한 사용자를 풀로 이동** 을 클릭합니다. **확인** 을 클릭합니다.
    
     ![사용자 이동, 대상 등록자 풀 대화 상자](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 이제 사용자의 **등록자** 풀 열에 사용자가 성공적으로 이동된 비즈니스용 Skype 서버 2019 풀이 포함되어 있는지 확인해야 합니다. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>2019 관리 셸을 사용하여 여러 비즈니스용 Skype 서버 이동
<a name="sectionSection1"> </a>

1. 2019 비즈니스용 Skype 서버 셸을 열 수 있습니다. 
    
2. 명령줄에 다음을 입력하고 **User1** 및 **User2를** 이동할 특정 사용자 이름으로 바꾸고 pool_FQDN 대상 풀의 **이름으로** 바 대체합니다. 이 예에서는 Hao Chen과 Katie Jordan을 이동하겠습니다. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell cmdlet의 Get-CsUser.](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. 등록자 **풀** ID는 이제 이전 단계에서  pool_FQDN 지정한 풀을 포인트로 지정해야 합니다. ID는 이제 사용자가 이전 단계에서 pool_FQDN으로 지정한 풀을 가리킵니다.이 ID가 있으면 사용자가 성공적으로 이동된 것입니다. 단계를 반복하여 **User2가** 이동된 것을 확인할 수 있습니다. 
    
     ![-Identity cmdlet을 Get-UsUser PowerShell 출력입니다.](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>2019 2019 관리 셸을 사용하여 모든 비즈니스용 Skype 서버 이동
<a name="sectionSection2"> </a>

이 예에서는 모든 사용자가 레거시 풀(pool01.contoso.net)로 반환됩니다. 비즈니스용 Skype 서버 2019 관리 셸을 사용하여 모든 사용자를 동시에 비즈니스용 Skype 서버 2019 풀(pool02.contoso.net)로 pool02.contoso.net.
  
1. 2019 비즈니스용 Skype 서버 셸을 열 수 있습니다.
    
2. 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 및 결과 관리 셸.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 파일럿 사용자 중 하나에 대해 **Get-CsUser를** 실행합니다. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 각 **사용자에 대한** 등록자 풀 ID는 이제 사용자가 이전 단계에서 pool_FQDN **지정한** 풀을 지정합니다. 이 ID가 있으면 사용자가 성공적으로 이동되었음을 나타냅니다. 
    
5. 또한 비즈니스용 Skype 서버 2019 제어판의 사용자 목록을 보고 등록자 풀 값이 이제 비즈니스용 Skype 서버 2019 풀을 비즈니스용 Skype 서버 있습니다.
    
     ![비즈니스용 Skype 서버 2019 제어판 사용자 목록입니다.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

