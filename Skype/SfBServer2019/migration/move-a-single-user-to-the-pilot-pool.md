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
description: 비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용하여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 사용자를 이동할 수 있습니다. 아래 예제에서 등록자 풀 열에서 pool01.contoso.net 레거시 풀이 있으며 이러한 6명 모두 이 풀에 연결됩니다. 다음 절차에 따라 비즈니스용 Skype 서버 2019 제어판 및 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동합니다.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752510"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>파일럿 풀로 단일 사용자 이동

비즈니스용 Skype 서버 2019 제어판 또는 비즈니스용 Skype 서버 2019 관리 셸을 사용하여 레거시 풀에서 비즈니스용 Skype 서버 2019 파일럿 풀로 사용자를 이동할 수 있습니다. 아래 예제에서 등록자  풀 열에서  pool01.contoso.net 레거시 풀이 있으며 이러한 6명 모두 이 풀에 연결됩니다. 다음 절차에 따라 비즈니스용 Skype 서버 2019 제어판 및 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자를 비즈니스용 Skype 서버 2019 풀로 이동합니다. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype 서버 2019 제어판을 사용하여 사용자를 이동
  
1. RTCUniversalServerAdmins 그룹의 구성원이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원인 계정으로 프런트 엔드 서버에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 제어판을 니다.**
    
3. 사용자, **검색을** 클릭한 다음 찾기를 **클릭합니다.** 
    
4. 비즈니스용 Skype 서버 2019 풀로 이동할 사용자를 선택합니다. 이 예에서는 Sara Davis를 이동합니다.
    
5. **동작** 메뉴에서 **선택한 사용자를 풀로 이동** 을 선택합니다.
    
6. 드롭다운 목록에서 비즈니스용 Skype 서버 2019 풀을 선택합니다.
    
7. **동작** 을 클릭하고 **선택한 사용자를 풀로 이동** 을 클릭합니다. **확인** 을 클릭합니다.
  
8. 사용자의 등록자 풀 열에 이제 사용자가 성공적으로 이동된 비즈니스용 Skype 서버 2019 풀이 포함되어 있는지 확인해야 합니다.  
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype 서버 2019 관리 셸을 사용하여 사용자를 이동

1. 비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.
    
2. 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 그런 다음 명령줄에 다음을 입력합니다. 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool** ID는 이제 비즈니스용 Skype 서버 2019 풀을 포인트로 합니다. 이 ID가 있으면 사용자가 성공적으로 이동되었음을 나타냅니다. 

    > [!NOTE]
    > **Get-CsUser** cmdlet에 대한 자세한 내용은 **Get-Help Get-CsUser -Detailed를 실행합니다.**
  

