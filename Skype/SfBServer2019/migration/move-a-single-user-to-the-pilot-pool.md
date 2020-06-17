---
title: 파일럿 풀로 단일 사용자 이동
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
description: 비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 사용자를 이동할 수 있습니다. 아래 예에서 등록자 풀 열에 pool01.contoso.net이 레거시 풀이 고 6 명의 사용자 모두가이 풀에 연결 되어 있습니다. 다음 절차에 따라 비즈니스용 skype 서버 2019 제어판 및 비즈니스용 Skype 서버 관리 셸을 사용 하 여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752510"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>파일럿 풀로 단일 사용자 이동

비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 사용자를 이동할 수 있습니다. 아래 예에서 **등록자 풀** 열에 **pool01.contoso.net** 이 레거시 풀이 고 6 명의 사용자 모두가이 풀에 연결 되어 있습니다. 다음 절차에 따라 비즈니스용 skype 서버 2019 제어판 및 비즈니스용 Skype 서버 관리 셸을 사용 하 여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동 합니다. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype 서버 2019 제어판을 사용 하 여 사용자를 이동 하려면
  
1. RTCUniversalServerAdmins 그룹의 구성원이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원인 계정으로 프런트 엔드 서버에 로그온합니다.
    
2. **비즈니스용 Skype 서버 제어판을**엽니다.
    
3. **사용자**를 클릭 하 고 **검색**을 클릭 한 다음 **찾기를**클릭 합니다.
    
4. 비즈니스용 Skype 서버 2019 풀로 이동 하려는 사용자를 선택 합니다. 이 예에서는 Sara Davis를 이동합니다.
    
5. **동작** 메뉴에서 **선택한 사용자를 풀로 이동**을 선택합니다.
    
6. 드롭다운 목록에서 비즈니스용 Skype 서버 2019 풀을 선택 합니다.
    
7. **동작**을 클릭하고 **선택한 사용자를 풀로 이동**을 클릭합니다. **확인**을 클릭합니다.
  
8. 사용자의 **등록자 풀** 열에 사용자가 성공적으로 이동 되었음을 나타내는 비즈니스용 Skype 서버 2019 풀이 포함 되어 있는지 확인 합니다. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 사용자를 이동 하려면

1. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 그런 다음 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. 이제 **RegistrarPool** Id가 비즈니스용 Skype 서버 2019 풀을 가리킵니다. 이 ID가 있으면 사용자가 성공적으로 이동되었음을 나타냅니다. 

    > [!NOTE]
    > **Csuser** cmdlet에 대 한 자세한 내용을 보려면 **Get-help 사용자-Detailed** 를 실행 합니다.
  

