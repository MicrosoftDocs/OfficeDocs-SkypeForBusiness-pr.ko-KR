---
title: 전화 접속 액세스 번호 마이그레이션
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
description: 전화 접속 액세스 번호를 비즈니스용 Skype 서버 2019로 마이그레이션하면 대화 상대 개체를 마이그레이션하기 위해 CsApplicationEndpoint cmdlet을 실행 해야 합니다. 이전 설치 및 비즈니스용 Skype 서버 2019 공존 기간 동안 비즈니스용 Skype 서버 2019에서 만든 전화 접속 액세스 번호는이 섹션에 설명 된 대로 레거시 설치에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752700"
---
# <a name="migrate-dial-in-access-numbers"></a>전화 접속 액세스 번호 마이그레이션

전화 접속 액세스 번호를 비즈니스용 Skype 서버 2019로 마이그레이션하면 대화 상대 개체를 마이그레이션하기 위해 **CsApplicationEndpoint** cmdlet을 실행 해야 합니다. 이전 설치 및 비즈니스용 Skype 서버 2019 공존 기간 동안 비즈니스용 Skype 서버 2019에서 만든 전화 접속 액세스 번호는이 섹션에 설명 된 대로 레거시 설치에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다. 

레거시 설치에서 만들었지만 비즈니스용 skype 서버 2019로, 또는 마이그레이션 전후에 비즈니스용 Skype 서버 2019에서 만든 전화 접속 액세스 번호는 다음과 같은 특징이 있습니다.

- Office Communications Server 2007 R2 모임 초대와 전화 접속 액세스 번호 페이지에 표시되지 않습니다.

- 레거시 설치 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.

- 비즈니스용 Skype 서버 2019 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.

- Office Communications Server 2007 R2 관리 도구에서 보거나 수정할 수 없습니다.

- 레거시 설치 제어판 및 레거시 설치 관리 셸에서 보거나 수정할 수 있습니다.

- 비즈니스용 Skype 서버 2019 제어판 및 비즈니스용 Skype 서버 2019 관리 셸에서 보거나 수정할 수 있습니다.

- Priority 매개 변수와 함께 et-CsDialinConferencingAccessNumber cmdlet을 사용하여 지역 내에서 다시 순차화할 수 있습니다.

레거시 설치 풀을 제거 하기 전에 레거시 설치 풀을 가리키는 전화 접속 액세스 번호 마이그레이션을 완료 해야 합니다. 다음 절차에 설명된 대로 전화 접속 액세스 번호 마이그레이션을 완료하지 않으면 액세스 번호에 대한 수신 전화가 실패합니다.

> [!IMPORTANT]
> 레거시 설치 풀의 역할을 해제 하기 전에이 절차를 수행 해야 합니다. 

> [!NOTE]
> 짧은 기간 동안 서비스 중단이 발생할 경우에 대비하여 네트워크 사용량이 낮을 때 전화 접속 액세스 번호를 이동하는 것이 좋습니다. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>전화 접속 액세스 번호를 식별하고 이동하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.

2. 각 전화 접속 액세스 번호를 비즈니스용 Skype 서버 2019에 호스트 된 풀로 이동 하려면 명령줄에서 다음을 실행 합니다. 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. 비즈니스용 Skype 서버 제어판을 엽니다.

4. 왼쪽 탐색 모음에서 **회의**를 클릭합니다.

5. **전화 접속 액세스 번호** 탭을 클릭합니다. 

6. 마이그레이션할 레거시 설치 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.

    > [!NOTE]
    > 모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019 풀을 가리키는 경우 레거시 설치 풀을 해제할 수 있습니다. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인

1. **CsUserAdministrator** 역할이나 **CsAdministrator** 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다. 

2. 비즈니스용 Skype 서버 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **회의**를 클릭합니다.

4. **전화 접속 액세스 번호** 탭을 클릭합니다. 

5. 모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인

1. 비즈니스용 Skype 서버 관리 셸을 엽니다.

2. 마이그레이션된 모든 전화 접속 회의 액세스 번호를 반환하려면 명령줄에서 다음을 실행합니다.

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. 모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.


