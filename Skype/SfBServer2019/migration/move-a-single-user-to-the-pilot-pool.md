---
title: 단일 사용자를 시험 운용 풀로 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 skype server 2019 제어판 또는 비즈니스용 Skype Server 2019 Management Shell을 사용 하 여 사용자를 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다. 아래 예제에서 레지스트라 풀 열에는 레거시 풀이 pool01.contoso.net,이 풀에는 6 명의 사용자가 모두 연결 되어 있습니다. 비즈니스용 skype server 2019 제어판 및 비즈니스용 skype Server Management Shell을 사용 하 여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동 하려면 다음 절차를 사용 합니다.
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988963"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>단일 사용자를 시험 운용 풀로 이동

비즈니스용 skype server 2019 제어판 또는 비즈니스용 Skype Server 2019 Management Shell을 사용 하 여 사용자를 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 이동할 수 있습니다. 아래 예제에서 **레지스트라 풀** 열에는 레거시 풀이 **pool01.contoso.net** ,이 풀에는 6 명의 사용자가 모두 연결 되어 있습니다. 비즈니스용 skype server 2019 제어판 및 비즈니스용 skype Server Management Shell을 사용 하 여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동 하려면 다음 절차를 사용 합니다. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype 서버 2019 제어판을 사용 하 여 사용자를 이동 하려면
  
1. RTCUniversalServerAdmins 그룹의 구성원 이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 프런트 엔드 서버에 로그온 합니다.
    
2. **비즈니스용 Skype Server 제어판을**엽니다.
    
3. **사용자**를 클릭 하 고 **검색**을 클릭 한 다음 **찾기를**클릭 합니다.
    
4. 비즈니스용 Skype Server 2019 풀로 이동 하려는 사용자를 선택 합니다. 이 예제에서는 사용자 Sara 아를 이동 합니다.
    
5. **작업** 메뉴에서 **선택한 사용자 이동을 선택 하 여 그룹으로 이동**합니다.
    
6. 드롭다운 목록에서 비즈니스용 Skype 서버 2019 풀을 선택 합니다.
    
7. **작업**을 클릭 한 다음 **선택한 사용자 이동을 클릭 하 여 그룹을 선택**합니다. **확인**을 클릭합니다.
  
8. 사용자의 **등록자 그룹** 열에 사용자가 성공적으로 이동 했음을 나타내는 비즈니스용 Skype 서버 2019 풀이 포함 되어 있는지 확인 합니다. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 사용자를 이동 하려면

1. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 명령줄에 다음을 입력 합니다. 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 그런 다음 명령줄에 다음을 입력 합니다. 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. 이제 **RegistrarPool** Id는 비즈니스용 Skype 서버 2019 풀을 가리킵니다. 이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다. 

    > [!NOTE]
    > **Get-csuser** cmdlet에 대 한 자세한 내용을 보려면 **Get-help-Csuser-Detailed** 를 실행 합니다.
  

