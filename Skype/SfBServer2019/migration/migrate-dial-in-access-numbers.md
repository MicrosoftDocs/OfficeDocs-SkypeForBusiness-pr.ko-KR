---
title: 전화 접속 액세스 번호 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 전화 접속 액세스 번호를 비즈니스용 Skype 서버 2019로 마이그레이션하면 contact 개체를 마이그레이션하기 위해 CsApplicationEndpoint cmdlet을 실행 해야 합니다. 레거시 설치 및 비즈니스용 Skype Server 2019 공존 기간 동안 비즈니스용 Skype Server 2019에서 만든 전화 접속 액세스 번호가 레거시 설치에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다 (이 문서에서 설명). 여기.
ms.openlocfilehash: 81f100979d009f4f9b48cf9a538ec92095a67ad8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238733"
---
# <a name="migrate-dial-in-access-numbers"></a>전화 접속 액세스 번호 마이그레이션

전화 접속 액세스 번호를 비즈니스용 Skype 서버 2019로 마이그레이션하면 contact 개체를 마이그레이션하기 위해 **CsApplicationEndpoint** cmdlet을 실행 해야 합니다. 레거시 설치 및 비즈니스용 Skype Server 2019 공존 기간 동안 비즈니스용 Skype Server 2019에서 만든 전화 접속 액세스 번호가 레거시 설치에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다 (이 문서에서 설명). 여기. 

이전에 설치 했지만 비즈니스용 Skype Server 2019으로 또는 마이그레이션 도중 또는 마이그레이션하기 이후 비즈니스용 2019 Skype에서 만든 전화 접속 액세스 번호에는 다음과 같은 특징이 있습니다.

- Office Communications Server 2007 R2 모임 초대 및 전화 접속 액세스 번호 페이지에는 나타나지 않습니다.

- 레거시 설치 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.

- 비즈니스용 Skype 서버 2019 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.

- Office Communications Server 2007 R2 관리 도구에서 보거나 수정할 수 없습니다.

- 레거시 설치 제어판 및 레거시 설치 관리 셸에서 보고 수정할 수 있습니다.

- 비즈니스용 Skype Server 2019 제어판 및 비즈니스용 Skype Server 2019 관리 셸에서 보고 수정할 수 있습니다.

- CsDialinConferencingAccessNumber cmdlet을 Priority 매개 변수를 사용 하 여 영역 내에서 다시 시퀀싱 될 수 있습니다.

레거시 설치 풀의 역할을 해제 하기 전에 레거시 설치 풀을 가리키는 전화 접속 액세스 번호 마이그레이션을 완료 해야 합니다. 다음 절차에 설명 된 대로 전화 접속 액세스 번호 마이그레이션을 완료 하지 않은 경우에는 액세스 번호로 수신 되는 호출이 실패 합니다.

> [!IMPORTANT]
> 레거시 설치 풀의 역할을 해제 하기 전에이 절차를 수행 해야 합니다. 

> [!NOTE]
> 짧은 서비스 중단 기간이 있는 경우 네트워크 사용량이 낮을 때 전화 접속 액세스 번호를 이동 하는 것이 좋습니다. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>전화 접속 액세스 번호를 확인 하 고 이동 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

2. 각 전화 접속 액세스 번호를 비즈니스용 Skype Server 2019에서 호스팅하는 풀로 이동 하려면 명령줄 실행에서 다음을 수행 합니다. 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. 비즈니스용 Skype Server 제어판을 엽니다.

4. 왼쪽 탐색 모음에서 **회의**를 클릭 합니다.

5. **전화 접속 액세스 번호** 탭을 클릭 합니다. 

6. 마이그레이션하는 레거시 설치 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.

    > [!NOTE]
    > 모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019 풀을 가리키는 경우에는 레거시 설치 풀을 해제할 수 있습니다. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인

1. **Csuseradministrator** 역할 또는 **csadministrator** 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 

2. 비즈니스용 Skype Server 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **회의**를 클릭 합니다.

4. **전화 접속 액세스 번호** 탭을 클릭 합니다. 

5. 모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인

1. 비즈니스용 Skype 서버 관리 셸을 엽니다.

2. 마이그레이션된 모든 전화 접속 회의 액세스 번호를 명령줄 실행에서 반환 하려면 다음을 수행 합니다.

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. 모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.


